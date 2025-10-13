# Game.Prefabs.Modes.UnlockAtStartMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.LocalModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UnlockAtStartMode : Game.Prefabs.Modes.LocalModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase[] m_Prefabs;
    public Game.Prefabs.PrefabBase m_Requirement;

    public UnlockAtStartMode();

    public virtual System.Void ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.PrefabBase[] m_Prefabs`  

```csharp
public Game.Prefabs.PrefabBase[] m_Prefabs;
```

- `public Game.Prefabs.PrefabBase m_Requirement`  

```csharp
public Game.Prefabs.PrefabBase m_Requirement;
```


## Constructors

- `public UnlockAtStartMode()`  

```csharp
public UnlockAtStartMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void ApplyModeData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		Entity entity = Entity.Null;
		if (m_Requirement != null)
		{
			entity = prefabSystem.GetEntity(m_Requirement);
		}
		for (int i = 0; i < m_Prefabs.Length; i++)
		{
			PrefabBase prefabBase = m_Prefabs[i];
			Entity entity2 = prefabSystem.GetEntity(prefabBase);
			if (entityManager.TryGetBuffer(entity2, isReadOnly: false, out DynamicBuffer<UnlockRequirement> buffer))
			{
				buffer.Clear();
				if (entity != Entity.Null)
				{
					buffer.Add(new UnlockRequirement(entity, UnlockFlags.RequireAll));
				}
				entityManager.AddComponentData(entity2, default(Updated));
			}
		}
	}
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RecordChanges(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_Prefabs.Length; i++)
		{
			PrefabBase prefabBase = m_Prefabs[i];
			prefabSystem.GetEntity(prefabBase);
		}
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_Prefabs.Length; i++)
		{
			PrefabBase prefabBase = m_Prefabs[i];
			if (prefabBase.TryGetExactly<Unlockable>(out var component))
			{
				Entity entity = prefabSystem.GetEntity(prefabBase);
				List<PrefabBase> list = new List<PrefabBase>();
				prefabBase.GetDependencies(list);
				component.LateInitialize(entityManager, entity, list);
			}
		}
	}
```



# Game.Prefabs.TriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TriggerPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Triggers.TriggerType m_TriggerType;
    public Game.Prefabs.PrefabBase[] m_TriggerPrefabs;
    public Game.Triggers.TargetType m_TargetTypes;

    public TriggerPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Triggers.TriggerType m_TriggerType`  

```csharp
public Game.Triggers.TriggerType m_TriggerType;
```

- `public Game.Prefabs.PrefabBase[] m_TriggerPrefabs`  

```csharp
public Game.Prefabs.PrefabBase[] m_TriggerPrefabs;
```

- `public Game.Triggers.TargetType m_TargetTypes`  

```csharp
public Game.Triggers.TargetType m_TargetTypes;
```


## Constructors

- `public TriggerPrefab()`  

```csharp
public TriggerPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_TriggerPrefabs == null)
		{
			return;
		}
		PrefabBase[] triggerPrefabs = m_TriggerPrefabs;
		foreach (PrefabBase prefabBase in triggerPrefabs)
		{
			if (prefabBase != null)
			{
				prefabs.Add(prefabBase);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TriggerData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<TriggerData> buffer = entityManager.GetBuffer<TriggerData>(entity);
		if (m_TriggerPrefabs != null && m_TriggerPrefabs.Length != 0)
		{
			PrefabBase[] triggerPrefabs = m_TriggerPrefabs;
			foreach (PrefabBase prefabBase in triggerPrefabs)
			{
				if (prefabBase != null)
				{
					buffer.Add(new TriggerData
					{
						m_TriggerType = m_TriggerType,
						m_TargetTypes = m_TargetTypes,
						m_TriggerPrefab = existingSystemManaged.GetEntity(prefabBase)
					});
				}
			}
		}
		else
		{
			buffer.Add(new TriggerData
			{
				m_TriggerType = m_TriggerType,
				m_TargetTypes = m_TargetTypes
			});
		}
	}
```



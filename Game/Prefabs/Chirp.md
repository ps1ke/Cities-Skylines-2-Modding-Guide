# Game.Prefabs.Chirp

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Chirp : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PrefabBase[] m_Chirps;

    public Chirp();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase[] m_Chirps`  

```csharp
public Game.Prefabs.PrefabBase[] m_Chirps;
```


## Constructors

- `public Chirp()`  

```csharp
public Chirp();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TriggerChirpData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<TriggerChirpData> buffer = entityManager.GetBuffer<TriggerChirpData>(entity);
		if (m_Chirps == null || m_Chirps.Length == 0)
		{
			return;
		}
		PrefabBase[] chirps = m_Chirps;
		foreach (PrefabBase prefabBase in chirps)
		{
			if (prefabBase != null)
			{
				buffer.Add(new TriggerChirpData
				{
					m_Chirp = existingSystemManaged.GetEntity(prefabBase)
				});
			}
		}
	}
```



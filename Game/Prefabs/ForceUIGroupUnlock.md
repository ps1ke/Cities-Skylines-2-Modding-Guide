# Game.Prefabs.ForceUIGroupUnlock

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `RequireComponent`, `ComponentMenu`  

## Code

```csharp
public class ForceUIGroupUnlock : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.UIGroupPrefab[] m_Unlocks;

    public ForceUIGroupUnlock();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.UIGroupPrefab[] m_Unlocks`  

```csharp
public Game.Prefabs.UIGroupPrefab[] m_Unlocks;
```


## Constructors

- `public ForceUIGroupUnlock()`  

```csharp
public ForceUIGroupUnlock();
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
		components.Add(ComponentType.ReadWrite<ForceUIGroupUnlockData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<ForceUIGroupUnlockData> buffer = entityManager.GetBuffer<ForceUIGroupUnlockData>(entity);
		for (int i = 0; i < m_Unlocks.Length; i++)
		{
			Entity entity2 = existingSystemManaged.GetEntity(m_Unlocks[i]);
			buffer.Add(new ForceUIGroupUnlockData
			{
				m_Entity = entity2
			});
		}
	}
```



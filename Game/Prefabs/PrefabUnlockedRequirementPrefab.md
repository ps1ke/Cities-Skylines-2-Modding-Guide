# Game.Prefabs.PrefabUnlockedRequirementPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UnlockRequirementPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PrefabUnlockedRequirementPrefab : Game.Prefabs.UnlockRequirementPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase[] m_RequiredPrefabs;

    public PrefabUnlockedRequirementPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase[] m_RequiredPrefabs`  

```csharp
public Game.Prefabs.PrefabBase[] m_RequiredPrefabs;
```


## Constructors

- `public PrefabUnlockedRequirementPrefab()`  

```csharp
public PrefabUnlockedRequirementPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<PrefabUnlockedRequirement>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.GetBuffer<UnlockRequirement>(entity).Add(new UnlockRequirement(entity, UnlockFlags.RequireAll));
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<PrefabUnlockedRequirement> buffer = entityManager.GetBuffer<PrefabUnlockedRequirement>(entity);
		PrefabBase[] requiredPrefabs = m_RequiredPrefabs;
		foreach (PrefabBase prefabBase in requiredPrefabs)
		{
			Entity entity2 = existingSystemManaged.GetEntity(prefabBase);
			buffer.Add(new PrefabUnlockedRequirement
			{
				m_Requirement = entity2
			});
		}
	}
```



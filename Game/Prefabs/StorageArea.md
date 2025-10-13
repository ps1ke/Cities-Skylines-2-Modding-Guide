# Game.Prefabs.StorageArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StorageArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Economy.ResourceInEditor[] m_StoredResources;
    public System.Int32 m_Capacity;

    public StorageArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Economy.ResourceInEditor[] m_StoredResources`  

```csharp
public Game.Economy.ResourceInEditor[] m_StoredResources;
```

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```


## Constructors

- `public StorageArea()`  

```csharp
public StorageArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Storage>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<StorageAreaData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		Resource resource = Resource.NoResource;
		if (m_StoredResources != null)
		{
			for (int i = 0; i < m_StoredResources.Length; i++)
			{
				resource |= EconomyUtils.GetResource(m_StoredResources[i]);
			}
		}
		StorageAreaData componentData = default(StorageAreaData);
		componentData.m_Resources = resource;
		componentData.m_Capacity = m_Capacity;
		entityManager.SetComponentData(entity, componentData);
	}
```



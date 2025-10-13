# Game.Prefabs.ShorelineObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ShorelineObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_ShorelineOffset;
    public System.Boolean m_AllowDryland;

    public ShorelineObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_ShorelineOffset`  

```csharp
public System.Single m_ShorelineOffset;
```

- `public System.Boolean m_AllowDryland`  

```csharp
public System.Boolean m_AllowDryland;
```


## Constructors

- `public ShorelineObject()`  

```csharp
public ShorelineObject();
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
		components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		PlaceableObjectData componentData = entityManager.GetComponentData<PlaceableObjectData>(entity);
		componentData.m_PlacementOffset.z = m_ShorelineOffset;
		if (m_AllowDryland)
		{
			componentData.m_Flags |= PlacementFlags.OnGround | PlacementFlags.Shoreline;
		}
		else
		{
			componentData.m_Flags &= ~PlacementFlags.OnGround;
			componentData.m_Flags |= PlacementFlags.Shoreline;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```



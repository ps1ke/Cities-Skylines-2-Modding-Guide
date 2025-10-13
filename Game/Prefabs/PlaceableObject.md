# Game.Prefabs.PlaceableObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PlaceableObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.UInt32 m_ConstructionCost;
    public System.Int32 m_XPReward;

    public PlaceableObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.UInt32 m_ConstructionCost`  

```csharp
public System.UInt32 m_ConstructionCost;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
```


## Constructors

- `public PlaceableObject()`  

```csharp
public PlaceableObject();
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
		components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		PlaceableObjectData componentData = entityManager.GetComponentData<PlaceableObjectData>(entity);
		componentData.m_ConstructionCost = m_ConstructionCost;
		componentData.m_XPReward = m_XPReward;
		if ((componentData.m_Flags & (PlacementFlags.Shoreline | PlacementFlags.Floating | PlacementFlags.Hovering)) == 0)
		{
			componentData.m_Flags |= PlacementFlags.OnGround;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```



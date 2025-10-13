# Game.Prefabs.PlaceableNetPiece

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PlaceableNetPiece : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.UInt32 m_ConstructionCost;
    public System.UInt32 m_ElevationCost;
    public System.Single m_UpkeepCost;

    public PlaceableNetPiece();

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

- `public System.UInt32 m_ElevationCost`  

```csharp
public System.UInt32 m_ElevationCost;
```

- `public System.Single m_UpkeepCost`  

```csharp
public System.Single m_UpkeepCost;
```


## Constructors

- `public PlaceableNetPiece()`  

```csharp
public PlaceableNetPiece();
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
		components.Add(ComponentType.ReadWrite<PlaceableNetPieceData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new PlaceableNetPieceData
		{
			m_ConstructionCost = m_ConstructionCost,
			m_ElevationCost = m_ElevationCost,
			m_UpkeepCost = m_UpkeepCost
		});
	}
```



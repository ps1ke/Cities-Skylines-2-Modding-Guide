# Game.Prefabs.ConnectionPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ConnectionPathfind : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PathfindCostInfo m_BorderCost;
    public Game.Prefabs.PathfindCostInfo m_PedestrianBorderCost;
    public Game.Prefabs.PathfindCostInfo m_DistanceCost;
    public Game.Prefabs.PathfindCostInfo m_AirwayCost;
    public Game.Prefabs.PathfindCostInfo m_InsideCost;
    public Game.Prefabs.PathfindCostInfo m_AreaCost;
    public Game.Prefabs.PathfindCostInfo m_CarSpawnCost;
    public Game.Prefabs.PathfindCostInfo m_PedestrianSpawnCost;
    public Game.Prefabs.PathfindCostInfo m_HelicopterTakeoffCost;
    public Game.Prefabs.PathfindCostInfo m_AirplaneTakeoffCost;
    public Game.Prefabs.PathfindCostInfo m_TaxiStartCost;
    public Game.Prefabs.PathfindCostInfo m_ParkingCost;

    public ConnectionPathfind();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PathfindCostInfo m_BorderCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_BorderCost;
```

- `public Game.Prefabs.PathfindCostInfo m_PedestrianBorderCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_PedestrianBorderCost;
```

- `public Game.Prefabs.PathfindCostInfo m_DistanceCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_DistanceCost;
```

- `public Game.Prefabs.PathfindCostInfo m_AirwayCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_AirwayCost;
```

- `public Game.Prefabs.PathfindCostInfo m_InsideCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_InsideCost;
```

- `public Game.Prefabs.PathfindCostInfo m_AreaCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_AreaCost;
```

- `public Game.Prefabs.PathfindCostInfo m_CarSpawnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_CarSpawnCost;
```

- `public Game.Prefabs.PathfindCostInfo m_PedestrianSpawnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_PedestrianSpawnCost;
```

- `public Game.Prefabs.PathfindCostInfo m_HelicopterTakeoffCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_HelicopterTakeoffCost;
```

- `public Game.Prefabs.PathfindCostInfo m_AirplaneTakeoffCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_AirplaneTakeoffCost;
```

- `public Game.Prefabs.PathfindCostInfo m_TaxiStartCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_TaxiStartCost;
```

- `public Game.Prefabs.PathfindCostInfo m_ParkingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_ParkingCost;
```


## Constructors

- `public ConnectionPathfind()`  

```csharp
public ConnectionPathfind();
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
		components.Add(ComponentType.ReadWrite<PathfindConnectionData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new PathfindConnectionData
		{
			m_BorderCost = m_BorderCost.ToPathfindCosts(),
			m_PedestrianBorderCost = m_PedestrianBorderCost.ToPathfindCosts(),
			m_DistanceCost = m_DistanceCost.ToPathfindCosts(),
			m_AirwayCost = m_AirwayCost.ToPathfindCosts(),
			m_InsideCost = m_InsideCost.ToPathfindCosts(),
			m_AreaCost = m_AreaCost.ToPathfindCosts(),
			m_CarSpawnCost = m_CarSpawnCost.ToPathfindCosts(),
			m_PedestrianSpawnCost = m_PedestrianSpawnCost.ToPathfindCosts(),
			m_HelicopterTakeoffCost = m_HelicopterTakeoffCost.ToPathfindCosts(),
			m_AirplaneTakeoffCost = m_AirplaneTakeoffCost.ToPathfindCosts(),
			m_TaxiStartCost = m_TaxiStartCost.ToPathfindCosts(),
			m_ParkingCost = m_ParkingCost.ToPathfindCosts()
		});
	}
```



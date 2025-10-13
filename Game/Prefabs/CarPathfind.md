# Game.Prefabs.CarPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CarPathfind : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PathfindCostInfo m_DrivingCost;
    public Game.Prefabs.PathfindCostInfo m_TurningCost;
    public Game.Prefabs.PathfindCostInfo m_UTurnCost;
    public Game.Prefabs.PathfindCostInfo m_UnsafeUTurnCost;
    public Game.Prefabs.PathfindCostInfo m_CurveAngleCost;
    public Game.Prefabs.PathfindCostInfo m_LaneCrossCost;
    public Game.Prefabs.PathfindCostInfo m_ParkingCost;
    public Game.Prefabs.PathfindCostInfo m_SpawnCost;
    public Game.Prefabs.PathfindCostInfo m_ForbiddenCost;

    public CarPathfind();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PathfindCostInfo m_DrivingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_DrivingCost;
```

- `public Game.Prefabs.PathfindCostInfo m_TurningCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_TurningCost;
```

- `public Game.Prefabs.PathfindCostInfo m_UTurnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_UTurnCost;
```

- `public Game.Prefabs.PathfindCostInfo m_UnsafeUTurnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_UnsafeUTurnCost;
```

- `public Game.Prefabs.PathfindCostInfo m_CurveAngleCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_CurveAngleCost;
```

- `public Game.Prefabs.PathfindCostInfo m_LaneCrossCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_LaneCrossCost;
```

- `public Game.Prefabs.PathfindCostInfo m_ParkingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_ParkingCost;
```

- `public Game.Prefabs.PathfindCostInfo m_SpawnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_SpawnCost;
```

- `public Game.Prefabs.PathfindCostInfo m_ForbiddenCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_ForbiddenCost;
```


## Constructors

- `public CarPathfind()`  

```csharp
public CarPathfind();
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
		components.Add(ComponentType.ReadWrite<PathfindCarData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new PathfindCarData
		{
			m_DrivingCost = m_DrivingCost.ToPathfindCosts(),
			m_TurningCost = m_TurningCost.ToPathfindCosts(),
			m_UTurnCost = m_UTurnCost.ToPathfindCosts(),
			m_UnsafeUTurnCost = m_UnsafeUTurnCost.ToPathfindCosts(),
			m_CurveAngleCost = m_CurveAngleCost.ToPathfindCosts(),
			m_LaneCrossCost = m_LaneCrossCost.ToPathfindCosts(),
			m_ParkingCost = m_ParkingCost.ToPathfindCosts(),
			m_SpawnCost = m_SpawnCost.ToPathfindCosts(),
			m_ForbiddenCost = m_ForbiddenCost.ToPathfindCosts()
		});
	}
```



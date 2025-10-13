# Game.Prefabs.TrackPathfind

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrackPathfind : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PathfindCostInfo m_DrivingCost;
    public Game.Prefabs.PathfindCostInfo m_TwowayCost;
    public Game.Prefabs.PathfindCostInfo m_SwitchCost;
    public Game.Prefabs.PathfindCostInfo m_DiamondCrossingCost;
    public Game.Prefabs.PathfindCostInfo m_CurveAngleCost;
    public Game.Prefabs.PathfindCostInfo m_SpawnCost;

    public TrackPathfind();

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

- `public Game.Prefabs.PathfindCostInfo m_TwowayCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_TwowayCost;
```

- `public Game.Prefabs.PathfindCostInfo m_SwitchCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_SwitchCost;
```

- `public Game.Prefabs.PathfindCostInfo m_DiamondCrossingCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_DiamondCrossingCost;
```

- `public Game.Prefabs.PathfindCostInfo m_CurveAngleCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_CurveAngleCost;
```

- `public Game.Prefabs.PathfindCostInfo m_SpawnCost`  

```csharp
public Game.Prefabs.PathfindCostInfo m_SpawnCost;
```


## Constructors

- `public TrackPathfind()`  

```csharp
public TrackPathfind();
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
		components.Add(ComponentType.ReadWrite<PathfindTrackData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new PathfindTrackData
		{
			m_DrivingCost = m_DrivingCost.ToPathfindCosts(),
			m_TwowayCost = m_TwowayCost.ToPathfindCosts(),
			m_SwitchCost = m_SwitchCost.ToPathfindCosts(),
			m_DiamondCrossingCost = m_DiamondCrossingCost.ToPathfindCosts(),
			m_CurveAngleCost = m_CurveAngleCost.ToPathfindCosts(),
			m_SpawnCost = m_SpawnCost.ToPathfindCosts()
		});
	}
```



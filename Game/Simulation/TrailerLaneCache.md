# Game.Simulation.CarNavigationHelpers+TrailerLaneCache

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TrailerLaneCache
{
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Entities.Entity m_WasCurrentLane;
    private Unity.Entities.Entity m_WasNextLane;
    private Unity.Mathematics.float2 m_WasCurrentPosition;
    private Unity.Mathematics.float2 m_WasNextPosition;
    private Unity.Entities.DynamicBuffer<Game.Objects.BlockedLane> m_WasBlockedLanes;

    public TrailerLaneCache(Game.Vehicles.CarTrailerLane& trailerLane, Unity.Entities.DynamicBuffer<Game.Objects.BlockedLane> blockedLanes, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> searchTree);

    private Colossal.Mathematics.Bounds3 CalculateMaxBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
    private Colossal.Mathematics.Bounds3 CalculateMinBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
    public System.Void CheckChanges(Unity.Entities.Entity entity, Game.Vehicles.CarTrailerLane& trailerLane, Unity.Collections.NativeList<Game.Objects.BlockedLane> newBlockedLanes, Game.Net.LaneObjectCommandBuffer buffer, Unity.Entities.BufferLookup<Game.Net.LaneObject> laneObjects, Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
}
```


## Fields

- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `private Unity.Entities.Entity m_WasCurrentLane`  

```csharp
private Unity.Entities.Entity m_WasCurrentLane;
```

- `private Unity.Entities.Entity m_WasNextLane`  

```csharp
private Unity.Entities.Entity m_WasNextLane;
```

- `private Unity.Mathematics.float2 m_WasCurrentPosition`  

```csharp
private Unity.Mathematics.float2 m_WasCurrentPosition;
```

- `private Unity.Mathematics.float2 m_WasNextPosition`  

```csharp
private Unity.Mathematics.float2 m_WasNextPosition;
```

- `private Unity.Entities.DynamicBuffer<Game.Objects.BlockedLane> m_WasBlockedLanes`  

```csharp
private Unity.Entities.DynamicBuffer<Game.Objects.BlockedLane> m_WasBlockedLanes;
```


## Constructors

- `public TrailerLaneCache(Game.Vehicles.CarTrailerLane& trailerLane, Unity.Entities.DynamicBuffer<Game.Objects.BlockedLane> blockedLanes, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> searchTree)`  

```csharp
public TrailerLaneCache(Game.Vehicles.CarTrailerLane& trailerLane, Unity.Entities.DynamicBuffer<Game.Objects.BlockedLane> blockedLanes, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> searchTree);
```


## Methods

- `private CalculateMaxBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData) : Colossal.Mathematics.Bounds3`  

```csharp
private Colossal.Mathematics.Bounds3 CalculateMaxBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
```

- `private CalculateMinBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData) : Colossal.Mathematics.Bounds3`  

```csharp
private Colossal.Mathematics.Bounds3 CalculateMinBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
```

- `public CheckChanges(Unity.Entities.Entity entity, Game.Vehicles.CarTrailerLane& trailerLane, Unity.Collections.NativeList<Game.Objects.BlockedLane> newBlockedLanes, Game.Net.LaneObjectCommandBuffer buffer, Unity.Entities.BufferLookup<Game.Net.LaneObject> laneObjects, Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData) : System.Void`  

```csharp
public System.Void CheckChanges(Unity.Entities.Entity entity, Game.Vehicles.CarTrailerLane& trailerLane, Unity.Collections.NativeList<Game.Objects.BlockedLane> newBlockedLanes, Game.Net.LaneObjectCommandBuffer buffer, Unity.Entities.BufferLookup<Game.Net.LaneObject> laneObjects, Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.CarNavigation tractorNavigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
```



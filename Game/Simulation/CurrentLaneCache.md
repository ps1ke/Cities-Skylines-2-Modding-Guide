# Game.Simulation.WatercraftNavigationHelpers+CurrentLaneCache

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CurrentLaneCache
{
    private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    private Unity.Entities.Entity m_WasCurrentLane;
    private Unity.Entities.Entity m_WasChangeLane;
    private Unity.Mathematics.float2 m_WasCurvePosition;

    public CurrentLaneCache(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.EntityStorageInfoLookup entityLookup, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> searchTree);

    private Colossal.Mathematics.Bounds3 CalculateMaxBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
    private Colossal.Mathematics.Bounds3 CalculateMinBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
    public System.Void CheckChanges(Unity.Entities.Entity entity, Game.Vehicles.WatercraftCurrentLane& currentLane, Game.Net.LaneObjectCommandBuffer buffer, Unity.Entities.BufferLookup<Game.Net.LaneObject> laneObjects, Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
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

- `private Unity.Entities.Entity m_WasChangeLane`  

```csharp
private Unity.Entities.Entity m_WasChangeLane;
```

- `private Unity.Mathematics.float2 m_WasCurvePosition`  

```csharp
private Unity.Mathematics.float2 m_WasCurvePosition;
```


## Constructors

- `public CurrentLaneCache(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.EntityStorageInfoLookup entityLookup, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> searchTree)`  

```csharp
public CurrentLaneCache(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.EntityStorageInfoLookup entityLookup, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> searchTree);
```


## Methods

- `private CalculateMaxBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData) : Colossal.Mathematics.Bounds3`  

```csharp
private Colossal.Mathematics.Bounds3 CalculateMaxBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
```

- `private CalculateMinBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData) : Colossal.Mathematics.Bounds3`  

```csharp
private Colossal.Mathematics.Bounds3 CalculateMinBounds(Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
```

- `public CheckChanges(Unity.Entities.Entity entity, Game.Vehicles.WatercraftCurrentLane& currentLane, Game.Net.LaneObjectCommandBuffer buffer, Unity.Entities.BufferLookup<Game.Net.LaneObject> laneObjects, Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData) : System.Void`  

```csharp
public System.Void CheckChanges(Unity.Entities.Entity entity, Game.Vehicles.WatercraftCurrentLane& currentLane, Game.Net.LaneObjectCommandBuffer buffer, Unity.Entities.BufferLookup<Game.Net.LaneObject> laneObjects, Game.Objects.Transform transform, Game.Objects.Moving moving, Game.Vehicles.WatercraftNavigation navigation, Game.Prefabs.ObjectGeometryData objectGeometryData);
```



# Game.Simulation.CarNavigationHelpers+FindBlockedLanesIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct FindBlockedLanesIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Colossal.Mathematics.Line3+Segment m_Line;
    public System.Single m_Radius;
    public Unity.Collections.NativeList<Game.Objects.BlockedLane> m_BlockedLanes;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes;
    public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Colossal.Mathematics.Line3+Segment m_Line`  

```csharp
public Colossal.Mathematics.Line3+Segment m_Line;
```

- `public System.Single m_Radius`  

```csharp
public System.Single m_Radius;
```

- `public Unity.Collections.NativeList<Game.Objects.BlockedLane> m_BlockedLanes`  

```csharp
public Unity.Collections.NativeList<Game.Objects.BlockedLane> m_BlockedLanes;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes;
```

- `public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData;
```


## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
```

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity) : System.Void`  

```csharp
public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity);
```



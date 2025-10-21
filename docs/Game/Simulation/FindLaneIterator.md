# Game.Simulation.WatercraftNavigationHelpers+FindLaneIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct FindLaneIterator : Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Unity.Mathematics.float3 m_Position;
    public System.Single m_MinDistance;
    public Game.Vehicles.WatercraftCurrentLane m_Result;
    public Game.Net.RoadTypes m_CarType;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
    public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_PrefabCarLaneData;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem item);
}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public System.Single m_MinDistance`  

```csharp
public System.Single m_MinDistance;
```

- `public Game.Vehicles.WatercraftCurrentLane m_Result`  

```csharp
public Game.Vehicles.WatercraftCurrentLane m_Result;
```

- `public Game.Net.RoadTypes m_CarType`  

```csharp
public Game.Net.RoadTypes m_CarType;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLaneData;
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

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_PrefabCarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_PrefabCarLaneData;
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

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem item) : System.Void`  

```csharp
public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem item);
```



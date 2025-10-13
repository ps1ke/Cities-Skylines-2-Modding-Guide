# Game.Routes.RaycastJobs+RaycastRoutesJob

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct RaycastRoutesJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Collections.NativeArray<Game.Routes.RaycastJobs+RouteItem> m_Routes;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData;
    public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData;
    public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData;
    public Unity.Entities.ComponentLookup<Game.Routes.Position> m_PositionData;
    public Unity.Entities.ComponentLookup<Game.Routes.HiddenRoute> m_HiddenRouteData;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Collections.NativeArray<Game.Routes.RaycastJobs+RouteItem> m_Routes`  

```csharp
public Unity.Collections.NativeArray<Game.Routes.RaycastJobs+RouteItem> m_Routes;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.Position> m_PositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.Position> m_PositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.HiddenRoute> m_HiddenRouteData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.HiddenRoute> m_HiddenRouteData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements;
```

- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

```csharp
public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```



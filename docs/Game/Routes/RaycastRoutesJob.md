# Game.Routes.RaycastJobs+RaycastRoutesJob

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Collections.NativeArray<Game.Routes.RaycastJobs+RouteItem> m_Routes`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_PrefabTransportLineData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Position> m_PositionData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.HiddenRoute> m_HiddenRouteData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  


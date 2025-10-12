# Game.Net.RaycastJobs+RaycastLanesJob

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public System.Single m_FovTan`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Lanes`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  


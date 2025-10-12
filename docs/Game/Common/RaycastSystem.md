# Game.Common.RaycastSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_TerrainQuery`  
- `private Unity.Entities.EntityQuery m_LabelQuery`  
- `private Unity.Entities.EntityQuery m_IconQuery`  
- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectsSearchSystem`  
- `private Game.Routes.SearchSystem m_RouteSearchSystem`  
- `private Game.Notifications.IconClusterSystem m_IconClusterSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private System.Collections.Generic.List<System.Object> m_InputContext`  
- `private System.Collections.Generic.List<System.Object> m_ResultContext`  
- `private Unity.Collections.NativeList<Game.Common.RaycastInput> m_Input`  
- `private Unity.Collections.NativeList<Game.Common.RaycastResult> m_Result`  
- `private Unity.Jobs.JobHandle m_Dependencies`  
- `private System.Boolean m_Updating`  
- `private Game.Common.RaycastSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RaycastSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddInput(System.Object context, Game.Common.RaycastInput input) : System.Void`  
- `private CompleteRaycast() : System.Void`  
- `public GetResult(System.Object context) : Unity.Collections.NativeArray<Game.Common.RaycastResult>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PerformRaycast(Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> accumulator) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Common.RaycastSystem+EntityResult`  
- `Game.Common.RaycastSystem+FindEntitiesFromTreeJob`  
- `Game.Common.RaycastSystem+DequeEntitiesJob`  
- `Game.Common.RaycastSystem+RaycastTerrainJob`  
- `Game.Common.RaycastSystem+RaycastWaterSourcesJob`  
- `Game.Common.RaycastSystem+RaycastResultJob`  
- `Game.Common.RaycastSystem+TypeHandle`  


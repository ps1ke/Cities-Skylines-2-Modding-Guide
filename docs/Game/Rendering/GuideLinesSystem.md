# Game.Rendering.GuideLinesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_MarkerNodeQuery`  
- `private Unity.Entities.EntityQuery m_TempNodeQuery`  
- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  
- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.NetToolSystem m_NetToolSystem`  
- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  
- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  
- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Tools.WaterToolSystem m_WaterToolSystem`  
- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Collections.NativeList<System.Boolean> m_AngleSides`  
- `private Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> m_Tooltips`  
- `private Unity.Jobs.JobHandle m_TooltipDeps`  
- `private Game.Rendering.GuideLinesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public GuideLinesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CheckDirection(Unity.Mathematics.float2 startDir, Unity.Mathematics.float2 checkDir, Unity.Mathematics.float2& leftDir, Unity.Mathematics.float2& rightDir, System.Int32& bestLeft, System.Int32& bestRight, Unity.Mathematics.float2& leftDir2, Unity.Mathematics.float2& rightDir2, System.Int32& bestLeft2, System.Int32& bestRight2) : System.Void`  
- `private static DrawAngleIndicator(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo> tooltips, Game.Prefabs.GuideLineSettingsData guideLineSettings, Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Mathematics.float2 dir1, Unity.Mathematics.float2 dir2, System.Single size, System.Single lineWidth, System.Int32 angle, System.Boolean angleSide) : System.Void`  
- `private static DrawAreaRange(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position, Game.Prefabs.LotData lotData) : System.Void`  
- `private static DrawNetCourse(Game.Rendering.OverlayRenderSystem+Buffer buffer, Game.Tools.NetCourse netCourse, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData, Game.Prefabs.NetGeometryData netGeometryData, Game.Prefabs.GuideLineSettingsData guideLineSettings) : System.Void`  
- `private static DrawNetCourse(Game.Rendering.OverlayRenderSystem+Buffer buffer, Game.Tools.NetCourse netCourse, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Game.Prefabs.NetGeometryData netGeometryData, Game.Prefabs.GuideLineSettingsData guideLineSettings) : System.Void`  
- `private static DrawUpgradeRange(Game.Rendering.OverlayRenderSystem+Buffer buffer, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position, Game.Prefabs.GuideLineSettingsData guideLineSettings, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData) : System.Void`  
- `public GetTooltips(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.GuideLinesSystem+TooltipInfo>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.GuideLinesSystem+TooltipInfo`  
- `Game.Rendering.GuideLinesSystem+TooltipType`  
- `Game.Rendering.GuideLinesSystem+WaterToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+ObjectToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+AreaToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+SelectionToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+ZoneToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+RouteToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+NetToolGuideLinesJob`  
- `Game.Rendering.GuideLinesSystem+TypeHandle`  


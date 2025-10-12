# Game.Tools.CoveragePreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  
- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Game.Net.CoverageService m_LastService`  
- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  
- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages`  
- `private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CoveragePreviewSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetInfoviewCoverageData(Game.Prefabs.InfoviewCoverageData& coverageData) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.CoveragePreviewSystem+InitializeCoverageJob`  
- `Game.Tools.CoveragePreviewSystem+CopyServiceCoverageJob`  
- `Game.Tools.CoveragePreviewSystem+SetupCoverageSearchJob`  
- `Game.Tools.CoveragePreviewSystem+TypeHandle`  


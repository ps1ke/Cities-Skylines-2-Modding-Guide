# Game.Tools.ToolFeedbackSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers`  
- `private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers`  
- `private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap`  
- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private Unity.Entities.EntityQuery m_AppliedQuery`  
- `private Unity.Entities.EntityQuery m_TargetQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Jobs.JobHandle m_RecentDeps`  
- `private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle`  
- `private static const System.Single INFINITE_RANGE`  

## Constructors

- `public ToolFeedbackSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private ProcessModifications() : System.Void`  
- `private UpdatePending() : System.Void`  

## Nested types

- `Game.Tools.ToolFeedbackSystem+RecentKey`  
- `Game.Tools.ToolFeedbackSystem+RecentValue`  
- `Game.Tools.ToolFeedbackSystem+RecentUpdate`  
- `Game.Tools.ToolFeedbackSystem+FeedbackType`  
- `Game.Tools.ToolFeedbackSystem+SetupCoverageSearchJob`  
- `Game.Tools.ToolFeedbackSystem+FillCoverageMapJob`  
- `Game.Tools.ToolFeedbackSystem+TargetCheckJob`  
- `Game.Tools.ToolFeedbackSystem+UpdateRecentMapJob`  
- `Game.Tools.ToolFeedbackSystem+TypeHandle`  


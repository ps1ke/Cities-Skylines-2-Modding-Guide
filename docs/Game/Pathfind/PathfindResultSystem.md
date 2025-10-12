# Game.Pathfind.PathfindResultSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityCommandBuffer m_CommandBuffer`  
- `private Unity.Entities.EntityArchetype m_PathEventArchetype`  
- `private Unity.Entities.EntityArchetype m_CoverageEventArchetype`  
- `private System.UInt32 m_PendingSimulationFrameIndex`  
- `private System.Int32 m_PendingRequestCount`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> m_ResultListIndex`  
- `private System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> m_QueryStats`  
- `private Unity.Collections.NativeList<Game.Pathfind.PathfindJobs+ResultItem> m_PathfindResultBuffer`  
- `private Unity.Collections.NativeList<Game.Pathfind.CoverageJobs+ResultItem> m_CoverageResultBuffer`  
- `private Unity.Collections.NativeList<Game.Pathfind.AvailabilityJobs+ResultItem> m_AvailabilityResultBuffer`  
- `private Game.Pathfind.PathfindResultSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.UInt32 pendingSimulationFrame { get }`  
- `public System.Int32 pendingRequestCount { get }`  
- `public System.Collections.Generic.Dictionary<Game.Pathfind.PathfindResultSystem+ResultKey, Game.Pathfind.PathfindResultSystem+ResultValue> queryStats { get }`  

## Constructors

- `public PathfindResultSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddQueryStats(System.Object system, Game.Pathfind.PathfindResultSystem+QueryType queryType, Game.Pathfind.SetupTargetType originType, Game.Pathfind.SetupTargetType destinationType, System.Int32 resultLength, System.Int32 graphTraversal) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.PathfindAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  
- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.CoverageAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  
- `private ProcessResults(Game.Pathfind.PathfindQueueSystem+ActionList<Game.Pathfind.AvailabilityAction> list, Unity.Jobs.JobHandle& outputDeps, Unity.Jobs.JobHandle inputDeps) : System.Void`  
- `private ProcessResults<T>(Game.Pathfind.PathfindQueueSystem+ActionList<T> list) : System.Void`  

## Nested types

- `Game.Pathfind.PathfindResultSystem+QueryType`  
- `Game.Pathfind.PathfindResultSystem+ResultKey`  
- `Game.Pathfind.PathfindResultSystem+ResultValue`  
- `Game.Pathfind.PathfindResultSystem+TypeHandle`  


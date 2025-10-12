# Game.Simulation.PathfindSetupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  
- `private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup`  
- `private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup`  
- `private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup`  
- `private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup`  
- `private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup`  
- `private Game.Simulation.FirePathfindSetup m_FirePathfindSetup`  
- `private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup`  
- `private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup`  
- `private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup`  
- `private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup`  
- `private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList`  
- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues`  
- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues`  
- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList`  
- `private Unity.Jobs.JobHandle m_QueueDependencies`  
- `private Unity.Jobs.JobHandle m_SetupDependencies`  
- `private System.UInt32 m_QueueSimulationFrameIndex`  
- `private System.UInt32 m_SetupSimulationFrameIndex`  
- `private System.Int32 m_PendingRequestCount`  

## Properties

- `public System.UInt32 pendingSimulationFrame { get }`  
- `public System.Int32 pendingRequestCount { get }`  

## Constructors

- `public PathfindSetupSystem()`  

## Methods

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public CompleteSetup() : System.Void`  
- `private FindTargets(System.Int32 startIndex, System.Int32 endIndex) : System.Void`  
- `private FindTargets(Game.Pathfind.SetupTargetType targetType, Game.Simulation.PathfindSetupSystem+SetupData& setupData) : Unity.Jobs.JobHandle`  
- `public GetQueue(System.Object system, System.Int32 maxDelayFrames, System.Int32 spreadFrames = 0) : Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem>`  
- `public GetSetupQuery(Unity.Entities.EntityQueryDesc[] entityQueryDesc) : Unity.Entities.EntityQuery`  
- `public GetSetupQuery(Unity.Entities.ComponentType[] componentTypes) : Unity.Entities.EntityQuery`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.PathfindSetupSystem+SetupData`  
- `Game.Simulation.PathfindSetupSystem+SetupListItem`  
- `Game.Simulation.PathfindSetupSystem+ActionListItem`  
- `Game.Simulation.PathfindSetupSystem+SetupQueue`  
- `Game.Simulation.PathfindSetupSystem+DequePathTargetsJob`  


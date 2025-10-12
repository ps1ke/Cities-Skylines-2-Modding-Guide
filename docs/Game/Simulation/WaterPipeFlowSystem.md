# Game.Simulation.WaterPipeFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_NodeGroup`  
- `private Unity.Entities.EntityQuery m_EdgeGroup`  
- `private Unity.Entities.EntityArchetype m_NodeArchetype`  
- `private Unity.Entities.EntityArchetype m_EdgeArchetype`  
- `private Game.Simulation.WaterPipeFlowJob+Data m_FreshData`  
- `private Game.Simulation.WaterPipeFlowJob+Data m_SewageData`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections`  
- `private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  
- `private Unity.Collections.NativeList<System.Int32> m_TradeNodes`  
- `private Unity.Entities.Entity m_SourceNode`  
- `private Unity.Entities.Entity m_SinkNode`  
- `private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase`  
- `private Unity.Jobs.JobHandle m_DataDependency`  
- `private System.Boolean <ready>k__BackingField`  
- `private System.Boolean <fluidFlowEnabled>k__BackingField`  
- `private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 kUpdateInterval`  
- `public static const System.Int32 kUpdateOffset`  
- `public static const System.Int32 kUpdatesPerDay`  
- `public static const System.Int32 kStartFrames`  
- `public static const System.Int32 kAdjustFrame`  
- `public static const System.Int32 kPrepareFrame`  
- `public static const System.Int32 kFlowFrames`  
- `public static const System.Int32 kFlowCompletionFrame`  
- `public static const System.Int32 kEndFrames`  
- `public static const System.Int32 kApplyFrame`  
- `public static const System.Int32 kStatusFrame`  
- `public static const System.Int32 kMaxEdgeCapacity`  
- `private static const System.Int32 kLayerHeight`  

## Properties

- `public System.Boolean ready { get; private set }`  
- `public Unity.Entities.EntityArchetype nodeArchetype { get }`  
- `public Unity.Entities.EntityArchetype edgeArchetype { get }`  
- `public Unity.Entities.Entity sourceNode { get }`  
- `public Unity.Entities.Entity sinkNode { get }`  
- `public System.Boolean fluidFlowEnabled { get; set }`  

## Constructors

- `public WaterPipeFlowSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private ApplyPhase() : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private FlowPhase() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private PreparePhase() : System.Void`  
- `public Reset() : System.Void`  
- `private ScheduleFlowJob(Game.Simulation.WaterPipeFlowJob+Data jobData, System.Int32 importCapacity, System.Int32 exportCapacity, System.Boolean finalFrame) : Unity.Jobs.JobHandle`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.WaterPipeFlowSystem+Phase`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareNetworkJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareNodesJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareEdgesJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareConnectionsJob`  
- `Game.Simulation.WaterPipeFlowSystem+PopulateNodeIndicesJob`  
- `Game.Simulation.WaterPipeFlowSystem+ApplyEdgesJob`  
- `Game.Simulation.WaterPipeFlowSystem+TypeHandle`  


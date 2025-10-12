# Game.Simulation.ElectricityFlowSystem

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
- `private Unity.Entities.EntityArchetype m_ChargeNodeArchetype`  
- `private Unity.Entities.EntityArchetype m_DischargeNodeArchetype`  
- `private Unity.Entities.EntityArchetype m_EdgeArchetype`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.Node> m_Nodes`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.Edge> m_Edges`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections`  
- `private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  
- `private Unity.Collections.NativeList<System.Int32> m_ChargeNodes`  
- `private Unity.Collections.NativeList<System.Int32> m_DischargeNodes`  
- `private Unity.Collections.NativeList<System.Int32> m_TradeNodes`  
- `private Unity.Collections.NativeReference<Game.Simulation.ElectricityFlowJob+State> m_FlowJobState`  
- `private Unity.Collections.NativeReference<Game.Simulation.Flow.MaxFlowSolverState> m_SolverState`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.LayerState> m_LayerStates`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.CutElement> m_LayerElements`  
- `private Unity.Collections.NativeList<Game.Simulation.Flow.CutElementRef> m_LayerElementRefs`  
- `private Unity.Entities.Entity m_SourceNode`  
- `private Unity.Entities.Entity m_SinkNode`  
- `private Unity.Entities.Entity m_LegacyOutsideSourceNode`  
- `private Unity.Entities.Entity m_LegacyOutsideSinkNode`  
- `private Game.Simulation.ElectricityFlowSystem+Phase m_NextPhase`  
- `private Unity.Jobs.JobHandle m_DataDependency`  
- `private System.Boolean <ready>k__BackingField`  
- `private Game.Simulation.ElectricityFlowSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 kUpdateInterval`  
- `public static const System.Int32 kUpdatesPerDay`  
- `public static const System.Int32 kUpdatesPerHour`  
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
- `public Unity.Entities.EntityArchetype chargeNodeArchetype { get }`  
- `public Unity.Entities.EntityArchetype dischargeNodeArchetype { get }`  
- `public Unity.Entities.EntityArchetype edgeArchetype { get }`  
- `public Unity.Entities.Entity sourceNode { get }`  
- `public Unity.Entities.Entity sinkNode { get }`  

## Constructors

- `public ElectricityFlowSystem()`  

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
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.ElectricityFlowSystem+Phase`  
- `Game.Simulation.ElectricityFlowSystem+PrepareNetworkJob`  
- `Game.Simulation.ElectricityFlowSystem+PrepareNodesJob`  
- `Game.Simulation.ElectricityFlowSystem+PrepareEdgesJob`  
- `Game.Simulation.ElectricityFlowSystem+PrepareConnectionsJob`  
- `Game.Simulation.ElectricityFlowSystem+PopulateNodeIndicesJob`  
- `Game.Simulation.ElectricityFlowSystem+ApplyEdgesJob`  
- `Game.Simulation.ElectricityFlowSystem+TypeHandle`  


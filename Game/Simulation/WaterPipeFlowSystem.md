# Game.Simulation.WaterPipeFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeFlowSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityArchetype m_NodeArchetype;
    private Unity.Entities.EntityArchetype m_EdgeArchetype;
    private Game.Simulation.WaterPipeFlowJob+Data m_FreshData;
    private Game.Simulation.WaterPipeFlowJob+Data m_SewageData;
    private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections;
    private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
    private Unity.Collections.NativeList<System.Int32> m_TradeNodes;
    private Unity.Entities.Entity m_SourceNode;
    private Unity.Entities.Entity m_SinkNode;
    private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase;
    private Unity.Jobs.JobHandle m_DataDependency;
    private System.Boolean <ready>k__BackingField;
    private System.Boolean <fluidFlowEnabled>k__BackingField;
    private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdateInterval;
    public static const System.Int32 kUpdateOffset;
    public static const System.Int32 kUpdatesPerDay;
    public static const System.Int32 kStartFrames;
    public static const System.Int32 kAdjustFrame;
    public static const System.Int32 kPrepareFrame;
    public static const System.Int32 kFlowFrames;
    public static const System.Int32 kFlowCompletionFrame;
    public static const System.Int32 kEndFrames;
    public static const System.Int32 kApplyFrame;
    public static const System.Int32 kStatusFrame;
    public static const System.Int32 kMaxEdgeCapacity;
    private static const System.Int32 kLayerHeight;

    public System.Boolean ready { get; private set; }
    public Unity.Entities.EntityArchetype nodeArchetype { get; }
    public Unity.Entities.EntityArchetype edgeArchetype { get; }
    public Unity.Entities.Entity sourceNode { get; }
    public Unity.Entities.Entity sinkNode { get; }
    public System.Boolean fluidFlowEnabled { get; set; }

    public WaterPipeFlowSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ApplyPhase();
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void FlowPhase();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void PreparePhase();
    public System.Void Reset();
    private Unity.Jobs.JobHandle ScheduleFlowJob(Game.Simulation.WaterPipeFlowJob+Data jobData, System.Int32 importCapacity, System.Int32 exportCapacity, System.Boolean finalFrame);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_NodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_NodeGroup;
```

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityArchetype m_NodeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_NodeArchetype;
```

- `private Unity.Entities.EntityArchetype m_EdgeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EdgeArchetype;
```

- `private Game.Simulation.WaterPipeFlowJob+Data m_FreshData`  

```csharp
private Game.Simulation.WaterPipeFlowJob+Data m_FreshData;
```

- `private Game.Simulation.WaterPipeFlowJob+Data m_SewageData`  

```csharp
private Game.Simulation.WaterPipeFlowJob+Data m_SewageData;
```

- `private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.Flow.Connection> m_Connections;
```

- `private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices`  

```csharp
private Unity.Collections.NativeReference<Game.Simulation.Flow.NodeIndices> m_NodeIndices;
```

- `private Unity.Collections.NativeList<System.Int32> m_TradeNodes`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_TradeNodes;
```

- `private Unity.Entities.Entity m_SourceNode`  

```csharp
private Unity.Entities.Entity m_SourceNode;
```

- `private Unity.Entities.Entity m_SinkNode`  

```csharp
private Unity.Entities.Entity m_SinkNode;
```

- `private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase`  

```csharp
private Game.Simulation.WaterPipeFlowSystem+Phase m_NextPhase;
```

- `private Unity.Jobs.JobHandle m_DataDependency`  

```csharp
private Unity.Jobs.JobHandle m_DataDependency;
```

- `private System.Boolean <ready>k__BackingField`  

```csharp
private System.Boolean <ready>k__BackingField;
```

- `private System.Boolean <fluidFlowEnabled>k__BackingField`  

```csharp
private System.Boolean <fluidFlowEnabled>k__BackingField;
```

- `private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeFlowSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdateInterval`  

```csharp
public static const System.Int32 kUpdateInterval;
```

- `public static const System.Int32 kUpdateOffset`  

```csharp
public static const System.Int32 kUpdateOffset;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```

- `public static const System.Int32 kStartFrames`  

```csharp
public static const System.Int32 kStartFrames;
```

- `public static const System.Int32 kAdjustFrame`  

```csharp
public static const System.Int32 kAdjustFrame;
```

- `public static const System.Int32 kPrepareFrame`  

```csharp
public static const System.Int32 kPrepareFrame;
```

- `public static const System.Int32 kFlowFrames`  

```csharp
public static const System.Int32 kFlowFrames;
```

- `public static const System.Int32 kFlowCompletionFrame`  

```csharp
public static const System.Int32 kFlowCompletionFrame;
```

- `public static const System.Int32 kEndFrames`  

```csharp
public static const System.Int32 kEndFrames;
```

- `public static const System.Int32 kApplyFrame`  

```csharp
public static const System.Int32 kApplyFrame;
```

- `public static const System.Int32 kStatusFrame`  

```csharp
public static const System.Int32 kStatusFrame;
```

- `public static const System.Int32 kMaxEdgeCapacity`  

```csharp
public static const System.Int32 kMaxEdgeCapacity;
```

- `private static const System.Int32 kLayerHeight`  

```csharp
private static const System.Int32 kLayerHeight;
```


## Properties

- `public System.Boolean ready { get; private set }`  

```csharp
public System.Boolean ready { get; private set; }
```

- `public Unity.Entities.EntityArchetype nodeArchetype { get }`  

```csharp
public Unity.Entities.EntityArchetype nodeArchetype { get; }
```

- `public Unity.Entities.EntityArchetype edgeArchetype { get }`  

```csharp
public Unity.Entities.EntityArchetype edgeArchetype { get; }
```

- `public Unity.Entities.Entity sourceNode { get }`  

```csharp
public Unity.Entities.Entity sourceNode { get; }
```

- `public Unity.Entities.Entity sinkNode { get }`  

```csharp
public Unity.Entities.Entity sinkNode { get; }
```

- `public System.Boolean fluidFlowEnabled { get; set }`  

```csharp
public System.Boolean fluidFlowEnabled { get; set; }
```


## Constructors

- `public WaterPipeFlowSystem()`  

```csharp
public WaterPipeFlowSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private ApplyPhase() : System.Void`  

```csharp
private System.Void ApplyPhase();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private FlowPhase() : System.Void`  

```csharp
private System.Void FlowPhase();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private PreparePhase() : System.Void`  

```csharp
private System.Void PreparePhase();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `private ScheduleFlowJob(Game.Simulation.WaterPipeFlowJob+Data jobData, System.Int32 importCapacity, System.Int32 exportCapacity, System.Boolean finalFrame) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ScheduleFlowJob(Game.Simulation.WaterPipeFlowJob+Data jobData, System.Int32 importCapacity, System.Int32 exportCapacity, System.Boolean finalFrame);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.WaterPipeFlowSystem+Phase`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareNetworkJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareNodesJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareEdgesJob`  
- `Game.Simulation.WaterPipeFlowSystem+PrepareConnectionsJob`  
- `Game.Simulation.WaterPipeFlowSystem+PopulateNodeIndicesJob`  
- `Game.Simulation.WaterPipeFlowSystem+ApplyEdgesJob`  
- `Game.Simulation.WaterPipeFlowSystem+TypeHandle`  


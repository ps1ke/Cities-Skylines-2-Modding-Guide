# Game.Simulation.ElectricityTradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityTradeSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Unity.Entities.EntityQuery m_TradeNodeGroup;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Colossal.NativePerThreadSumInt m_Export;
    private Colossal.NativePerThreadSumInt m_Import;
    private System.Int32 m_LastExport;
    private System.Int32 m_LastImport;
    private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1233563293_0;

    public System.Int32 export { get; }
    public System.Int32 import { get; }

    public ElectricityTradeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Unity.Entities.EntityQuery m_TradeNodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_TradeNodeGroup;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Colossal.NativePerThreadSumInt m_Export`  

```csharp
private Colossal.NativePerThreadSumInt m_Export;
```

- `private Colossal.NativePerThreadSumInt m_Import`  

```csharp
private Colossal.NativePerThreadSumInt m_Import;
```

- `private System.Int32 m_LastExport`  

```csharp
private System.Int32 m_LastExport;
```

- `private System.Int32 m_LastImport`  

```csharp
private System.Int32 m_LastImport;
```

- `private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityTradeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1233563293_0`  

```csharp
private Unity.Entities.EntityQuery __query_1233563293_0;
```


## Properties

- `public System.Int32 export { get }`  

```csharp
public System.Int32 export { get; }
```

- `public System.Int32 import { get }`  

```csharp
public System.Int32 import { get; }
```


## Constructors

- `public ElectricityTradeSystem()`  

```csharp
[Preserve]
	public ElectricityTradeSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<OutsideTradeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1233563293_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 126;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_ServiceFeeSystem = base.World.GetOrCreateSystemManaged<ServiceFeeSystem>();
		m_TradeNodeGroup = GetEntityQuery(ComponentType.ReadOnly<TradeNode>(), ComponentType.ReadOnly<ElectricityFlowNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>());
		RequireForUpdate<OutsideTradeParameterData>();
		m_Export = new NativePerThreadSumInt(Allocator.Persistent);
		m_Import = new NativePerThreadSumInt(Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Export.Dispose();
		m_Import.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastExport = m_Export.Count;
		m_LastImport = m_Import.Count;
		m_Export.Count = 0;
		m_Import.Count = 0;
		if (!m_TradeNodeGroup.IsEmptyIgnoreFilter)
		{
			SumJob jobData = new SumJob
			{
				m_FlowConnectionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Export = m_Export.ToConcurrent(),
				m_Import = m_Import.ToConcurrent(),
				m_SourceNode = m_ElectricityFlowSystem.sourceNode,
				m_SinkNode = m_ElectricityFlowSystem.sinkNode
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TradeNodeGroup, base.Dependency);
			JobHandle deps;
			ElectricityTradeJob jobData2 = new ElectricityTradeJob
			{
				m_Export = m_Export,
				m_Import = m_Import,
				m_FeeQueue = m_ServiceFeeSystem.GetFeeQueue(out deps),
				m_OutsideTradeParameters = __query_1233563293_0.GetSingleton<OutsideTradeParameterData>()
			};
			base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, deps));
			m_ServiceFeeSystem.AddQueueWriter(base.Dependency);
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastExport = 0;
		m_LastImport = 0;
	}
```


## Nested types

- `Game.Simulation.ElectricityTradeSystem+SumJob`  
- `Game.Simulation.ElectricityTradeSystem+ElectricityTradeJob`  
- `Game.Simulation.ElectricityTradeSystem+TypeHandle`  


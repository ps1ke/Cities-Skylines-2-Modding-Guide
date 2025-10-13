# Game.Simulation.WaterTradeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterTradeSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem;
    private Unity.Entities.EntityQuery m_TradeNodeGroup;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Colossal.NativePerThreadSumInt m_FreshExport;
    private Colossal.NativePerThreadSumInt m_PollutedExport;
    private Colossal.NativePerThreadSumInt m_FreshImport;
    private Colossal.NativePerThreadSumInt m_SewageExport;
    private System.Int32 m_LastFreshExport;
    private System.Int32 m_LastFreshImport;
    private System.Int32 m_LastSewageExport;
    private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1457460959_0;

    public System.Int32 freshExport { get; }
    public System.Int32 freshImport { get; }
    public System.Int32 sewageExport { get; }

    public WaterTradeSystem();

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

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem`  

```csharp
private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_TradeNodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_TradeNodeGroup;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Colossal.NativePerThreadSumInt m_FreshExport`  

```csharp
private Colossal.NativePerThreadSumInt m_FreshExport;
```

- `private Colossal.NativePerThreadSumInt m_PollutedExport`  

```csharp
private Colossal.NativePerThreadSumInt m_PollutedExport;
```

- `private Colossal.NativePerThreadSumInt m_FreshImport`  

```csharp
private Colossal.NativePerThreadSumInt m_FreshImport;
```

- `private Colossal.NativePerThreadSumInt m_SewageExport`  

```csharp
private Colossal.NativePerThreadSumInt m_SewageExport;
```

- `private System.Int32 m_LastFreshExport`  

```csharp
private System.Int32 m_LastFreshExport;
```

- `private System.Int32 m_LastFreshImport`  

```csharp
private System.Int32 m_LastFreshImport;
```

- `private System.Int32 m_LastSewageExport`  

```csharp
private System.Int32 m_LastSewageExport;
```

- `private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterTradeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1457460959_0`  

```csharp
private Unity.Entities.EntityQuery __query_1457460959_0;
```


## Properties

- `public System.Int32 freshExport { get }`  

```csharp
public System.Int32 freshExport { get; }
```

- `public System.Int32 freshImport { get }`  

```csharp
public System.Int32 freshImport { get; }
```

- `public System.Int32 sewageExport { get }`  

```csharp
public System.Int32 sewageExport { get; }
```


## Constructors

- `public WaterTradeSystem()`  

```csharp
[Preserve]
	public WaterTradeSystem()
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
		__query_1457460959_0 = entityQueryBuilder2.Build(ref state);
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
		return 62;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_ServiceFeeSystem = base.World.GetOrCreateSystemManaged<ServiceFeeSystem>();
		m_WaterStatisticsSystem = base.World.GetOrCreateSystemManaged<WaterStatisticsSystem>();
		m_TradeNodeGroup = GetEntityQuery(ComponentType.ReadOnly<TradeNode>(), ComponentType.ReadOnly<WaterPipeNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>());
		RequireForUpdate<OutsideTradeParameterData>();
		m_FreshExport = new NativePerThreadSumInt(Allocator.Persistent);
		m_PollutedExport = new NativePerThreadSumInt(Allocator.Persistent);
		m_FreshImport = new NativePerThreadSumInt(Allocator.Persistent);
		m_SewageExport = new NativePerThreadSumInt(Allocator.Persistent);
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
		m_FreshExport.Dispose();
		m_PollutedExport.Dispose();
		m_FreshImport.Dispose();
		m_SewageExport.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastFreshExport = m_FreshExport.Count;
		m_LastFreshImport = m_FreshImport.Count;
		m_LastSewageExport = m_SewageExport.Count;
		int availableWater = m_WaterStatisticsSystem.freshCapacity - m_WaterStatisticsSystem.freshConsumption;
		m_FreshExport.Count = 0;
		m_PollutedExport.Count = 0;
		m_FreshImport.Count = 0;
		m_SewageExport.Count = 0;
		if (!m_TradeNodeGroup.IsEmptyIgnoreFilter)
		{
			OutsideTradeParameterData singleton = __query_1457460959_0.GetSingleton<OutsideTradeParameterData>();
			SumJob jobData = new SumJob
			{
				m_FlowConnectionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FreshExport = m_FreshExport.ToConcurrent(),
				m_PollutedExport = m_PollutedExport.ToConcurrent(),
				m_FreshImport = m_FreshImport.ToConcurrent(),
				m_SewageExport = m_SewageExport.ToConcurrent(),
				m_OutsideTradeParameters = singleton,
				m_SourceNode = m_WaterPipeFlowSystem.sourceNode,
				m_SinkNode = m_WaterPipeFlowSystem.sinkNode
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TradeNodeGroup, base.Dependency);
			JobHandle deps;
			WaterTradeJob jobData2 = new WaterTradeJob
			{
				m_AvailableWater = availableWater,
				m_FreshExport = m_FreshExport,
				m_PollutedExport = m_PollutedExport,
				m_FreshImport = m_FreshImport,
				m_SewageExport = m_SewageExport,
				m_FeeQueue = m_ServiceFeeSystem.GetFeeQueue(out deps),
				m_OutsideTradeParameters = singleton
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
		m_LastFreshExport = 0;
		m_LastFreshImport = 0;
		m_LastSewageExport = 0;
	}
```


## Nested types

- `Game.Simulation.WaterTradeSystem+SumJob`  
- `Game.Simulation.WaterTradeSystem+WaterTradeJob`  
- `Game.Simulation.WaterTradeSystem+TypeHandle`  


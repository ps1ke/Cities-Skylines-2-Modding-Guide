# Game.Simulation.DispatchWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DispatchWaterSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private System.Boolean <freshConsumptionDisabled>k__BackingField;
    private System.Boolean <sewageConsumptionDisabled>k__BackingField;
    private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1010455350_0;
    private Unity.Entities.EntityQuery __query_1010455350_1;
    public static readonly System.Int16 kAlertCooldown;
    public static readonly System.Int16 kHealthPenaltyCooldown;
    private static const System.Single kNotificationMaxDelay;

    public System.Boolean freshConsumptionDisabled { get; set; }
    public System.Boolean sewageConsumptionDisabled { get; set; }

    public DispatchWaterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private System.Boolean <freshConsumptionDisabled>k__BackingField`  

```csharp
private System.Boolean <freshConsumptionDisabled>k__BackingField;
```

- `private System.Boolean <sewageConsumptionDisabled>k__BackingField`  

```csharp
private System.Boolean <sewageConsumptionDisabled>k__BackingField;
```

- `private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1010455350_0`  

```csharp
private Unity.Entities.EntityQuery __query_1010455350_0;
```

- `private Unity.Entities.EntityQuery __query_1010455350_1`  

```csharp
private Unity.Entities.EntityQuery __query_1010455350_1;
```

- `public static readonly System.Int16 kAlertCooldown`  

```csharp
public static readonly System.Int16 kAlertCooldown;
```

- `public static readonly System.Int16 kHealthPenaltyCooldown`  

```csharp
public static readonly System.Int16 kHealthPenaltyCooldown;
```

- `private static const System.Single kNotificationMaxDelay`  

```csharp
private static const System.Single kNotificationMaxDelay;
```


## Properties

- `public System.Boolean freshConsumptionDisabled { get; set }`  

```csharp
public System.Boolean freshConsumptionDisabled { get; set; }
```

- `public System.Boolean sewageConsumptionDisabled { get; set }`  

```csharp
public System.Boolean sewageConsumptionDisabled { get; set; }
```


## Constructors

- `public DispatchWaterSystem()`  

```csharp
[Preserve]
	public DispatchWaterSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<WaterPipeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1010455350_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1010455350_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
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
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_ConsumerQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadWrite<WaterConsumer>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_ConsumerQuery);
		RequireForUpdate<WaterPipeParameterData>();
		RequireForUpdate<BuildingEfficiencyParameterData>();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_WaterPipeFlowSystem.ready)
		{
			DispatchWaterJob jobData = new DispatchWaterJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterConsumer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_NodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
				m_Parameters = __query_1010455350_0.GetSingleton<WaterPipeParameterData>(),
				m_EfficiencyParameters = __query_1010455350_1.GetSingleton<BuildingEfficiencyParameterData>(),
				m_SinkNode = m_WaterPipeFlowSystem.sinkNode,
				m_RandomSeed = RandomSeed.Next(),
				m_FreshConsumptionDisabled = freshConsumptionDisabled,
				m_SewageConsumptionDisabled = sewageConsumptionDisabled
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ConsumerQuery, base.Dependency);
			m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.DispatchWaterSystem+DispatchWaterJob`  
- `Game.Simulation.DispatchWaterSystem+TypeHandle`  


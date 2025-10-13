# Game.Simulation.DispatchElectricitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DispatchElectricitySystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2129007938_0;
    private Unity.Entities.EntityQuery __query_2129007938_1;
    public static readonly System.Int16 kAlertCooldown;

    public DispatchElectricitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2129007938_0`  

```csharp
private Unity.Entities.EntityQuery __query_2129007938_0;
```

- `private Unity.Entities.EntityQuery __query_2129007938_1`  

```csharp
private Unity.Entities.EntityQuery __query_2129007938_1;
```

- `public static readonly System.Int16 kAlertCooldown`  

```csharp
public static readonly System.Int16 kAlertCooldown;
```


## Constructors

- `public DispatchElectricitySystem()`  

```csharp
[Preserve]
	public DispatchElectricitySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ElectricityParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2129007938_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2129007938_1 = entityQueryBuilder2.Build(ref state);
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
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_ConsumerQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ElectricityConsumer>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_ConsumerQuery);
		RequireForUpdate<ElectricityParameterData>();
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
		if (m_ElectricityFlowSystem.ready)
		{
			DispatchElectricityJob jobData = new DispatchElectricityJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_NodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
				m_Parameters = __query_2129007938_0.GetSingleton<ElectricityParameterData>(),
				m_EfficiencyParameters = __query_2129007938_1.GetSingleton<BuildingEfficiencyParameterData>(),
				m_SinkNode = m_ElectricityFlowSystem.sinkNode
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ConsumerQuery, base.Dependency);
			m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.DispatchElectricitySystem+DispatchElectricityJob`  
- `Game.Simulation.DispatchElectricitySystem+TypeHandle`  


# Game.Simulation.WaterPipePollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipePollutionSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdateInterval;

    public WaterPipePollutionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdateInterval`  

```csharp
private static const System.Int32 kUpdateInterval;
```


## Constructors

- `public WaterPipePollutionSystem()`  

```csharp
[Preserve]
	public WaterPipePollutionSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_NodeQuery = GetEntityQuery(ComponentType.ReadWrite<WaterPipeNode>(), ComponentType.ReadOnly<ConnectedFlowEdge>(), ComponentType.Exclude<Deleted>());
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadWrite<WaterPipeEdge>(), ComponentType.Exclude<Deleted>());
		m_ParameterQuery = GetEntityQuery(ComponentType.ReadOnly<WaterPipeParameterData>());
		RequireForUpdate(m_NodeQuery);
		RequireForUpdate(m_EdgeQuery);
		RequireForUpdate(m_ParameterQuery);
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
		WaterPipeParameterData singleton = m_ParameterQuery.GetSingleton<WaterPipeParameterData>();
		bool purify = m_SimulationSystem.frameIndex / 64 % singleton.m_WaterPipePollutionSpreadInterval != 0;
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(new NodePollutionJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_FlowConnectionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeNode_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StaleWaterPipePurification = singleton.m_StaleWaterPipePurification
		}, m_NodeQuery, base.Dependency);
		EdgePollutionJob jobData = new EdgePollutionJob
		{
			m_FlowEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FlowNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNode_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SourceNode = m_WaterPipeFlowSystem.sourceNode,
			m_Purify = purify
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_EdgeQuery, dependsOn);
	}
```


## Nested types

- `Game.Simulation.WaterPipePollutionSystem+NodePollutionJob`  
- `Game.Simulation.WaterPipePollutionSystem+EdgePollutionJob`  
- `Game.Simulation.WaterPipePollutionSystem+TypeHandle`  


# Game.Simulation.WaterPipeGraphDeleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeGraphDeleteSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedConnectionQuery;
    private Unity.Entities.EntityQuery m_DeletedValveNodeQuery;
    private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle;

    public WaterPipeGraphDeleteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedValveNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedValveNodeQuery;
```

- `private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeGraphDeleteSystem()`  

```csharp
[Preserve]
	public WaterPipeGraphDeleteSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_DeletedConnectionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<WaterPipeNodeConnection>(),
				ComponentType.ReadOnly<WaterPipeValveConnection>(),
				ComponentType.ReadOnly<WaterPipeBuildingConnection>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_DeletedValveNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<WaterPipeValveConnection>(),
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireAnyForUpdate(m_DeletedConnectionQuery, m_DeletedValveNodeQuery);
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
		JobHandle jobHandle = default(JobHandle);
		if (!m_DeletedConnectionQuery.IsEmptyIgnoreFilter)
		{
			jobHandle = JobChunkExtensions.ScheduleParallel(new DeleteConnectionsJob
			{
				m_NodeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ValveConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeValveConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_DeletedConnectionQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		}
		JobHandle jobHandle2 = default(JobHandle);
		if (!m_DeletedValveNodeQuery.IsEmptyIgnoreFilter)
		{
			jobHandle2 = JobChunkExtensions.ScheduleParallel(new DeleteValveNodesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ValveConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeValveConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_DeletedValveNodeQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		}
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2);
	}
```


## Nested types

- `Game.Simulation.WaterPipeGraphDeleteSystem+DeleteConnectionsJob`  
- `Game.Simulation.WaterPipeGraphDeleteSystem+DeleteValveNodesJob`  
- `Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle`  


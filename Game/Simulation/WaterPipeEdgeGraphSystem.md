# Game.Simulation.WaterPipeEdgeGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeEdgeGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedEdgeQuery;
    private Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeEdgeGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEdgeQuery;
```

- `private Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeEdgeGraphSystem()`  

```csharp
[Preserve]
	public WaterPipeEdgeGraphSystem()
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
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2B>();
		m_CreatedEdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.WaterPipeConnection>(), ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CreatedEdgeQuery);
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
		NativeParallelHashMap<Entity, Entity> nodeMap = new NativeParallelHashMap<Entity, Entity>(32, Allocator.TempJob);
		CreateEdgeConnectionsJob jobData = new CreateEdgeConnectionsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NetEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedNetNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedNetEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPipeConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_NodeMap = nodeMap,
			m_NodeArchetype = m_WaterPipeFlowSystem.nodeArchetype,
			m_EdgeArchetype = m_WaterPipeFlowSystem.edgeArchetype
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_CreatedEdgeQuery, base.Dependency);
		nodeMap.Dispose(base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.WaterPipeEdgeGraphSystem+CreateEdgeConnectionsJob`  
- `Game.Simulation.WaterPipeEdgeGraphSystem+TypeHandle`  


# Game.Simulation.WaterPipeBuildingGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeBuildingGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
    private Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeBuildingGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
```

- `private Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeBuildingGraphSystem()`  

```csharp
[Preserve]
	public WaterPipeBuildingGraphSystem()
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

- `internal static <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all) : Unity.Entities.EntityQueryDesc`  

```csharp
internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WaterPipeRoadConnectionGraphSystem = base.World.GetOrCreateSystemManaged<WaterPipeRoadConnectionGraphSystem>();
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_UpdatedBuildingQuery = GetEntityQuery(CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.WaterPumpingStation>() }), CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.SewageOutlet>() }), CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<WaterPipeBuildingConnection>() }));
		RequireForUpdate(m_UpdatedBuildingQuery);
		static EntityQueryDesc CreatedUpdatedBuildingDesc(ComponentType[] all)
		{
			return new EntityQueryDesc
			{
				All = all.Concat(new ComponentType[1] { ComponentType.ReadOnly<Building>() }).ToArray(),
				Any = new ComponentType[2]
				{
					ComponentType.ReadOnly<Created>(),
					ComponentType.ReadOnly<Updated>()
				},
				None = new ComponentType[2]
				{
					ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
					ComponentType.ReadOnly<Temp>()
				}
			};
		}
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
		JobHandle deps;
		UpdateBuildingConnectionsJob jobData = new UpdateBuildingConnectionsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PumpingStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPumpingStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SewageOutletType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_SewageOutlet_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetOrphans = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedNetEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_Deleted = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPipeConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeValveConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeValveConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_UpdatedRoadEdges = m_WaterPipeRoadConnectionGraphSystem.GetEdgeUpdateQueue(out deps).AsParallelWriter(),
			m_NodeArchetype = m_WaterPipeFlowSystem.nodeArchetype,
			m_EdgeArchetype = m_WaterPipeFlowSystem.edgeArchetype,
			m_SourceNode = m_WaterPipeFlowSystem.sourceNode,
			m_SinkNode = m_WaterPipeFlowSystem.sinkNode
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_UpdatedBuildingQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		m_WaterPipeRoadConnectionGraphSystem.AddQueueWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.WaterPipeBuildingGraphSystem+UpdateBuildingConnectionsJob`  
- `Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle`  


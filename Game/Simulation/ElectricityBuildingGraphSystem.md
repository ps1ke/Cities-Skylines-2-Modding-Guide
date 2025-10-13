# Game.Simulation.ElectricityBuildingGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityBuildingGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
    private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle;

    public ElectricityBuildingGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
```

- `private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityBuildingGraphSystem()`  

```csharp
[Preserve]
	public ElectricityBuildingGraphSystem()
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
		m_ElectricityRoadConnectionGraphSystem = base.World.GetOrCreateSystemManaged<ElectricityRoadConnectionGraphSystem>();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_UpdatedBuildingQuery = GetEntityQuery(CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<ElectricityProducer>() }), CreatedUpdatedBuildingDesc(new ComponentType[2]
		{
			ComponentType.ReadOnly<ElectricityConsumer>(),
			ComponentType.ReadOnly<Game.Net.SubNet>()
		}), CreatedUpdatedBuildingDesc(new ComponentType[2]
		{
			ComponentType.ReadOnly<ElectricityConsumer>(),
			ComponentType.ReadOnly<InstalledUpgrade>()
		}), CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.Battery>() }), CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.Transformer>() }), CreatedUpdatedBuildingDesc(new ComponentType[1] { ComponentType.ReadOnly<ElectricityBuildingConnection>() }));
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
			m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Transformer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BatteryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Battery_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetOrphans = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedNetEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_Deleted = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ElectricityConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityValveConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityValveConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_UpdatedRoadEdges = m_ElectricityRoadConnectionGraphSystem.GetEdgeUpdateQueue(out deps).AsParallelWriter(),
			m_NodeArchetype = m_ElectricityFlowSystem.nodeArchetype,
			m_ChargeNodeArchetype = m_ElectricityFlowSystem.chargeNodeArchetype,
			m_DischargeNodeArchetype = m_ElectricityFlowSystem.dischargeNodeArchetype,
			m_EdgeArchetype = m_ElectricityFlowSystem.edgeArchetype,
			m_SourceNode = m_ElectricityFlowSystem.sourceNode,
			m_SinkNode = m_ElectricityFlowSystem.sinkNode
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_UpdatedBuildingQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		m_ElectricityRoadConnectionGraphSystem.AddQueueWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ElectricityBuildingGraphSystem+UpdateBuildingConnectionsJob`  
- `Game.Simulation.ElectricityBuildingGraphSystem+TypeHandle`  


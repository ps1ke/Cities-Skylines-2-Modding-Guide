# Game.Tools.ApplyNetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyNetSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes;
    private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes;
    private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes;
    private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle;

    public ApplyNetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes;
```

- `private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyNetSystem()`  

```csharp
[Preserve]
	public ApplyNetSystem()
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
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TempQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Temp>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Lane>(),
				ComponentType.ReadOnly<Aggregate>()
			},
			None = new ComponentType[0]
		});
		m_ApplyCreatedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		m_ApplyUpdatedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Updated>());
		m_ApplyDeletedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Deleted>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		RequireForUpdate(m_TempQuery);
		RequireForUpdate(m_EconomyParameterQuery);
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
		PatchTempReferencesJob jobData = new PatchTempReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RW_BufferLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RW_BufferLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RW_BufferLookup, ref base.CheckedStateRef)
		};
		FixConnectedEdgesJob jobData2 = new FixConnectedEdgesJob
		{
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RW_BufferLookup, ref base.CheckedStateRef)
		};
		HandleTempEntitiesJob jobData3 = new HandleTempEntitiesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetNodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetEdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LandValueData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LocalConnect_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TramTrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TramTrack_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainTrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrainTrack_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Waterway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Pollution_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficLightsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrafficLights_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AggregatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Aggregated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StandaloneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Standalone_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MarkerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Marker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RecentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Recent_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_EconomyParameterData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_ApplyCreatedTypes = m_ApplyCreatedTypes,
			m_ApplyUpdatedTypes = m_ApplyUpdatedTypes,
			m_ApplyDeletedTypes = m_ApplyDeletedTypes,
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle dependsOn = JobChunkExtensions.Schedule(jobData, m_TempQuery, base.Dependency);
		JobHandle job = JobChunkExtensions.ScheduleParallel(jobData2, m_TempQuery, dependsOn);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData3, m_TempQuery, dependsOn);
		base.Dependency = JobHandle.CombineDependencies(job, jobHandle);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
	}
```


## Nested types

- `Game.Tools.ApplyNetSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyNetSystem+FixConnectedEdgesJob`  
- `Game.Tools.ApplyNetSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyNetSystem+TypeHandle`  


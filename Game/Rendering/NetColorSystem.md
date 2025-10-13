# Game.Rendering.NetColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetColorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1733354667_0;

    public NetColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  

```csharp
private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1733354667_0`  

```csharp
private Unity.Entities.EntityQuery __query_1733354667_0;
```


## Constructors

- `public NetColorSystem()`  

```csharp
[Preserve]
	public NetColorSystem()
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
		__query_1733354667_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ZoneToolSystem = base.World.GetOrCreateSystemManaged<ZoneToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_IndustrialDemandSystem = base.World.GetOrCreateSystemManaged<IndustrialDemandSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_ZonePreferenceParameterGroup = GetEntityQuery(ComponentType.ReadOnly<ZonePreferenceData>());
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadWrite<EdgeColor>(), ComponentType.Exclude<Deleted>());
		m_NodeQuery = GetEntityQuery(ComponentType.ReadOnly<Node>(), ComponentType.ReadWrite<NodeColor>(), ComponentType.Exclude<Deleted>());
		m_LaneQuery = GetEntityQuery(ComponentType.ReadOnly<Lane>(), ComponentType.ReadWrite<LaneColor>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_InfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<InfomodeActive>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<InfoviewCoverageData>(),
				ComponentType.ReadOnly<InfoviewAvailabilityData>(),
				ComponentType.ReadOnly<InfoviewNetGeometryData>(),
				ComponentType.ReadOnly<InfoviewNetStatusData>()
			},
			None = new ComponentType[0]
		});
		m_ProcessQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>());
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
		if (m_ToolSystem.activeInfoview == null || (m_EdgeQuery.IsEmptyIgnoreFilter && m_NodeQuery.IsEmptyIgnoreFilter))
		{
			return;
		}
		ZonePreferenceData zonePreferences = ((m_ZonePreferenceParameterGroup.CalculateEntityCount() > 0) ? m_ZonePreferenceParameterGroup.GetSingleton<ZonePreferenceData>() : default(ZonePreferenceData));
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> infomodeChunks = m_InfomodeQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle);
		Entity zonePrefab = Entity.Null;
		if (m_ToolSystem.activeTool == m_ZoneToolSystem && m_ZoneToolSystem.prefab != null)
		{
			zonePrefab = m_PrefabSystem.GetEntity(m_ZoneToolSystem.prefab);
		}
		else if (m_ToolSystem.activeTool == m_ObjectToolSystem && m_ObjectToolSystem.prefab != null)
		{
			PlaceholderBuilding component2;
			if (m_ObjectToolSystem.prefab.TryGet<SignatureBuilding>(out var component) && component.m_ZoneType != null)
			{
				zonePrefab = m_PrefabSystem.GetEntity(component.m_ZoneType);
			}
			else if (m_ObjectToolSystem.prefab.TryGet<PlaceholderBuilding>(out component2) && component2.m_ZoneType != null)
			{
				zonePrefab = m_PrefabSystem.GetEntity(component2.m_ZoneType);
			}
		}
		JobHandle dependencies;
		JobHandle deps;
		JobHandle deps2;
		JobHandle outJobHandle2;
		UpdateEdgeColorsJob jobData = new UpdateEdgeColorsJob
		{
			m_InfomodeChunks = infomodeChunks,
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfomodeActiveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewCoverageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewCoverageData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewAvailabilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewAvailabilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrainTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TramTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TramTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterwayType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Waterway_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubwayTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SubwayTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NetCondition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PollutionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Pollution_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceCoverageType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourceAvailabilityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Temps = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZonePropertiesDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPathwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathwayData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProcessEstimates = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_ProcessEstimate_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceCoverageData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceAvailabilityData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ColorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeColor_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZonePrefab = zonePrefab,
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_IndustrialDemands = m_IndustrialDemandSystem.GetBuildingDemands(out deps),
			m_StorageDemands = m_IndustrialDemandSystem.GetStorageBuildingDemands(out deps2),
			m_Processes = m_ProcessQuery.ToComponentDataListAsync<IndustrialProcessData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
			m_ZonePreferences = zonePreferences
		};
		UpdateNodeColorsJob jobData2 = new UpdateNodeColorsJob
		{
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_InfomodeChunks = infomodeChunks,
			m_InfomodeActiveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrainTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TramTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TramTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterwayType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Waterway_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubwayTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SubwayTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NetCondition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PollutionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Pollution_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ColorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeColor_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		UpdateEdgeColors2Job jobData3 = new UpdateEdgeColors2Job
		{
			m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StartNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EndNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ColorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeColor_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		LaneColorJob jobData4 = new LaneColorJob
		{
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SecondaryLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeMappingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeMapping_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ColorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneColor_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubFlowType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubFlow_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_InfomodeChunks = infomodeChunks,
			m_InfomodeActiveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityNodeConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityFlowEdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityBuildingConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeNodeConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeEdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPipeBuildingConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeBuildingConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedBuildings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_ConnectedBuilding_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedFlowEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_ElectricitySinkNode = m_ElectricityFlowSystem.sinkNode,
			m_WaterSinkNode = m_WaterPipeFlowSystem.sinkNode,
			m_WaterPipeParameters = __query_1733354667_0.GetSingleton<WaterPipeParameterData>()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_EdgeQuery, JobUtils.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2, dependencies, deps, deps2));
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(jobData2, m_NodeQuery, jobHandle), jobData: jobData3, query: m_EdgeQuery), jobData: jobData4, query: m_LaneQuery);
		infomodeChunks.Dispose(jobHandle2);
		m_GroundPollutionSystem.AddReader(jobHandle);
		m_IndustrialDemandSystem.AddReader(jobHandle);
		m_ResourceSystem.AddPrefabsReader(jobHandle);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Rendering.NetColorSystem+UpdateEdgeColorsJob`  
- `Game.Rendering.NetColorSystem+UpdateNodeColorsJob`  
- `Game.Rendering.NetColorSystem+UpdateEdgeColors2Job`  
- `Game.Rendering.NetColorSystem+LaneColorJob`  
- `Game.Rendering.NetColorSystem+TypeHandle`  


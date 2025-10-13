# Game.Tools.TrafficRoutesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficRoutesSystem : Game.GameSystemBase
{
    private System.Boolean <routesVisible>k__BackingField;
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_LivePathQuery;
    private Unity.Entities.EntityQuery m_PathSourceQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private System.Int32 m_UpdateFrameIndex;
    private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle;

    public System.Boolean routesVisible { get; set; }

    public TrafficRoutesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <routesVisible>k__BackingField`  

```csharp
private System.Boolean <routesVisible>k__BackingField;
```

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_LivePathQuery`  

```csharp
private Unity.Entities.EntityQuery m_LivePathQuery;
```

- `private Unity.Entities.EntityQuery m_PathSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathSourceQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private System.Int32 m_UpdateFrameIndex`  

```csharp
private System.Int32 m_UpdateFrameIndex;
```

- `private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean routesVisible { get; set }`  

```csharp
public System.Boolean routesVisible { get; set; }
```


## Constructors

- `public TrafficRoutesSystem()`  

```csharp
[Preserve]
	public TrafficRoutesSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_LivePathQuery = GetEntityQuery(ComponentType.ReadOnly<LivePath>(), ComponentType.ReadOnly<Route>(), ComponentType.Exclude<Deleted>());
		m_PathSourceQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<UpdateFrame>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<PathOwner>(),
				ComponentType.ReadOnly<TrainCurrentLane>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_RouteConfigQuery = GetEntityQuery(ComponentType.ReadOnly<RouteConfigurationData>());
		m_UpdateFrameIndex = -1;
		routesVisible = false;
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
		Entity entity = (routesVisible ? m_ToolSystem.selected : Entity.Null);
		if (entity == Entity.Null && m_LivePathQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> livePathChunks = m_LivePathQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		NativeQueue<Entity> pathSourceQueue = default(NativeQueue<Entity>);
		JobHandle jobHandle = base.Dependency;
		if (base.EntityManager.HasComponent<Building>(entity) || base.EntityManager.HasComponent<Aggregate>(entity) || base.EntityManager.HasComponent<Game.Net.Node>(entity) || base.EntityManager.HasComponent<Game.Net.Edge>(entity) || base.EntityManager.HasComponent<Game.Routes.TransportStop>(entity) || base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(entity))
		{
			NativeHashSet<Entity> targetMap = new NativeHashSet<Entity>(100, Allocator.TempJob);
			pathSourceQueue = new NativeQueue<Entity>(Allocator.TempJob);
			if (++m_UpdateFrameIndex == 16)
			{
				m_UpdateFrameIndex = 0;
			}
			m_PathSourceQuery.ResetFilter();
			m_PathSourceQuery.AddSharedComponentFilter(new UpdateFrame((uint)m_UpdateFrameIndex));
			FillTargetMapJob jobData = new FillTargetMapJob
			{
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_SpawnLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_SpawnLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_AggregateElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_AggregateElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedRoutes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
				m_SelectedEntity = entity,
				m_SelectedIndex = m_ToolSystem.selectedIndex,
				m_TargetMap = targetMap
			};
			JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new FindPathSourcesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HumanCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WatercraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AircraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrainCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransformFrames = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_CarNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_CarNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_WatercraftNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_AircraftNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_AircraftNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TrainNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TargetMap = targetMap,
				m_PathSourceQueue = pathSourceQueue.AsParallelWriter()
			}, dependsOn: IJobExtensions.Schedule(jobData, jobHandle), query: m_PathSourceQuery);
			targetMap.Dispose(jobHandle2);
			jobHandle = jobHandle2;
		}
		else
		{
			m_UpdateFrameIndex = -1;
		}
		JobHandle jobHandle3 = IJobExtensions.Schedule(new UpdateLivePathsJob
		{
			m_LivePathChunks = livePathChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteSegmentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteSegment_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_PathSourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathSource_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Watercraft_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Aircraft_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Passengers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_SelectedEntity = entity,
			m_UpdateFrameIndex = m_UpdateFrameIndex,
			m_SourceCountLimit = 200,
			m_RouteConfigurationData = m_RouteConfigQuery.GetSingleton<RouteConfigurationData>(),
			m_PathSourceQueue = pathSourceQueue,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(outJobHandle, jobHandle));
		livePathChunks.Dispose(jobHandle3);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle3);
		if (pathSourceQueue.IsCreated)
		{
			pathSourceQueue.Dispose(jobHandle3);
		}
		base.Dependency = jobHandle3;
	}
```


## Nested types

- `Game.Tools.TrafficRoutesSystem+LivePathEntityData`  
- `Game.Tools.TrafficRoutesSystem+FillTargetMapJob`  
- `Game.Tools.TrafficRoutesSystem+FindPathSourcesJob`  
- `Game.Tools.TrafficRoutesSystem+UpdateLivePathsJob`  
- `Game.Tools.TrafficRoutesSystem+TypeHandle`  


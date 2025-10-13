# Game.Routes.SegmentCurveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SegmentCurveSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
    private Unity.Entities.EntityQuery m_AllRoutesQuery;
    private System.Boolean m_Loaded;
    private Game.Routes.SegmentCurveSystem+TypeHandle __TypeHandle;

    public SegmentCurveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllRoutesQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Routes.SegmentCurveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.SegmentCurveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SegmentCurveSystem()`  

```csharp
[Preserve]
	public SegmentCurveSystem()
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

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdatedRoutesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Segment>(),
				ComponentType.ReadOnly<CurveElement>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<LivePath>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Common.Event>(),
				ComponentType.ReadOnly<PathUpdated>()
			}
		});
		m_AllRoutesQuery = GetEntityQuery(ComponentType.ReadOnly<Segment>(), ComponentType.ReadOnly<CurveElement>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery entityQuery = (GetLoaded() ? m_AllRoutesQuery : m_UpdatedRoutesQuery);
		if (!entityQuery.IsEmptyIgnoreFilter)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> chunks = entityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			FindUpdatedSegmentsJob jobData = new FindUpdatedSegmentsJob
			{
				m_Chunks = chunks,
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PathUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_CurveElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_SegmentList = nativeList
			};
			JobHandle jobHandle = new UpdateSegmentCurvesJob
			{
				m_SegmentList = nativeList.AsDeferredJobArray(),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SegmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathTargetsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathTargets_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathSourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathSource_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathOwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WatercraftCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AircraftCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrainCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PersonalCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AircraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Aircraft_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GroupMemberData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HumanCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CarNavigationLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_CarNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_WatercraftNavigationLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_AircraftNavigationLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_AircraftNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_TrainNavigationLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CurveElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_CurveElement_RW_BufferLookup, ref base.CheckedStateRef),
				m_CurveSources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_CurveSource_RW_BufferLookup, ref base.CheckedStateRef)
			}.Schedule(dependsOn: IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle)), list: nativeList, innerloopBatchCount: 1);
			nativeList.Dispose(jobHandle);
			chunks.Dispose(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Routes.SegmentCurveSystem+FindUpdatedSegmentsJob`  
- `Game.Routes.SegmentCurveSystem+UpdateSegmentCurvesJob`  
- `Game.Routes.SegmentCurveSystem+TypeHandle`  


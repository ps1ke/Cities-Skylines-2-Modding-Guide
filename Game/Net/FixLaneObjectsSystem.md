# Game.Net.FixLaneObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FixLaneObjectsSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle;

    public FixLaneObjectsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FixLaneObjectsSystem()`  

```csharp
[Preserve]
	public FixLaneObjectsSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_LaneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<LaneObject>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<ParkingLane>()
			}
		});
		m_LaneObjectUpdater = new LaneObjectUpdater(this);
		RequireForUpdate(m_LaneQuery);
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
		NativeQueue<Entity> laneObjectQueue = new NativeQueue<Entity>(Allocator.TempJob);
		CollectLaneObjectsJob jobData = new CollectLaneObjectsJob
		{
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarTrailerLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarTrailerLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneObject_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_LaneObjectQueue = laneObjectQueue.AsParallelWriter()
		};
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		FixLaneObjectsJob jobData2 = new FixLaneObjectsJob
		{
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarNavigationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanNavigationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalNavigationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftNavigationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftNavigationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutOfControlData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_OutOfControl_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HelicopterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Helicopter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HangaroundLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_HangaroundLocation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
			m_CarCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CarTrailerLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarTrailerLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HumanCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TrainCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_BlockedLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_BlockedLane_RW_BufferLookup, ref base.CheckedStateRef),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies2),
			m_StaticObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies3),
			m_MovingObjectSearchTree = m_ObjectSearchSystem.GetMovingSearchTree(readOnly: true, out dependencies4),
			m_LaneObjectQueue = laneObjectQueue,
			m_LaneObjectBuffer = m_LaneObjectUpdater.Begin(Allocator.TempJob)
		};
		JobHandle job = JobChunkExtensions.ScheduleParallel(jobData, m_LaneQuery, base.Dependency);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(job, dependencies2, JobHandle.CombineDependencies(dependencies, dependencies3, dependencies4)));
		laneObjectQueue.Dispose(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_ObjectSearchSystem.AddMovingSearchTreeReader(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		JobHandle dependency = m_LaneObjectUpdater.Apply(this, jobHandle);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Net.FixLaneObjectsSystem+CollectLaneObjectsJob`  
- `Game.Net.FixLaneObjectsSystem+FixLaneObjectsJob`  
- `Game.Net.FixLaneObjectsSystem+TypeHandle`  


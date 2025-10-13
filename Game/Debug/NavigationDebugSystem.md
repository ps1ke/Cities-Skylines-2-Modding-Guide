# Game.Debug.NavigationDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NavigationDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_NavigationQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Debug.BaseDebugSystem+Option m_HumanOption;
    private Game.Debug.BaseDebugSystem+Option m_AnimalOption;
    private Game.Debug.BaseDebugSystem+Option m_CarOption;
    private Game.Debug.BaseDebugSystem+Option m_TrainOption;
    private Game.Debug.BaseDebugSystem+Option m_WatercraftOption;
    private Game.Debug.BaseDebugSystem+Option m_AircraftOption;
    private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle;

    public NavigationDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle DrawNavigationGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle DrawSelectedGizmos(Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NavigationQuery`  

```csharp
private Unity.Entities.EntityQuery m_NavigationQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_HumanOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_HumanOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AnimalOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AnimalOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CarOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CarOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_TrainOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_TrainOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_WatercraftOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_WatercraftOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AircraftOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AircraftOption;
```

- `private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NavigationDebugSystem()`  

```csharp
[Preserve]
	public NavigationDebugSystem()
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

- `private DrawNavigationGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle DrawNavigationGizmos(EntityQuery group, JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new NavigationGizmoJob
		{
			m_HumanOption = m_HumanOption.enabled,
			m_AnimalOption = m_AnimalOption.enabled,
			m_CarOption = m_CarOption.enabled,
			m_TrainOption = m_TrainOption.enabled,
			m_WatercraftOption = m_WatercraftOption.enabled,
			m_AircraftOption = m_AircraftOption.enabled,
			m_TimeOffset = UnityEngine.Time.realtimeSinceStartup,
			m_Selected = m_ToolSystem.selected,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CarCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_CarNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_WatercraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WatercraftNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_AircraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AircraftNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_AircraftNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TrainType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_HumanCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimalCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, group, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `private DrawSelectedGizmos(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle DrawSelectedGizmos(JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = IJobExtensions.Schedule(new SelectedNavigationGizmoJob
		{
			m_Selected = m_ToolSystem.selected,
			m_CarCurrentLaneType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarNavigationLaneType = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_CarNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_CarNavigationType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftCurrentLaneType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftNavigationLaneType = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_WatercraftNavigationType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftCurrentLaneType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftNavigationLaneType = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_AircraftNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_AircraftNavigationType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftNavigation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainCurrentLaneType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainNavigationLaneType = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElementType = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_BlockerType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Blocker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanCurrentLaneType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalCurrentLaneType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedType = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneReservationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneReservation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneCondition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneSignalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneSignal_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_AreaLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WatercraftDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Watercraft_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AircraftDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Aircraft_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrainCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWatercraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WatercraftData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAircraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AircraftData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneOverlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_SimulationFrame = m_SimulationSystem.frameIndex
		}, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NavigationQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.Object>(),
				ComponentType.ReadOnly<Moving>()
			},
			Any = new ComponentType[6]
			{
				ComponentType.ReadOnly<CarCurrentLane>(),
				ComponentType.ReadOnly<TrainCurrentLane>(),
				ComponentType.ReadOnly<HumanCurrentLane>(),
				ComponentType.ReadOnly<WatercraftCurrentLane>(),
				ComponentType.ReadOnly<AircraftCurrentLane>(),
				ComponentType.ReadOnly<AnimalCurrentLane>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_HumanOption = AddOption("Humans", defaultEnabled: true);
		m_AnimalOption = AddOption("Animals", defaultEnabled: true);
		m_CarOption = AddOption("Cars", defaultEnabled: true);
		m_TrainOption = AddOption("Trains", defaultEnabled: true);
		m_WatercraftOption = AddOption("Ships", defaultEnabled: true);
		m_AircraftOption = AddOption("Aircrafts", defaultEnabled: true);
		base.Enabled = false;
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
		if (!m_NavigationQuery.IsEmptyIgnoreFilter)
		{
			if (m_ToolSystem.selected != Entity.Null)
			{
				base.Dependency = JobHandle.CombineDependencies(DrawNavigationGizmos(m_NavigationQuery, base.Dependency), DrawSelectedGizmos(base.Dependency));
			}
			else
			{
				base.Dependency = DrawNavigationGizmos(m_NavigationQuery, base.Dependency);
			}
		}
	}
```


## Nested types

- `Game.Debug.NavigationDebugSystem+NavigationGizmoJob`  
- `Game.Debug.NavigationDebugSystem+SelectedNavigationGizmoJob`  
- `Game.Debug.NavigationDebugSystem+TypeHandle`  


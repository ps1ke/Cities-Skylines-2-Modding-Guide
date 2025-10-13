# Game.Simulation.AnimalNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimalNavigationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.AnimalNavigationSystem+Actions m_Actions;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Game.Simulation.AnimalNavigationSystem+TypeHandle __TypeHandle;

    public AnimalNavigationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
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

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.AnimalNavigationSystem+Actions m_Actions`  

```csharp
private Game.Simulation.AnimalNavigationSystem+Actions m_Actions;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Game.Simulation.AnimalNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AnimalNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimalNavigationSystem()`  

```csharp
[Preserve]
	public AnimalNavigationSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_Actions = base.World.GetOrCreateSystemManaged<Actions>();
		m_CreatureQuery = GetEntityQuery(ComponentType.ReadOnly<Animal>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<AnimalCurrentLane>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
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
		uint num = m_SimulationSystem.frameIndex % 16;
		if (num == 5 || num == 9 || num == 13)
		{
			m_CreatureQuery.ResetFilter();
			m_CreatureQuery.SetSharedComponentFilter(new UpdateFrame(num));
			JobHandle deps;
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle dependencies3;
			JobHandle dependencies4;
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateNavigationJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MovingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_GroupMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StumblingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Stumbling_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TripSourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_TripSource_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AnimalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Animal_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MeshGroupType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_NavigationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalNavigation_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BlockerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Blocker_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HumanCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneReservationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneReservation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_AreaLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TaxiStandData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TaxiStand_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AnimalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Animal_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GroupMemberData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HangaroundLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_HangaroundLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathOwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CreatureData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAnimalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AnimalData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_LaneOverlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabActivityLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
				m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_AnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
				m_AnimationMotions = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationMotion_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
				m_AnimalCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_RandomSeed = RandomSeed.Next(),
				m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
				m_StaticObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
				m_MovingObjectSearchTree = m_ObjectSearchSystem.GetMovingSearchTree(readOnly: true, out dependencies3),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies4),
				m_LaneObjectBuffer = m_Actions.m_LaneObjectUpdater.Begin(Allocator.TempJob)
			}, m_CreatureQuery, JobUtils.CombineDependencies(base.Dependency, dependencies, dependencies2, dependencies3, dependencies4, deps));
			m_TerrainSystem.AddCPUHeightReader(jobHandle);
			m_WaterSystem.AddSurfaceReader(jobHandle);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
			m_ObjectSearchSystem.AddMovingSearchTreeReader(jobHandle);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
			m_Actions.m_Dependency = jobHandle;
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Simulation.AnimalNavigationSystem+Groups`  
- `Game.Simulation.AnimalNavigationSystem+Actions`  
- `Game.Simulation.AnimalNavigationSystem+GroupNavigationJob`  
- `Game.Simulation.AnimalNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.AnimalNavigationSystem+TypeHandle`  


# Game.Simulation.AreaLotSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaLotSimulationSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_Watersystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData;
    private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public AreaLotSimulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetUnlimitedTotalAmount(System.Int32 used, System.Int32 originalAmount, System.Single mu);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_Watersystem`  

```csharp
private Game.Simulation.WaterSystem m_Watersystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData`  

```csharp
private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData;
```

- `private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public AreaLotSimulationSystem()`  

```csharp
[Preserve]
	public AreaLotSimulationSystem()
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

- `public static GetUnlimitedTotalAmount(System.Int32 used, System.Int32 originalAmount, System.Single mu) : System.Int32`  

```csharp
public static int GetUnlimitedTotalAmount(int used, int originalAmount, float mu)
	{
		return Mathf.RoundToInt(math.log(originalAmount / 10000) - math.log((originalAmount - used) / 10000) / mu);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 512;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_Watersystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_WorkVehicleSelectData = new WorkVehicleSelectData(this);
		m_AreaQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadWrite<Extractor>(),
				ComponentType.ReadWrite<Storage>(),
				ComponentType.ReadWrite<Game.Buildings.CargoTransportStation>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ExtractorQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Areas.Lot>(),
				ComponentType.ReadWrite<Extractor>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_VehiclePrefabQuery = GetEntityQuery(WorkVehicleSelectData.GetEntityQueryDesc());
		m_ExtractorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorParameterData>());
		RequireForUpdate(m_AreaQuery);
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
		m_WorkVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_VehiclePrefabQuery, Allocator.TempJob, out var jobHandle);
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new ManageVehiclesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WoodResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_WoodResource_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ExtractorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Extractor_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StorageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Storage_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CargoTransportStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CargoTransportStation_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnedVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_WorkRoute_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabExtractorAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStorageAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWorkVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNavigationAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NavigationAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCargoTransportStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStorageCompanyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_VehicleLayouts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubRoutes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_SubRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_WorkVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WorkVehicle_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_WorkVehicleSelectData = m_WorkVehicleSelectData,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 512).AsParallelWriter()
		}, m_AreaQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		m_WorkVehicleSelectData.PostUpdate(jobHandle2);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle2);
		base.Dependency = jobHandle2;
		if (!m_ExtractorQuery.IsEmptyIgnoreFilter)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			JobHandle dependencies;
			CellMapData<NaturalResourceCell> data = m_NaturalResourceSystem.GetData(readOnly: false, out dependencies);
			JobHandle outJobHandle;
			JobHandle dependencies2;
			ExtractResourcesJob jobData = new ExtractResourcesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_MapFeatureElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ExtractorAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ExtractorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Chunks = m_ExtractorQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies2),
				m_City = m_CitySystem.City,
				m_RandomSeed = RandomSeed.Next(),
				m_ExtractorParameters = m_ExtractorParameterQuery.GetSingleton<ExtractorParameterData>(),
				m_NaturalResourceData = data,
				m_UpdateList = nativeList
			};
			JobHandle dependencies3;
			JobHandle dependencies4;
			JobHandle deps;
			AreaResourceSystem.UpdateAreaResourcesJob jobData2 = new AreaResourceSystem.UpdateAreaResourcesJob
			{
				m_City = m_CitySystem.City,
				m_FullUpdate = false,
				m_UpdateList = nativeList.AsDeferredJobArray(),
				m_ObjectTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies3),
				m_NaturalResourceData = data,
				m_GroundWaterResourceData = m_GroundWaterSystem.GetData(readOnly: true, out dependencies4),
				m_GeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ExtractorAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ExtractorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RW_ComponentLookup, ref base.CheckedStateRef),
				m_WoodResources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_WoodResource_RW_BufferLookup, ref base.CheckedStateRef),
				m_MapFeatureElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_MapFeatureElement_RW_BufferLookup, ref base.CheckedStateRef),
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_WaterSurfaceData = m_Watersystem.GetSurfaceData(out deps)
			};
			JobHandle jobHandle3 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, JobHandle.CombineDependencies(outJobHandle, dependencies2, dependencies)));
			JobHandle jobHandle4 = jobData2.Schedule(nativeList, 1, JobUtils.CombineDependencies(jobHandle3, dependencies3, deps, dependencies4));
			nativeList.Dispose(jobHandle4);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle3);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle4);
			m_NaturalResourceSystem.AddWriter(jobHandle4);
			m_TerrainSystem.AddCPUHeightReader(jobHandle4);
			m_Watersystem.AddSurfaceReader(jobHandle4);
			m_GroundWaterSystem.AddReader(jobHandle4);
			base.Dependency = jobHandle4;
		}
	}
```


## Nested types

- `Game.Simulation.AreaLotSimulationSystem+ManageVehiclesJob`  
- `Game.Simulation.AreaLotSimulationSystem+ExtractResourcesJob`  
- `Game.Simulation.AreaLotSimulationSystem+TypeHandle`  


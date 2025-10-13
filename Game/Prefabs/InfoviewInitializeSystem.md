# Game.Prefabs.InfoviewInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InfoviewInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NewInfoviewQuery;
    private Unity.Entities.EntityQuery m_AllInfoviewQuery;
    private Unity.Entities.EntityQuery m_AllInfomodeQuery;
    private Unity.Entities.EntityQuery m_NewPlaceableQuery;
    private Unity.Entities.EntityQuery m_AllPlaceableQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle;
    private static const System.Int32 TYPE_PRIORITY;
    private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY;
    private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY;
    private static const System.Int32 PRIMARY_EFFECT_PRIORITY;
    private static const System.Int32 SECONDARY_EFFECT_PRIORITY;

    public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get; }
    public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get; }

    public InfoviewInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle FindInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewQuery, Unity.Entities.EntityQuery infomodeQuery, Unity.Entities.EntityQuery objectQuery);
    private Unity.Jobs.JobHandle InitializeInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewGroup, Unity.Entities.EntityQuery infomodeGroup);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NewInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewInfoviewQuery;
```

- `private Unity.Entities.EntityQuery m_AllInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllInfoviewQuery;
```

- `private Unity.Entities.EntityQuery m_AllInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllInfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_NewPlaceableQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewPlaceableQuery;
```

- `private Unity.Entities.EntityQuery m_AllPlaceableQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllPlaceableQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.InfoviewInitializeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 TYPE_PRIORITY`  

```csharp
private static const System.Int32 TYPE_PRIORITY;
```

- `private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY`  

```csharp
private static const System.Int32 PRIMARY_REQUIREMENT_PRIORITY;
```

- `private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY`  

```csharp
private static const System.Int32 SECONDARY_REQUIREMENT_PRIORITY;
```

- `private static const System.Int32 PRIMARY_EFFECT_PRIORITY`  

```csharp
private static const System.Int32 PRIMARY_EFFECT_PRIORITY;
```

- `private static const System.Int32 SECONDARY_EFFECT_PRIORITY`  

```csharp
private static const System.Int32 SECONDARY_EFFECT_PRIORITY;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.InfoviewPrefab> infoviews { get; }
```

- `public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Prefabs.InfomodePrefab> infomodes { get; }
```


## Constructors

- `public InfoviewInitializeSystem()`  

```csharp
[Preserve]
	public InfoviewInitializeSystem()
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

- `private FindInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewQuery, Unity.Entities.EntityQuery infomodeQuery, Unity.Entities.EntityQuery objectQuery) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FindInfoviews(JobHandle inputDeps, EntityQuery infoviewQuery, EntityQuery infomodeQuery, EntityQuery objectQuery)
	{
		NativeQueue<InfoviewBufferData> infoViewBuffer = new NativeQueue<InfoviewBufferData>(Allocator.TempJob);
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> infoviewChunks = infoviewQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle outJobHandle2;
		NativeList<ArchetypeChunk> infomodeChunks = infomodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
		FindInfoviewJob jobData = new FindInfoviewJob
		{
			m_InfoviewChunks = infoviewChunks,
			m_InfomodeChunks = infomodeChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CoverageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HospitalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_HospitalData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PowerPlantType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PowerPlantData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransformerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BatteryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BatteryData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPumpingStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterPumpingStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterTowerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterTowerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SewageOutletType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SewageOutletData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransportStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GarbageFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FireStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_FireStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PoliceStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PoliceStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MaintenanceDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MaintenanceDepotData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PostFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PostFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TelecomFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TelecomFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SchoolDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SchoolData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmergencyShelterDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_EmergencyShelterData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DisasterFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_DisasterFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FirewatchTowerDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_FirewatchTowerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeathcareFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_DeathcareFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrisonDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrisonData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AdminBuildingDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AdminBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WelfareOfficeDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WelfareOfficeData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResearchFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResearchFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkingFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ParkingFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PowerLineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PowerLineData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PipelineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PipelineData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElectricityConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ElectricityConnectionData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPipeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterPipeConnectionData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResourceConnectionData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransportStopData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportLineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ExtractorAreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TerraformingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TerraformingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WindPoweredType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WindPoweredData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPoweredType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterPoweredData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroundWaterPoweredType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_GroundWaterPoweredData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PollutionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PollutionData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnableBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceUpgradeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewModeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewMode_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InfoviewCoverageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewCoverageData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewAvailabilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewAvailabilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewVehicleData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewTransportStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewTransportStopData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewRouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewRouteData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewHeatmapType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewHeatmapData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewObjectStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewObjectStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewNetStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PlaceableInfoviewType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableInfoviewItem_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		FindSubInfoviewJob jobData2 = new FindSubInfoviewJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SpawnableBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PlaceableInfoviewType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableInfoviewItem_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingUpgradeElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingUpgradeElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableInfoviewData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceableInfoviewItem_RO_BufferLookup, ref base.CheckedStateRef),
			m_InfoviewModes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_InfoviewMode_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_InfoViewBuffer = infoViewBuffer.AsParallelWriter()
		};
		AssignInfoviewJob jobData3 = new AssignInfoviewJob
		{
			m_InfoViewBuffer = infoViewBuffer,
			m_PlaceableInfoviewData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceableInfoviewItem_RW_BufferLookup, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, objectQuery, JobHandle.CombineDependencies(inputDeps, outJobHandle, outJobHandle2));
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData2, objectQuery, jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData3, dependsOn);
		infoViewBuffer.Dispose(jobHandle2);
		infoviewChunks.Dispose(jobHandle);
		infomodeChunks.Dispose(jobHandle);
		return jobHandle2;
	}
```

- `private InitializeInfoviews(Unity.Jobs.JobHandle inputDeps, Unity.Entities.EntityQuery infoviewGroup, Unity.Entities.EntityQuery infomodeGroup) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle InitializeInfoviews(JobHandle inputDeps, EntityQuery infoviewGroup, EntityQuery infomodeGroup)
	{
		NativeArray<ArchetypeChunk> nativeArray = infoviewGroup.ToArchetypeChunkArray(Allocator.TempJob);
		NativeArray<ArchetypeChunk> nativeArray2 = infomodeGroup.ToArchetypeChunkArray(Allocator.TempJob);
		NativeParallelMultiHashMap<Entity, InfoModeData> nativeParallelMultiHashMap = new NativeParallelMultiHashMap<Entity, InfoModeData>(100, Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<InfoviewMode> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewMode_RW_BufferTypeHandle, ref base.CheckedStateRef);
			ComponentLookup<InfomodeGroup> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_InfomodeGroup_RO_ComponentLookup, ref base.CheckedStateRef);
			inputDeps.Complete();
			for (int i = 0; i < nativeArray2.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray2[i];
				NativeArray<Entity> nativeArray3 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray4.Length; j++)
				{
					Entity mode = nativeArray3[j];
					PrefabData prefabData = nativeArray4[j];
					InfomodeBasePrefab prefab = m_PrefabSystem.GetPrefab<InfomodeBasePrefab>(prefabData);
					if (prefab.m_IncludeInGroups != null)
					{
						for (int k = 0; k < prefab.m_IncludeInGroups.Length; k++)
						{
							Entity entity = m_PrefabSystem.GetEntity(prefab.m_IncludeInGroups[k]);
							nativeParallelMultiHashMap.Add(entity, new InfoModeData
							{
								m_Mode = mode,
								m_Priority = prefab.m_Priority
							});
						}
					}
				}
			}
			for (int l = 0; l < nativeArray.Length; l++)
			{
				ArchetypeChunk archetypeChunk2 = nativeArray[l];
				NativeArray<PrefabData> nativeArray5 = archetypeChunk2.GetNativeArray(ref typeHandle);
				BufferAccessor<InfoviewMode> bufferAccessor = archetypeChunk2.GetBufferAccessor(ref bufferTypeHandle);
				for (int m = 0; m < bufferAccessor.Length; m++)
				{
					PrefabData prefabData2 = nativeArray5[m];
					DynamicBuffer<InfoviewMode> dynamicBuffer = bufferAccessor[m];
					InfoviewPrefab prefab2 = m_PrefabSystem.GetPrefab<InfoviewPrefab>(prefabData2);
					if (prefab2.m_Infomodes == null)
					{
						continue;
					}
					for (int n = 0; n < prefab2.m_Infomodes.Length; n++)
					{
						InfomodeInfo infomodeInfo = prefab2.m_Infomodes[n];
						Entity entity2 = m_PrefabSystem.GetEntity(infomodeInfo.m_Mode);
						if (componentLookup.HasComponent(entity2))
						{
							if (nativeParallelMultiHashMap.TryGetFirstValue(entity2, out var item, out var it))
							{
								do
								{
									int priority = infomodeInfo.m_Priority * 1000000 + infomodeInfo.m_Mode.m_Priority * 1000 + item.m_Priority;
									dynamicBuffer.Add(new InfoviewMode(item.m_Mode, priority, infomodeInfo.m_Supplemental, infomodeInfo.m_Optional));
								}
								while (nativeParallelMultiHashMap.TryGetNextValue(out item, ref it));
							}
						}
						else
						{
							int priority2 = infomodeInfo.m_Priority * 1000000 + infomodeInfo.m_Mode.m_Priority;
							dynamicBuffer.Add(new InfoviewMode(entity2, priority2, infomodeInfo.m_Supplemental, infomodeInfo.m_Optional));
						}
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
			nativeArray2.Dispose();
			nativeParallelMultiHashMap.Dispose();
		}
		return default(JobHandle);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_NewInfoviewQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<InfoviewData>(), ComponentType.ReadOnly<Created>());
		m_AllInfoviewQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<InfoviewData>());
		m_AllInfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<InfomodeData>(), ComponentType.Exclude<InfomodeGroup>());
		m_NewPlaceableQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadWrite<PlaceableInfoviewItem>(), ComponentType.ReadOnly<Created>());
		m_AllPlaceableQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadWrite<PlaceableInfoviewItem>());
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
		if (!m_NewInfoviewQuery.IsEmptyIgnoreFilter)
		{
			base.Dependency = InitializeInfoviews(base.Dependency, m_NewInfoviewQuery, m_AllInfomodeQuery);
			base.Dependency = FindInfoviews(base.Dependency, m_AllInfoviewQuery, m_AllInfomodeQuery, m_AllPlaceableQuery);
		}
		else if (!m_NewPlaceableQuery.IsEmptyIgnoreFilter)
		{
			base.Dependency = FindInfoviews(base.Dependency, m_AllInfoviewQuery, m_AllInfomodeQuery, m_NewPlaceableQuery);
		}
	}
```


## Nested types

- `Game.Prefabs.InfoviewInitializeSystem+InfoModeData`  
- `Game.Prefabs.InfoviewInitializeSystem+FindInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+PollutionType`  
- `Game.Prefabs.InfoviewInitializeSystem+WaterType`  
- `Game.Prefabs.InfoviewInitializeSystem+InfoviewBufferData`  
- `Game.Prefabs.InfoviewInitializeSystem+FindSubInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+AssignInfoviewJob`  
- `Game.Prefabs.InfoviewInitializeSystem+TypeHandle`  
- `Game.Prefabs.InfoviewInitializeSystem+<get___infomodes_F6CD08E>d__30`  
- `Game.Prefabs.InfoviewInitializeSystem+<get___infoviews_5966D7E4>d__28`  
- `Game.Prefabs.InfoviewInitializeSystem+<get_infomodes>d__11`  
- `Game.Prefabs.InfoviewInitializeSystem+<get_infoviews>d__9`  


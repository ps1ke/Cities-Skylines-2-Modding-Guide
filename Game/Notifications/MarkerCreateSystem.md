# Game.Notifications.MarkerCreateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MarkerCreateSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_IconQuery;
    private System.UInt32 m_TransportTypeMask;
    private System.UInt32 m_BuildingTypeMask;
    private System.UInt32 m_BuildingStatusTypeMask;
    private System.UInt32 m_VehicleTypeMask;
    private System.UInt32 m_MarkerTypeMask;
    private System.Boolean m_Loaded;
    private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle;

    public MarkerCreateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private System.UInt32 m_TransportTypeMask`  

```csharp
private System.UInt32 m_TransportTypeMask;
```

- `private System.UInt32 m_BuildingTypeMask`  

```csharp
private System.UInt32 m_BuildingTypeMask;
```

- `private System.UInt32 m_BuildingStatusTypeMask`  

```csharp
private System.UInt32 m_BuildingStatusTypeMask;
```

- `private System.UInt32 m_VehicleTypeMask`  

```csharp
private System.UInt32 m_VehicleTypeMask;
```

- `private System.UInt32 m_MarkerTypeMask`  

```csharp
private System.UInt32 m_MarkerTypeMask;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MarkerCreateSystem()`  

```csharp
[Preserve]
	public MarkerCreateSystem()
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
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_EntityQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Routes.TransportStop>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Vehicle>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<CarTrailer>()
			}
		}, new EntityQueryDesc
		{
			Any = new ComponentType[1] { ComponentType.ReadOnly<Marker>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Owner>()
			}
		}, new EntityQueryDesc
		{
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.OutsideConnection>() },
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Routes.TransportStop>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Building>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Vehicle>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<CarTrailer>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Marker>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Owner>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.OutsideConnection>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_InfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<InfomodeActive>() },
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<InfoviewTransportStopData>(),
				ComponentType.ReadOnly<InfoviewBuildingData>(),
				ComponentType.ReadOnly<InfoviewBuildingStatusData>(),
				ComponentType.ReadOnly<InfoviewVehicleData>(),
				ComponentType.ReadOnly<InfoviewMarkerData>()
			}
		});
		m_IconQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<TransportStopMarkerData>(),
				ComponentType.ReadOnly<BuildingMarkerData>(),
				ComponentType.ReadOnly<VehicleMarkerData>(),
				ComponentType.ReadOnly<MarkerMarkerData>(),
				ComponentType.ReadOnly<PrefabData>()
			}
		});
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
		EntityQuery entityQuery = (GetLoaded() ? m_EntityQuery : m_UpdatedQuery);
		TransportType requiredTransportStopType = TransportType.None;
		MarkerType requiredMarkerType = MarkerType.None;
		uint num = 0u;
		uint num2 = 0u;
		uint num3 = 0u;
		uint num4 = 0u;
		uint num5 = 0u;
		if (m_ToolSystem.activeTool != null)
		{
			if (m_ToolSystem.activeTool.requireStops != TransportType.None)
			{
				num |= (uint)(1 << (int)m_ToolSystem.activeTool.requireStops);
				requiredTransportStopType = m_ToolSystem.activeTool.requireStops;
			}
			if (m_ToolSystem.activeTool.requireStopIcons)
			{
				num = uint.MaxValue;
			}
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			num5 |= 1;
			requiredMarkerType = MarkerType.CreatureSpawner;
		}
		NativeArray<ArchetypeChunk> infomodeChunks = default(NativeArray<ArchetypeChunk>);
		if (!m_InfomodeQuery.IsEmptyIgnoreFilter)
		{
			ComponentTypeHandle<InfoviewTransportStopData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewTransportStopData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfoviewBuildingData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfoviewBuildingStatusData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfoviewVehicleData> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewVehicleData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<InfoviewMarkerData> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewMarkerData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			infomodeChunks = m_InfomodeQuery.ToArchetypeChunkArray(Allocator.TempJob);
			for (int i = 0; i < infomodeChunks.Length; i++)
			{
				ArchetypeChunk archetypeChunk = infomodeChunks[i];
				NativeArray<InfoviewTransportStopData> nativeArray = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<InfoviewBuildingData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
				NativeArray<InfoviewBuildingStatusData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
				NativeArray<InfoviewVehicleData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle4);
				NativeArray<InfoviewMarkerData> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle5);
				for (int j = 0; j < nativeArray.Length; j++)
				{
					InfoviewTransportStopData infoviewTransportStopData = nativeArray[j];
					if (infoviewTransportStopData.m_Type != TransportType.None)
					{
						num |= (uint)(1 << (int)infoviewTransportStopData.m_Type);
					}
				}
				for (int k = 0; k < nativeArray2.Length; k++)
				{
					num2 |= (uint)(1 << (int)nativeArray2[k].m_Type);
				}
				for (int l = 0; l < nativeArray3.Length; l++)
				{
					num3 |= (uint)(1 << (int)nativeArray3[l].m_Type);
				}
				for (int m = 0; m < nativeArray4.Length; m++)
				{
					num4 |= (uint)(1 << (int)nativeArray4[m].m_Type);
				}
				for (int n = 0; n < nativeArray5.Length; n++)
				{
					num5 |= (uint)(1 << (int)nativeArray5[n].m_Type);
				}
			}
		}
		if (num == m_TransportTypeMask && num2 == m_BuildingTypeMask && num3 == m_BuildingStatusTypeMask && num4 == m_VehicleTypeMask && num5 == m_MarkerTypeMask && ((num == 0 && num2 == 0 && num3 == 0 && num4 == 0 && num5 == 0) || entityQuery.IsEmptyIgnoreFilter))
		{
			if (infomodeChunks.IsCreated)
			{
				infomodeChunks.Dispose();
			}
			return;
		}
		m_TransportTypeMask = num;
		m_BuildingTypeMask = num2;
		m_BuildingStatusTypeMask = num3;
		m_VehicleTypeMask = num4;
		m_MarkerTypeMask = num5;
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> iconChunks = m_IconQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new MarkerCreateJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewTransportStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewTransportStopData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewBuildingStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewVehicleData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewMarkerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfomodeActiveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportStopMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransportStopMarkerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingMarkerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_VehicleMarkerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MarkerMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MarkerMarkerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkedCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkedTrainType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UniqueObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UniqueObject_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IconElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Notifications_IconElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BusStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_BusStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TrainStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TaxiStandType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TaxiStand_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TramStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TramStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ShipStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_ShipStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MailBoxType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_MailBox_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WorkStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AirplaneStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_AirplaneStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubwayStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_SubwayStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HospitalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Hospital_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElectricityProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Transformer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BatteryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Battery_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPumpingStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPumpingStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterTowerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterTower_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SewageOutletType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_SewageOutlet_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WastewaterTreatmentPlantType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WastewaterTreatmentPlant_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransportStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GarbageFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FireStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_FireStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PoliceStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PoliceStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadMaintenanceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RoadMaintenance_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkMaintenanceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ParkMaintenance_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PostFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PostFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TelecomFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TelecomFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SchoolType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_School_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmergencyShelterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_EmergencyShelter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DisasterFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_DisasterFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FirewatchTowerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_FirewatchTower_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeathcareFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_DeathcareFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrisonType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Prison_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AdminBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_AdminBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WelfareOfficeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WelfareOffice_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResearchFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResearchFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkingFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ParkingFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResidentialPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResidentialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommercialPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CommercialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_IndustrialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OfficePropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_OfficeProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ExtractorPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ExtractorProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PassengerTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PassengerTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CargoTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CargoTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TaxiType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkMaintenanceVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkMaintenanceVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadMaintenanceVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_RoadMaintenanceVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AmbulanceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Ambulance_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EvacuatingTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_EvacuatingTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FireEngineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_FireEngine_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GarbageTruckType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_GarbageTruck_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HearseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Hearse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PoliceCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PoliceCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PostVanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PostVan_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrisonerTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PrisonerTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatureSpawnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_CreatureSpawner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElectricityOutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_ElectricityOutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPipeOutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_WaterPipeOutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportStopData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkStopData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InfomodeChunks = infomodeChunks,
			m_IconChunks = iconChunks,
			m_RequiredTransportStopType = requiredTransportStopType,
			m_RequiredMarkerType = requiredMarkerType,
			m_RequireStandaloneStops = (num == uint.MaxValue),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		}, m_EntityQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		if (infomodeChunks.IsCreated)
		{
			infomodeChunks.Dispose(jobHandle);
		}
		iconChunks.Dispose(jobHandle);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		m_TransportTypeMask = uint.MaxValue;
		m_BuildingTypeMask = uint.MaxValue;
		m_BuildingStatusTypeMask = uint.MaxValue;
		m_VehicleTypeMask = uint.MaxValue;
		m_MarkerTypeMask = uint.MaxValue;
		m_Loaded = true;
	}
```


## Nested types

- `Game.Notifications.MarkerCreateSystem+MarkerCreateJob`  
- `Game.Notifications.MarkerCreateSystem+TypeHandle`  


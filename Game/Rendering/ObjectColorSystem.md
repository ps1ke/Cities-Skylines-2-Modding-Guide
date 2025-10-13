# Game.Rendering.ObjectColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectColorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_MiddleObjectQuery;
    private Unity.Entities.EntityQuery m_TempObjectQuery;
    private Unity.Entities.EntityQuery m_SubObjectQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.FireHazardSystem m_FireHazardSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle;

    public ObjectColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_MiddleObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_MiddleObjectQuery;
```

- `private Unity.Entities.EntityQuery m_TempObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempObjectQuery;
```

- `private Unity.Entities.EntityQuery m_SubObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubObjectQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  

```csharp
private Game.Simulation.FireHazardSystem m_FireHazardSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectColorSystem()`  

```csharp
[Preserve]
	public ObjectColorSystem()
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
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_FireHazardSystem = base.World.GetOrCreateSystemManaged<FireHazardSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.Object>(),
				ComponentType.ReadWrite<Game.Objects.Color>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Owner>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Objects.Object>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadWrite<Game.Objects.Color>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Vehicle>(),
				ComponentType.ReadOnly<Creature>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Objects.UtilityObject>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_MiddleObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadWrite<Game.Objects.Color>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Vehicle>(),
				ComponentType.ReadOnly<Controller>(),
				ComponentType.ReadWrite<Game.Objects.Color>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_TempObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Objects.Object>(),
				ComponentType.ReadWrite<Game.Objects.Color>(),
				ComponentType.ReadOnly<Temp>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_SubObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Objects.Object>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadWrite<Game.Objects.Color>()
			},
			None = new ComponentType[6]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Vehicle>(),
				ComponentType.ReadOnly<Creature>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Objects.UtilityObject>()
			}
		});
		m_InfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<InfomodeActive>() },
			Any = new ComponentType[6]
			{
				ComponentType.ReadOnly<InfoviewBuildingData>(),
				ComponentType.ReadOnly<InfoviewBuildingStatusData>(),
				ComponentType.ReadOnly<InfoviewTransportStopData>(),
				ComponentType.ReadOnly<InfoviewVehicleData>(),
				ComponentType.ReadOnly<InfoviewObjectStatusData>(),
				ComponentType.ReadOnly<InfoviewNetStatusData>()
			},
			None = new ComponentType[0]
		});
		m_HappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		m_FireConfigQuery = GetEntityQuery(ComponentType.ReadOnly<FireConfigurationData>());
		m_FireHazardData = new EventHelpers.FireHazardData(this);
		RequireForUpdate(m_HappinessParameterQuery);
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
		if (!(m_ToolSystem.activeInfoview == null) && !m_ObjectQuery.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			LocalEffectSystem.ReadData readData = m_LocalEffectSystem.GetReadData(out dependencies);
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> infomodeChunks = m_InfomodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			FireConfigurationPrefab prefab = m_PrefabSystem.GetPrefab<FireConfigurationPrefab>(m_FireConfigQuery.GetSingletonEntity());
			m_FireHazardData.Update(this, readData, prefab, m_ClimateSystem.temperature, m_FireHazardSystem.noRainDays);
			JobHandle dependencies2;
			UpdateObjectColorsJob jobData = new UpdateObjectColorsJob
			{
				m_InfomodeChunks = infomodeChunks,
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfomodeActiveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewBuildingStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewBuildingStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewTransportStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewTransportStopData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewVehicleData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewObjectStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewObjectStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewNetStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewNetStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HospitalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Hospital_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElectricityProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Transformer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WaterPumpingStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPumpingStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WaterTowerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterTower_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SewageOutletType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_SewageOutlet_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WastewaterTreatmentPlantType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WastewaterTreatmentPlant_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransportStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_GarbageFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FireStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_FireStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PoliceStationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PoliceStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CrimeProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RoadMaintenanceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RoadMaintenance_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkMaintenanceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ParkMaintenance_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PostFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PostFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TelecomFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TelecomFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SchoolType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_School_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AttractivenessProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_AttractivenessProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EmergencyShelterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_EmergencyShelter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DisasterFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_DisasterFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FirewatchTowerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_FirewatchTower_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeathcareFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_DeathcareFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrisonType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Prison_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AdminBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_AdminBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WelfareOfficeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WelfareOffice_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResearchFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResearchFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkingFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ParkingFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BatteryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Battery_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MailProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingConditionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_BuildingCondition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResidentialPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResidentialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CommercialPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CommercialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_IndustrialPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_IndustrialProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OfficePropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_OfficeProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StoragePropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_StorageProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ExtractorPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ExtractorProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_GarbageProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AbandonedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LeisureProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_LeisureProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElectricityConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WaterConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingEfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransportStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BusStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_BusStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrainStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TrainStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TaxiStandType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TaxiStand_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TramStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TramStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ShipStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_ShipStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MailBoxType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_MailBox_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WorkStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WorkStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AirplaneStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_AirplaneStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubwayStopType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_SubwayStop_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_VehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
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
				m_PassengerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ResidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlantType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UtilityObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UtilityObject_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DamagedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UnderConstructionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UniqueObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UniqueObject_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlaceholderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Placeholder_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AttachedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AccidentSiteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_AccidentSite_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AbandonedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PollutionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PollutionModifierData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionModifierData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommercialCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CommercialCompany_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlaceholderBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SewageOutletData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SewageOutletData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Profitabilities = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_Profitability_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LeisureProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_LeisureProvider_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
				m_ResourceBuffs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabUtilityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityNodeConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterPipeNodeConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityFlowEdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterPipeEdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedFlowEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_FireHazardData = m_FireHazardData,
				m_TelecomCoverageData = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies2),
				m_PollutionParameters = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>(),
				m_City = m_CitySystem.City,
				m_ColorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Color_RW_ComponentTypeHandle, ref base.CheckedStateRef)
			};
			UpdateMiddleObjectColorsJob jobData2 = new UpdateMiddleObjectColorsJob
			{
				m_InfomodeChunks = infomodeChunks,
				m_InfomodeActiveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfomodeActive_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InfoviewObjectStatusType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewObjectStatusData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			UpdateTempObjectColorsJob jobData3 = new UpdateTempObjectColorsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			UpdateSubObjectColorsJob jobData4 = new UpdateSubObjectColorsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElevationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlantType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_ObjectQuery, JobHandle.CombineDependencies(base.Dependency, JobHandle.CombineDependencies(dependencies2, dependencies, outJobHandle)));
			JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData2, m_MiddleObjectQuery, jobHandle);
			JobHandle dependency = JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(jobData3, m_TempObjectQuery, jobHandle2), jobData: jobData4, query: m_SubObjectQuery);
			infomodeChunks.Dispose(jobHandle2);
			m_LocalEffectSystem.AddLocalEffectReader(jobHandle);
			m_TelecomCoverageSystem.AddReader(jobHandle);
			base.Dependency = dependency;
		}
	}
```


## Nested types

- `Game.Rendering.ObjectColorSystem+UpdateObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateMiddleObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateTempObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateSubObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+TypeHandle`  


# Game.Simulation.IndustrialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Unity.Entities.EntityQuery m_IndustrialQuery`  
- `private Unity.Entities.EntityQuery m_OfficeQuery`  
- `private Unity.Entities.EntityQuery m_StorageCompanyQuery`  
- `private Unity.Entities.EntityQuery m_ProcessDataQuery`  
- `private Unity.Entities.EntityQuery m_CityServiceQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand`  
- `private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand`  
- `private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand`  
- `private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand`  
- `private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand`  
- `private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand`  
- `private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors`  
- `private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors`  
- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_FreeProperties`  
- `private Unity.Collections.NativeArray<System.Int32> m_FreeStorages`  
- `private Unity.Collections.NativeArray<System.Int32> m_Storages`  
- `private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private System.Int32 m_LastIndustrialCompanyDemand`  
- `private System.Int32 m_LastIndustrialBuildingDemand`  
- `private System.Int32 m_LastStorageCompanyDemand`  
- `private System.Int32 m_LastStorageBuildingDemand`  
- `private System.Int32 m_LastOfficeCompanyDemand`  
- `private System.Int32 m_LastOfficeBuildingDemand`  
- `private System.Single m_IndustrialOfficeTaxEffectDemandOffset`  
- `private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Int32 kStorageProductionDemand`  
- `private static readonly System.Int32 kStorageCompanyEstimateLimit`  

## Properties

- `public System.Int32 industrialCompanyDemand { get }`  
- `public System.Int32 industrialBuildingDemand { get }`  
- `public System.Int32 storageCompanyDemand { get }`  
- `public System.Int32 storageBuildingDemand { get }`  
- `public System.Int32 officeCompanyDemand { get }`  
- `public System.Int32 officeBuildingDemand { get }`  

## Constructors

- `public IndustrialDemandSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetConsumption(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetIndustrialDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetIndustrialResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetOfficeDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetStorageBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetStorageCompanyDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.IndustrialDemandSystem+UpdateIndustrialDemandJob`  
- `Game.Simulation.IndustrialDemandSystem+TypeHandle`  


# Game.Simulation.CommercialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Unity.Entities.EntityQuery m_CommercialQuery`  
- `private Unity.Entities.EntityQuery m_CommercialProcessDataQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand`  
- `private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand`  
- `private Unity.Collections.NativeArray<System.Int32> m_DemandFactors`  
- `private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands`  
- `private Unity.Collections.NativeArray<System.Int32> m_Consumption`  
- `private Unity.Collections.NativeArray<System.Int32> m_FreeProperties`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private System.Int32 m_LastCompanyDemand`  
- `private System.Int32 m_LastBuildingDemand`  
- `private System.Single m_CommercialTaxEffectDemandOffset`  
- `private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Int32 companyDemand { get }`  
- `public System.Int32 buildingDemand { get }`  

## Constructors

- `public CommercialDemandSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetConsumption(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
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

- `Game.Simulation.CommercialDemandSystem+UpdateCommercialDemandJob`  
- `Game.Simulation.CommercialDemandSystem+TypeHandle`  


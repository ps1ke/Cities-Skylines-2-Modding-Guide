# Game.Simulation.CountCompanyDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Unity.Entities.EntityQuery m_FreeIndustrialQuery`  
- `private Unity.Entities.EntityQuery m_IndustrialCompanyQuery`  
- `private Unity.Entities.EntityQuery m_StorageCompanyQuery`  
- `private Unity.Entities.EntityQuery m_ProcessDataQuery`  
- `private Unity.Entities.EntityQuery m_CityServiceQuery`  
- `private Unity.Entities.EntityQuery m_SpawnableQuery`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers`  
- `private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers`  
- `private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers`  
- `private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers`  
- `private Unity.Collections.NativeArray<System.Int32> m_Production`  
- `private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities`  
- `private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables`  
- `private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables`  
- `private Unity.Collections.NativeArray<System.Int32> m_Demand`  
- `private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies`  
- `private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies`  
- `private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless`  
- `private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless`  
- `private Unity.Entities.EntityQuery m_CompanyQuery`  
- `private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CountCompanyDataSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetCommercialCompanyDatas(Unity.Jobs.JobHandle& deps) : Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas`  
- `public GetIndustrialCompanyDatas(Unity.Jobs.JobHandle& deps) : Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas`  
- `public GetProduction(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
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

- `Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas`  
- `Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas`  
- `Game.Simulation.CountCompanyDataSystem+CompanyDataItem`  
- `Game.Simulation.CountCompanyDataSystem+SumJob`  
- `Game.Simulation.CountCompanyDataSystem+CountCompanyDataJob`  
- `Game.Simulation.CountCompanyDataSystem+TypeHandle`  


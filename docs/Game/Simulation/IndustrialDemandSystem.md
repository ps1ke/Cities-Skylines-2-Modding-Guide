# Game.Simulation.IndustrialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialDemandSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_IndustrialQuery;
    private Unity.Entities.EntityQuery m_OfficeQuery;
    private Unity.Entities.EntityQuery m_StorageCompanyQuery;
    private Unity.Entities.EntityQuery m_ProcessDataQuery;
    private Unity.Entities.EntityQuery m_CityServiceQuery;
    private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand;
    private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands;
    private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands;
    private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands;
    private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
    private Unity.Collections.NativeArray<System.Int32> m_FreeStorages;
    private Unity.Collections.NativeArray<System.Int32> m_Storages;
    private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Int32 m_LastIndustrialCompanyDemand;
    private System.Int32 m_LastIndustrialBuildingDemand;
    private System.Int32 m_LastStorageCompanyDemand;
    private System.Int32 m_LastStorageBuildingDemand;
    private System.Int32 m_LastOfficeCompanyDemand;
    private System.Int32 m_LastOfficeBuildingDemand;
    private System.Single m_IndustrialOfficeTaxEffectDemandOffset;
    private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kStorageProductionDemand;
    private static readonly System.Int32 kStorageCompanyEstimateLimit;

    public System.Int32 industrialCompanyDemand { get; }
    public System.Int32 industrialBuildingDemand { get; }
    public System.Int32 storageCompanyDemand { get; }
    public System.Int32 storageBuildingDemand { get; }
    public System.Int32 officeCompanyDemand { get; }
    public System.Int32 officeBuildingDemand { get; }

    public IndustrialDemandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetBuildingDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetConsumption(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetIndustrialDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetIndustrialResourceDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetOfficeDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetResourceDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetStorageBuildingDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetStorageCompanyDemands(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialQuery;
```

- `private Unity.Entities.EntityQuery m_OfficeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OfficeQuery;
```

- `private Unity.Entities.EntityQuery m_StorageCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessDataQuery;
```

- `private Unity.Entities.EntityQuery m_CityServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityServiceQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeProperties`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeStorages`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeStorages;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Storages`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Storages;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Int32 m_LastIndustrialCompanyDemand`  

```csharp
private System.Int32 m_LastIndustrialCompanyDemand;
```

- `private System.Int32 m_LastIndustrialBuildingDemand`  

```csharp
private System.Int32 m_LastIndustrialBuildingDemand;
```

- `private System.Int32 m_LastStorageCompanyDemand`  

```csharp
private System.Int32 m_LastStorageCompanyDemand;
```

- `private System.Int32 m_LastStorageBuildingDemand`  

```csharp
private System.Int32 m_LastStorageBuildingDemand;
```

- `private System.Int32 m_LastOfficeCompanyDemand`  

```csharp
private System.Int32 m_LastOfficeCompanyDemand;
```

- `private System.Int32 m_LastOfficeBuildingDemand`  

```csharp
private System.Int32 m_LastOfficeBuildingDemand;
```

- `private System.Single m_IndustrialOfficeTaxEffectDemandOffset`  

```csharp
private System.Single m_IndustrialOfficeTaxEffectDemandOffset;
```

- `private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kStorageProductionDemand`  

```csharp
private static readonly System.Int32 kStorageProductionDemand;
```

- `private static readonly System.Int32 kStorageCompanyEstimateLimit`  

```csharp
private static readonly System.Int32 kStorageCompanyEstimateLimit;
```


## Properties

- `public System.Int32 industrialCompanyDemand { get }`  

```csharp
public System.Int32 industrialCompanyDemand { get; }
```

- `public System.Int32 industrialBuildingDemand { get }`  

```csharp
public System.Int32 industrialBuildingDemand { get; }
```

- `public System.Int32 storageCompanyDemand { get }`  

```csharp
public System.Int32 storageCompanyDemand { get; }
```

- `public System.Int32 storageBuildingDemand { get }`  

```csharp
public System.Int32 storageBuildingDemand { get; }
```

- `public System.Int32 officeCompanyDemand { get }`  

```csharp
public System.Int32 officeCompanyDemand { get; }
```

- `public System.Int32 officeBuildingDemand { get }`  

```csharp
public System.Int32 officeBuildingDemand { get; }
```


## Constructors

- `public IndustrialDemandSystem()`  

```csharp
public IndustrialDemandSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public System.Void AddReader(Unity.Jobs.JobHandle reader);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetBuildingDemands(Unity.Jobs.JobHandle& deps);
```

- `public GetConsumption(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetConsumption(Unity.Jobs.JobHandle& deps);
```

- `public GetIndustrialDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetIndustrialDemandFactors(Unity.Jobs.JobHandle& deps);
```

- `public GetIndustrialResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetIndustrialResourceDemands(Unity.Jobs.JobHandle& deps);
```

- `public GetOfficeDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetOfficeDemandFactors(Unity.Jobs.JobHandle& deps);
```

- `public GetResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetResourceDemands(Unity.Jobs.JobHandle& deps);
```

- `public GetStorageBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetStorageBuildingDemands(Unity.Jobs.JobHandle& deps);
```

- `public GetStorageCompanyDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetStorageCompanyDemands(Unity.Jobs.JobHandle& deps);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.IndustrialDemandSystem+UpdateIndustrialDemandJob`  
- `Game.Simulation.IndustrialDemandSystem+TypeHandle`  


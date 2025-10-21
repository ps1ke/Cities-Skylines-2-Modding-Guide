# Game.Simulation.CommercialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommercialDemandSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_CommercialQuery;
    private Unity.Entities.EntityQuery m_CommercialProcessDataQuery;
    private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand;
    private Unity.Collections.NativeArray<System.Int32> m_DemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
    private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands;
    private Unity.Collections.NativeArray<System.Int32> m_Consumption;
    private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Int32 m_LastCompanyDemand;
    private System.Int32 m_LastBuildingDemand;
    private System.Single m_CommercialTaxEffectDemandOffset;
    private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle;

    public System.Int32 companyDemand { get; }
    public System.Int32 buildingDemand { get; }

    public CommercialDemandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetBuildingDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetConsumption(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetResourceDemands(Unity.Jobs.JobHandle& deps);
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

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialProcessDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialProcessDataQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_DemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_DemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Consumption`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Consumption;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeProperties`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Int32 m_LastCompanyDemand`  

```csharp
private System.Int32 m_LastCompanyDemand;
```

- `private System.Int32 m_LastBuildingDemand`  

```csharp
private System.Int32 m_LastBuildingDemand;
```

- `private System.Single m_CommercialTaxEffectDemandOffset`  

```csharp
private System.Single m_CommercialTaxEffectDemandOffset;
```

- `private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 companyDemand { get }`  

```csharp
public System.Int32 companyDemand { get; }
```

- `public System.Int32 buildingDemand { get }`  

```csharp
public System.Int32 buildingDemand { get; }
```


## Constructors

- `public CommercialDemandSystem()`  

```csharp
public CommercialDemandSystem();
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

- `public GetDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetDemandFactors(Unity.Jobs.JobHandle& deps);
```

- `public GetResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetResourceDemands(Unity.Jobs.JobHandle& deps);
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

- `Game.Simulation.CommercialDemandSystem+UpdateCommercialDemandJob`  
- `Game.Simulation.CommercialDemandSystem+TypeHandle`  


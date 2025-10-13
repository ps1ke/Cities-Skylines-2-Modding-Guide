# Game.Simulation.CountCompanyDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountCompanyDataSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_FreeIndustrialQuery;
    private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
    private Unity.Entities.EntityQuery m_StorageCompanyQuery;
    private Unity.Entities.EntityQuery m_ProcessDataQuery;
    private Unity.Entities.EntityQuery m_CityServiceQuery;
    private Unity.Entities.EntityQuery m_SpawnableQuery;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_Production;
    private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities;
    private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables;
    private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables;
    private Unity.Collections.NativeArray<System.Int32> m_Demand;
    private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies;
    private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies;
    private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless;
    private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle;

    public CountCompanyDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas GetCommercialCompanyDatas(Unity.Jobs.JobHandle& deps);
    public Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas GetIndustrialCompanyDatas(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetProduction(Unity.Jobs.JobHandle& deps);
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

- `private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_FreeIndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeIndustrialQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
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

- `private Unity.Entities.EntityQuery m_SpawnableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableQuery;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Production`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Production;
```

- `private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Demand`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Demand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CountCompanyDataSystem()`  

```csharp
public CountCompanyDataSystem();
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

- `public GetCommercialCompanyDatas(Unity.Jobs.JobHandle& deps) : Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas`  

```csharp
public Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas GetCommercialCompanyDatas(Unity.Jobs.JobHandle& deps);
```

- `public GetIndustrialCompanyDatas(Unity.Jobs.JobHandle& deps) : Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas`  

```csharp
public Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas GetIndustrialCompanyDatas(Unity.Jobs.JobHandle& deps);
```

- `public GetProduction(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetProduction(Unity.Jobs.JobHandle& deps);
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

- `Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas`  
- `Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas`  
- `Game.Simulation.CountCompanyDataSystem+CompanyDataItem`  
- `Game.Simulation.CountCompanyDataSystem+SumJob`  
- `Game.Simulation.CountCompanyDataSystem+CountCompanyDataJob`  
- `Game.Simulation.CountCompanyDataSystem+TypeHandle`  


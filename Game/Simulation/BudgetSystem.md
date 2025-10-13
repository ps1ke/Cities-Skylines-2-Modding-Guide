# Game.Simulation.BudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IBudgetSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BudgetSystem : Game.GameSystemBase, Game.Simulation.IBudgetSystem
{
    private System.UInt32 m_LastUpdate;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    protected Unity.Collections.NativeArray<System.Int32> m_Trade;
    protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth;
    protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth;
    protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth;
    protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth;
    protected System.Int32 m_TotalTradeWorth;
    protected System.Int32 m_TotalTaxIncome;
    private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount;
    private Unity.Collections.NativeArray<System.Int32> m_ServiceCount;
    private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers;
    private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing;
    private Unity.Collections.NativeArray<System.Int32> m_TouristCount;
    private Unity.Collections.NativeArray<System.Int32> m_TouristIncome;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle;

    public System.Boolean HasData { get; }
    public System.UInt32 LastUpdate { get; }

    public BudgetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Unity.Mathematics.float2 GetCitizenWellbeing();
    public System.Int32 GetCompanyCount(System.Boolean service, Game.Economy.Resource resource);
    public System.Int32 GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource);
    public Unity.Mathematics.int2 GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource);
    public System.Int32 GetHouseholdCount();
    public System.Int32 GetHouseholdWealth();
    public Unity.Mathematics.int2 GetHouseholdWorkers();
    public Unity.Mathematics.int2 GetLodgingData();
    public System.Int32 GetTotalTradeWorth();
    public System.Int32 GetTouristCount();
    public System.Int32 GetTouristIncome();
    public System.Int32 GetTrade(Game.Economy.Resource resource);
    public System.Int32 GetTradeWorth(Game.Economy.Resource resource);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void SetTradeWorth(Game.Economy.Resource resource, Game.Prefabs.ResourceData resourceData);
    private System.Void UpdateData();
    private System.Void UpdateTotalTradeWorth();
}
```


## Fields

- `private System.UInt32 m_LastUpdate`  

```csharp
private System.UInt32 m_LastUpdate;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_Trade`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_Trade;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth;
```

- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth`  

```csharp
protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth;
```

- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth`  

```csharp
protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth;
```

- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth`  

```csharp
protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth;
```

- `protected System.Int32 m_TotalTradeWorth`  

```csharp
protected System.Int32 m_TotalTradeWorth;
```

- `protected System.Int32 m_TotalTaxIncome`  

```csharp
protected System.Int32 m_TotalTaxIncome;
```

- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ServiceCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ServiceCount;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TouristCount`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TouristCount;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TouristIncome`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TouristIncome;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean HasData { get }`  

```csharp
public System.Boolean HasData { get; }
```

- `public System.UInt32 LastUpdate { get }`  

```csharp
public System.UInt32 LastUpdate { get; }
```


## Constructors

- `public BudgetSystem()`  

```csharp
public BudgetSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetCitizenWellbeing() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 GetCitizenWellbeing();
```

- `public GetCompanyCount(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetCompanyCount(System.Boolean service, Game.Economy.Resource resource);
```

- `public GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource);
```

- `public GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource) : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource);
```

- `public GetHouseholdCount() : System.Int32`  

```csharp
public System.Int32 GetHouseholdCount();
```

- `public GetHouseholdWealth() : System.Int32`  

```csharp
public System.Int32 GetHouseholdWealth();
```

- `public GetHouseholdWorkers() : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetHouseholdWorkers();
```

- `public GetLodgingData() : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetLodgingData();
```

- `public GetTotalTradeWorth() : System.Int32`  

```csharp
public System.Int32 GetTotalTradeWorth();
```

- `public GetTouristCount() : System.Int32`  

```csharp
public System.Int32 GetTouristCount();
```

- `public GetTouristIncome() : System.Int32`  

```csharp
public System.Int32 GetTouristIncome();
```

- `public GetTrade(Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetTrade(Game.Economy.Resource resource);
```

- `public GetTradeWorth(Game.Economy.Resource resource) : System.Int32`  

```csharp
public System.Int32 GetTradeWorth(Game.Economy.Resource resource);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private SetTradeWorth(Game.Economy.Resource resource, Game.Prefabs.ResourceData resourceData) : System.Void`  

```csharp
private System.Void SetTradeWorth(Game.Economy.Resource resource, Game.Prefabs.ResourceData resourceData);
```

- `private UpdateData() : System.Void`  

```csharp
private System.Void UpdateData();
```

- `private UpdateTotalTradeWorth() : System.Void`  

```csharp
private System.Void UpdateTotalTradeWorth();
```


## Nested types

- `Game.Simulation.BudgetSystem+TypeHandle`  


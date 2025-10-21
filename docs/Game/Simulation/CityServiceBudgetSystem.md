# Game.Simulation.CityServiceBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICityServiceBudgetSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceBudgetSystem : Game.GameSystemBase, Game.Simulation.ICityServiceBudgetSystem
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;
    private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Unity.Entities.EntityQuery m_UpkeepGroup;
    private Unity.Entities.EntityQuery m_ServiceObjectQuery;
    private Unity.Entities.EntityQuery m_NetUpkeepQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery;
    private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
    private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
    private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
    private Unity.Entities.EntityQuery m_FireStationQuery;
    private Unity.Entities.EntityQuery m_PoliceStationQuery;
    protected Unity.Collections.NativeArray<System.Int32> m_Income;
    protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp;
    protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome;
    protected Unity.Collections.NativeArray<System.Int32> m_Expenses;
    protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp;
    private System.Int32 m_TotalTaxIncome;
    private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices;
    private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps;
    private Unity.Jobs.JobHandle m_TempArrayDeps;
    private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_844909884_0;

    public CityServiceBudgetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddArrayReader(Unity.Jobs.JobHandle deps);
    public System.Int32 GetBalance();
    public static System.Int32 GetBalance(Unity.Collections.NativeArray<System.Int32> income, Unity.Collections.NativeArray<System.Int32> expenses);
    public System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep);
    public static System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> upkeepIndices, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas);
    private static System.Int32 GetEstimatedServiceUpkeep(Game.Simulation.CollectedCityServiceBudgetData data, Unity.Mathematics.int2 indices, System.Int32 budget, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps);
    public System.Int32 GetExpense(Game.City.ExpenseSource source);
    public static System.Int32 GetExpense(Game.City.ExpenseSource source, Unity.Collections.NativeArray<System.Int32> expenses);
    public Unity.Collections.NativeArray<System.Int32> GetExpenseArray(Unity.Jobs.JobHandle& deps);
    public System.Int32 GetIncome(Game.City.IncomeSource source);
    public static System.Int32 GetIncome(Game.City.IncomeSource source, Unity.Collections.NativeArray<System.Int32> income);
    public Unity.Collections.NativeArray<System.Int32> GetIncomeArray(Unity.Jobs.JobHandle& deps);
    public System.Int32 GetMoneyDelta();
    public System.Int32 GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab);
    public System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab);
    public static System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas);
    public Unity.Entities.Entity[] GetServiceBuildings(Unity.Entities.Entity servicePrefab);
    public System.Int32 GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget);
    public System.Int32 GetTotalExpenses();
    public static System.Int32 GetTotalExpenses(Unity.Collections.NativeArray<System.Int32> expenses);
    public System.Int32 GetTotalIncome();
    public static System.Int32 GetTotalIncome(Unity.Collections.NativeArray<System.Int32> income);
    public System.Int32 GetTotalIncome(Game.City.IncomeSource source);
    public System.Int32 GetTotalTaxIncome();
    private static System.Int32 GetTotalTaxIncome(Unity.Collections.NativeArray<System.Int32> income);
    public Unity.Mathematics.int2 GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem`  

```csharp
private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Unity.Entities.EntityQuery m_UpkeepGroup`  

```csharp
private Unity.Entities.EntityQuery m_UpkeepGroup;
```

- `private Unity.Entities.EntityQuery m_ServiceObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceObjectQuery;
```

- `private Unity.Entities.EntityQuery m_NetUpkeepQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetUpkeepQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_DeathcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_FireStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireStationQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceStationQuery;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_Income`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_Income;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_Expenses`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_Expenses;
```

- `protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp`  

```csharp
protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp;
```

- `private System.Int32 m_TotalTaxIncome`  

```csharp
private System.Int32 m_TotalTaxIncome;
```

- `private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes`  

```csharp
private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices;
```

- `private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps;
```

- `private Unity.Jobs.JobHandle m_TempArrayDeps`  

```csharp
private Unity.Jobs.JobHandle m_TempArrayDeps;
```

- `private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_844909884_0`  

```csharp
private Unity.Entities.EntityQuery __query_844909884_0;
```


## Constructors

- `public CityServiceBudgetSystem()`  

```csharp
public CityServiceBudgetSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddArrayReader(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public System.Void AddArrayReader(Unity.Jobs.JobHandle deps);
```

- `public GetBalance() : System.Int32`  

```csharp
public System.Int32 GetBalance();
```

- `public static GetBalance(Unity.Collections.NativeArray<System.Int32> income, Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  

```csharp
public static System.Int32 GetBalance(Unity.Collections.NativeArray<System.Int32> income, Unity.Collections.NativeArray<System.Int32> expenses);
```

- `public GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep) : System.Void`  

```csharp
public System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep);
```

- `public static GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> upkeepIndices, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas) : System.Void`  

```csharp
public static System.Void GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> upkeepIndices, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas);
```

- `private static GetEstimatedServiceUpkeep(Game.Simulation.CollectedCityServiceBudgetData data, Unity.Mathematics.int2 indices, System.Int32 budget, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps) : System.Int32`  

```csharp
private static System.Int32 GetEstimatedServiceUpkeep(Game.Simulation.CollectedCityServiceBudgetData data, Unity.Mathematics.int2 indices, System.Int32 budget, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps);
```

- `public GetExpense(Game.City.ExpenseSource source) : System.Int32`  

```csharp
public System.Int32 GetExpense(Game.City.ExpenseSource source);
```

- `public static GetExpense(Game.City.ExpenseSource source, Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  

```csharp
public static System.Int32 GetExpense(Game.City.ExpenseSource source, Unity.Collections.NativeArray<System.Int32> expenses);
```

- `public GetExpenseArray(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetExpenseArray(Unity.Jobs.JobHandle& deps);
```

- `public GetIncome(Game.City.IncomeSource source) : System.Int32`  

```csharp
public System.Int32 GetIncome(Game.City.IncomeSource source);
```

- `public static GetIncome(Game.City.IncomeSource source, Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  

```csharp
public static System.Int32 GetIncome(Game.City.IncomeSource source, Unity.Collections.NativeArray<System.Int32> income);
```

- `public GetIncomeArray(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetIncomeArray(Unity.Jobs.JobHandle& deps);
```

- `public GetMoneyDelta() : System.Int32`  

```csharp
public System.Int32 GetMoneyDelta();
```

- `public GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab) : System.Int32`  

```csharp
public System.Int32 GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab);
```

- `public GetServiceBudget(Unity.Entities.Entity servicePrefab) : System.Int32`  

```csharp
public System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab);
```

- `public static GetServiceBudget(Unity.Entities.Entity servicePrefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas) : System.Int32`  

```csharp
public static System.Int32 GetServiceBudget(Unity.Entities.Entity servicePrefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas);
```

- `public GetServiceBuildings(Unity.Entities.Entity servicePrefab) : Unity.Entities.Entity[]`  

```csharp
public Unity.Entities.Entity[] GetServiceBuildings(Unity.Entities.Entity servicePrefab);
```

- `public GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget) : System.Int32`  

```csharp
public System.Int32 GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget);
```

- `public GetTotalExpenses() : System.Int32`  

```csharp
public System.Int32 GetTotalExpenses();
```

- `public static GetTotalExpenses(Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  

```csharp
public static System.Int32 GetTotalExpenses(Unity.Collections.NativeArray<System.Int32> expenses);
```

- `public GetTotalIncome() : System.Int32`  

```csharp
public System.Int32 GetTotalIncome();
```

- `public static GetTotalIncome(Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  

```csharp
public static System.Int32 GetTotalIncome(Unity.Collections.NativeArray<System.Int32> income);
```

- `public GetTotalIncome(Game.City.IncomeSource source) : System.Int32`  

```csharp
public System.Int32 GetTotalIncome(Game.City.IncomeSource source);
```

- `public GetTotalTaxIncome() : System.Int32`  

```csharp
public System.Int32 GetTotalTaxIncome();
```

- `private static GetTotalTaxIncome(Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  

```csharp
private static System.Int32 GetTotalTaxIncome(Unity.Collections.NativeArray<System.Int32> income);
```

- `public GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab) : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab);
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage) : System.Void`  

```csharp
public System.Void SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage);
```


## Nested types

- `Game.Simulation.CityServiceBudgetSystem+UpdateDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+ClearServiceDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+CityServiceBudgetJob`  
- `Game.Simulation.CityServiceBudgetSystem+ClearBuildingDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+CollectServiceBuildingBudgetDatasJob`  
- `Game.Simulation.CityServiceBudgetSystem+NetServiceBudgetJob`  
- `Game.Simulation.CityServiceBudgetSystem+TypeHandle`  


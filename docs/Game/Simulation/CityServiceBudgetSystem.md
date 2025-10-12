# Game.Simulation.CityServiceBudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICityServiceBudgetSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GameModeGovernmentSubsidiesSystem`  
- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  
- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  
- `private Unity.Entities.EntityQuery m_ServiceQuery`  
- `private Unity.Entities.EntityQuery m_UpkeepGroup`  
- `private Unity.Entities.EntityQuery m_ServiceObjectQuery`  
- `private Unity.Entities.EntityQuery m_NetUpkeepQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_OutsideTradeParameterQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareFacilityQuery`  
- `private Unity.Entities.EntityQuery m_DeathcareFacilityQuery`  
- `private Unity.Entities.EntityQuery m_GarbageFacilityQuery`  
- `private Unity.Entities.EntityQuery m_FireStationQuery`  
- `private Unity.Entities.EntityQuery m_PoliceStationQuery`  
- `protected Unity.Collections.NativeArray<System.Int32> m_Income`  
- `protected Unity.Collections.NativeArray<System.Int32> m_IncomeTemp`  
- `protected Unity.Collections.NativeArray<System.Int32> m_TotalIncome`  
- `protected Unity.Collections.NativeArray<System.Int32> m_Expenses`  
- `protected Unity.Collections.NativeArray<System.Int32> m_ExpensesTemp`  
- `private System.Int32 m_TotalTaxIncome`  
- `private Unity.Collections.NativeReference<System.Int32> m_TotalTaxes`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> m_CityServiceBudgets`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> m_CityServiceUpkeepIndices`  
- `private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> m_CityServiceUpkeeps`  
- `private Unity.Jobs.JobHandle m_TempArrayDeps`  
- `private Game.Simulation.CityServiceBudgetSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_844909884_0`  

## Constructors

- `public CityServiceBudgetSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddArrayReader(Unity.Jobs.JobHandle deps) : System.Void`  
- `public GetBalance() : System.Int32`  
- `public static GetBalance(Unity.Collections.NativeArray<System.Int32> income, Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  
- `public GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep) : System.Void`  
- `public static GetEstimatedServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32& upkeep, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Mathematics.int2> upkeepIndices, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas) : System.Void`  
- `private static GetEstimatedServiceUpkeep(Game.Simulation.CollectedCityServiceBudgetData data, Unity.Mathematics.int2 indices, System.Int32 budget, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceUpkeepData> upkeeps) : System.Int32`  
- `public GetExpense(Game.City.ExpenseSource source) : System.Int32`  
- `public static GetExpense(Game.City.ExpenseSource source, Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  
- `public GetExpenseArray(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetIncome(Game.City.IncomeSource source) : System.Int32`  
- `public static GetIncome(Game.City.IncomeSource source, Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  
- `public GetIncomeArray(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetMoneyDelta() : System.Int32`  
- `public GetNumberOfServiceBuildings(Unity.Entities.Entity serviceBuildingPrefab) : System.Int32`  
- `public GetServiceBudget(Unity.Entities.Entity servicePrefab) : System.Int32`  
- `public static GetServiceBudget(Unity.Entities.Entity servicePrefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Simulation.CollectedCityServiceBudgetData> budgets, Unity.Entities.Entity budgetEntity, Unity.Entities.BufferLookup<Game.Simulation.ServiceBudgetData> budgetDatas) : System.Int32`  
- `public GetServiceBuildings(Unity.Entities.Entity servicePrefab) : Unity.Entities.Entity[]`  
- `public GetServiceEfficiency(Unity.Entities.Entity servicePrefab, System.Int32 budget) : System.Int32`  
- `public GetTotalExpenses() : System.Int32`  
- `public static GetTotalExpenses(Unity.Collections.NativeArray<System.Int32> expenses) : System.Int32`  
- `public GetTotalIncome() : System.Int32`  
- `public static GetTotalIncome(Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  
- `public GetTotalIncome(Game.City.IncomeSource source) : System.Int32`  
- `public GetTotalTaxIncome() : System.Int32`  
- `private static GetTotalTaxIncome(Unity.Collections.NativeArray<System.Int32> income) : System.Int32`  
- `public GetWorkersAndWorkplaces(Unity.Entities.Entity serviceBuildingPrefab) : Unity.Mathematics.int2`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public SetServiceBudget(Unity.Entities.Entity servicePrefab, System.Int32 percentage) : System.Void`  

## Nested types

- `Game.Simulation.CityServiceBudgetSystem+UpdateDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+ClearServiceDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+CityServiceBudgetJob`  
- `Game.Simulation.CityServiceBudgetSystem+ClearBuildingDataJob`  
- `Game.Simulation.CityServiceBudgetSystem+CollectServiceBuildingBudgetDatasJob`  
- `Game.Simulation.CityServiceBudgetSystem+NetServiceBudgetJob`  
- `Game.Simulation.CityServiceBudgetSystem+TypeHandle`  


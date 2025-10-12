# Game.Simulation.BudgetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IBudgetSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.UInt32 m_LastUpdate`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `protected Unity.Collections.NativeArray<System.Int32> m_Trade`  
- `protected Unity.Collections.NativeArray<System.Int32> m_TradeWorth`  
- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWealth`  
- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWealth`  
- `protected Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWealth`  
- `protected System.Int32 m_TotalTradeWorth`  
- `protected System.Int32 m_TotalTaxIncome`  
- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdCount`  
- `private Unity.Collections.NativeArray<System.Int32> m_ServiceCount`  
- `private Unity.Collections.NativeArray<System.Int32> m_ProcessingCount`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_HouseholdWorkers`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ServiceWorkers`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_ProcessingWorkers`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_CitizenWellbeing`  
- `private Unity.Collections.NativeArray<System.Int32> m_TouristCount`  
- `private Unity.Collections.NativeArray<System.Int32> m_TouristIncome`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_LodgingData`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.BudgetSystem+TypeHandle __TypeHandle`  

## Properties

- `public System.Boolean HasData { get }`  
- `public System.UInt32 LastUpdate { get }`  

## Constructors

- `public BudgetSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetCitizenWellbeing() : Unity.Mathematics.float2`  
- `public GetCompanyCount(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  
- `public GetCompanyWealth(System.Boolean service, Game.Economy.Resource resource) : System.Int32`  
- `public GetCompanyWorkers(System.Boolean service, Game.Economy.Resource resource) : Unity.Mathematics.int2`  
- `public GetHouseholdCount() : System.Int32`  
- `public GetHouseholdWealth() : System.Int32`  
- `public GetHouseholdWorkers() : Unity.Mathematics.int2`  
- `public GetLodgingData() : Unity.Mathematics.int2`  
- `public GetTotalTradeWorth() : System.Int32`  
- `public GetTouristCount() : System.Int32`  
- `public GetTouristIncome() : System.Int32`  
- `public GetTrade(Game.Economy.Resource resource) : System.Int32`  
- `public GetTradeWorth(Game.Economy.Resource resource) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SetTradeWorth(Game.Economy.Resource resource, Game.Prefabs.ResourceData resourceData) : System.Void`  
- `private UpdateData() : System.Void`  
- `private UpdateTotalTradeWorth() : System.Void`  

## Nested types

- `Game.Simulation.BudgetSystem+TypeHandle`  


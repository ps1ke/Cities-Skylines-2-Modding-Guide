# Game.Debug.EconomyDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_AgentQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Debug.BaseDebugSystem+Option m_ResidentialOption`  
- `private Game.Debug.BaseDebugSystem+Option m_CommercialOption`  
- `private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption`  
- `private Game.Debug.BaseDebugSystem+Option m_IndustrialOption`  
- `private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption`  
- `private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption`  
- `private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption`  
- `private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption`  
- `private Game.Debug.BaseDebugSystem+Option m_TradeCostOption`  
- `private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle`  

## Constructors

- `public EconomyDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static PrintAgeDebug() : System.Void`  
- `public static PrintCompanyDebug(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Void`  
- `public static PrintSchoolDebug() : System.Void`  
- `public static PrintTradeDebug(Game.Simulation.ITradeSystem tradeSystem, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Void`  
- `public static RemoveExtraCompanies() : System.Void`  

## Nested types

- `Game.Debug.EconomyDebugSystem+EconomyGizmoJob`  
- `Game.Debug.EconomyDebugSystem+TypeHandle`  


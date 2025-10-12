# Game.UI.InGame.ToolbarBottomUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  
- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding`  
- `private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab`  
- `private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery`  
- `private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_2118611066_0`  
- `private static const System.String kGroup`  

## Constructors

- `public ToolbarBottomUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <OnCreate>b__14_0() : System.String`  
- `private <OnCreate>b__14_1() : System.Int32`  
- `private <OnCreate>b__14_2() : System.Boolean`  
- `private <OnCreate>b__14_3() : Unity.Mathematics.float2`  
- `private <OnCreate>b__14_4() : Unity.Mathematics.float2`  
- `private GetPopulation() : System.Int32`  
- `private GetPopulationDelta() : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SetCityName(System.String name) : System.Void`  

## Nested types

- `Game.UI.InGame.ToolbarBottomUISystem+TypeHandle`  


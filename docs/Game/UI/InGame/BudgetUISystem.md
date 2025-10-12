# Game.UI.InGame.BudgetUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GovernmentSubsidiesSystem`  
- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalIncomeBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalExpensesBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_IncomeItemsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_IncomeValuesBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ExpenseItemsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ExpenseValuesBinding`  
- `private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> m_BudgetsActivations`  
- `private static const System.String kGroup`  

## Constructors

- `public BudgetUISystem()`  

## Methods

- `private <OnCreate>b__14_0() : System.Int32`  
- `private <OnCreate>b__14_1() : System.Int32`  
- `private <OnCreate>b__14_2() : System.Boolean`  
- `private BindExpenseItems(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindExpenseValues(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindIncomeItems(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindIncomeValues(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private GetConfig() : Game.UI.UIEconomyConfigurationPrefab`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  


# Game.UI.InGame.BudgetUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class BudgetUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GovernmentSubsidiesSystem;
    private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalIncomeBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalExpensesBinding;
    private Colossal.UI.Binding.RawValueBinding m_IncomeItemsBinding;
    private Colossal.UI.Binding.RawValueBinding m_IncomeValuesBinding;
    private Colossal.UI.Binding.RawValueBinding m_ExpenseItemsBinding;
    private Colossal.UI.Binding.RawValueBinding m_ExpenseValuesBinding;
    private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> m_BudgetsActivations;
    private static const System.String kGroup;

    public BudgetUISystem();

    private System.Int32 <OnCreate>b__14_0();
    private System.Int32 <OnCreate>b__14_1();
    private System.Boolean <OnCreate>b__14_2();
    private System.Void BindExpenseItems(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindExpenseValues(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindIncomeItems(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindIncomeValues(Colossal.UI.Binding.IJsonWriter writer);
    private Game.UI.UIEconomyConfigurationPrefab GetConfig();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GovernmentSubsidiesSystem`  

```csharp
private Game.Simulation.GameModeGovernmentSubsidiesSystem m_GovernmentSubsidiesSystem;
```

- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalIncomeBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalIncomeBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalExpensesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalExpensesBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_IncomeItemsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IncomeItemsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_IncomeValuesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IncomeValuesBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ExpenseItemsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ExpenseItemsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ExpenseValuesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ExpenseValuesBinding;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> m_BudgetsActivations`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> m_BudgetsActivations;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public BudgetUISystem()`  

```csharp
public BudgetUISystem();
```


## Methods

- `private <OnCreate>b__14_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_0();
```

- `private <OnCreate>b__14_1() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_1();
```

- `private <OnCreate>b__14_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__14_2();
```

- `private BindExpenseItems(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindExpenseItems(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindExpenseValues(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindExpenseValues(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindIncomeItems(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindIncomeItems(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindIncomeValues(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindIncomeValues(Colossal.UI.Binding.IJsonWriter writer);
```

- `private GetConfig() : Game.UI.UIEconomyConfigurationPrefab`  

```csharp
private Game.UI.UIEconomyConfigurationPrefab GetConfig();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```



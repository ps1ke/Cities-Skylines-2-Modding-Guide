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
[Preserve]
	public BudgetUISystem()
	{
	}
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
private void BindExpenseItems(IJsonWriter writer)
	{
		UIEconomyConfigurationPrefab config = GetConfig();
		writer.ArrayBegin(config.m_ExpenseItems.Length);
		BudgetItem<ExpenseSource>[] expenseItems = config.m_ExpenseItems;
		foreach (BudgetItem<ExpenseSource> budgetItem in expenseItems)
		{
			writer.TypeBegin("Game.UI.InGame.BudgetItem");
			writer.PropertyName("id");
			writer.Write(budgetItem.m_ID);
			writer.PropertyName("color");
			writer.Write(budgetItem.m_Color);
			writer.PropertyName("icon");
			writer.Write(budgetItem.m_Icon);
			writer.PropertyName("active");
			writer.Write(!m_BudgetsActivations.ContainsKey(budgetItem.m_ID) || m_BudgetsActivations[budgetItem.m_ID]());
			writer.PropertyName("sources");
			writer.ArrayBegin(budgetItem.m_Sources.Length);
			ExpenseSource[] sources = budgetItem.m_Sources;
			foreach (ExpenseSource expenseSource in sources)
			{
				writer.TypeBegin("Game.UI.InGame.BudgetSource");
				writer.PropertyName("id");
				writer.Write(Enum.GetName(typeof(ExpenseSource), expenseSource));
				writer.PropertyName("index");
				writer.Write((int)expenseSource);
				writer.TypeEnd();
			}
			writer.ArrayEnd();
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `private BindExpenseValues(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindExpenseValues(IJsonWriter writer)
	{
		writer.ArrayBegin(15u);
		for (int i = 0; i < 15; i++)
		{
			writer.Write(-m_CityServiceBudgetSystem.GetExpense((ExpenseSource)i));
		}
		writer.ArrayEnd();
	}
```

- `private BindIncomeItems(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindIncomeItems(IJsonWriter writer)
	{
		UIEconomyConfigurationPrefab config = GetConfig();
		writer.ArrayBegin(config.m_IncomeItems.Length);
		BudgetItem<IncomeSource>[] incomeItems = config.m_IncomeItems;
		foreach (BudgetItem<IncomeSource> budgetItem in incomeItems)
		{
			writer.TypeBegin("Game.UI.InGame.BudgetItem");
			writer.PropertyName("id");
			writer.Write(budgetItem.m_ID);
			writer.PropertyName("color");
			writer.Write(budgetItem.m_Color);
			writer.PropertyName("icon");
			writer.Write(budgetItem.m_Icon);
			writer.PropertyName("active");
			writer.Write(!m_BudgetsActivations.ContainsKey(budgetItem.m_ID) || m_BudgetsActivations[budgetItem.m_ID]());
			writer.PropertyName("sources");
			writer.ArrayBegin(budgetItem.m_Sources.Length);
			IncomeSource[] sources = budgetItem.m_Sources;
			foreach (IncomeSource incomeSource in sources)
			{
				writer.TypeBegin("Game.UI.InGame.BudgetSource");
				writer.PropertyName("id");
				writer.Write(Enum.GetName(typeof(IncomeSource), incomeSource));
				writer.PropertyName("index");
				writer.Write((int)incomeSource);
				writer.TypeEnd();
			}
			writer.ArrayEnd();
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `private BindIncomeValues(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindIncomeValues(IJsonWriter writer)
	{
		writer.ArrayBegin(14u);
		for (int i = 0; i < 14; i++)
		{
			writer.Write(m_CityServiceBudgetSystem.GetIncome((IncomeSource)i));
		}
		writer.ArrayEnd();
	}
```

- `private GetConfig() : Game.UI.UIEconomyConfigurationPrefab`  

```csharp
private UIEconomyConfigurationPrefab GetConfig()
	{
		return m_PrefabSystem.GetSingletonPrefab<UIEconomyConfigurationPrefab>(m_ConfigQuery);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CityServiceBudgetSystem = base.World.GetOrCreateSystemManaged<CityServiceBudgetSystem>();
		m_GovernmentSubsidiesSystem = base.World.GetOrCreateSystemManaged<GameModeGovernmentSubsidiesSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_MapTilePurchaseSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UIEconomyConfigurationData>());
		m_BudgetsActivations = new Dictionary<string, Func<bool>>
		{
			{ "Government", m_GovernmentSubsidiesSystem.GetGovernmentSubsidiesEnabled },
			{
				"Loan Interest",
				() => !m_CityConfigurationSystem.unlimitedMoney
			},
			{ "Tile Upkeep", m_MapTilePurchaseSystem.GetMapTileUpkeepEnabled }
		};
		AddBinding(m_TotalIncomeBinding = new GetterValueBinding<int>("budget", "totalIncome", () => m_CityServiceBudgetSystem.GetTotalIncome()));
		AddBinding(m_TotalExpensesBinding = new GetterValueBinding<int>("budget", "totalExpenses", () => m_CityServiceBudgetSystem.GetTotalExpenses()));
		AddBinding(m_IncomeItemsBinding = new RawValueBinding("budget", "incomeItems", BindIncomeItems));
		AddBinding(m_IncomeValuesBinding = new RawValueBinding("budget", "incomeValues", BindIncomeValues));
		AddBinding(m_ExpenseItemsBinding = new RawValueBinding("budget", "expenseItems", BindExpenseItems));
		AddBinding(m_ExpenseValuesBinding = new RawValueBinding("budget", "expenseValues", BindExpenseValues));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_TotalIncomeBinding.Update();
		m_TotalExpensesBinding.Update();
		m_IncomeValuesBinding.Update();
		m_ExpenseValuesBinding.Update();
	}
```



# Game.UI.UIEconomyConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIEconomyConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.UI.BudgetItem<Game.City.IncomeSource>[] m_IncomeItems;
    public Game.UI.BudgetItem<Game.City.ExpenseSource>[] m_ExpenseItems;

    public UIEconomyConfigurationPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.UI.BudgetItem<Game.City.IncomeSource>[] m_IncomeItems`  

```csharp
public Game.UI.BudgetItem<Game.City.IncomeSource>[] m_IncomeItems;
```

- `public Game.UI.BudgetItem<Game.City.ExpenseSource>[] m_ExpenseItems`  

```csharp
public Game.UI.BudgetItem<Game.City.ExpenseSource>[] m_ExpenseItems;
```


## Constructors

- `public UIEconomyConfigurationPrefab()`  

```csharp
public UIEconomyConfigurationPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<UIEconomyConfigurationData>());
	}
```



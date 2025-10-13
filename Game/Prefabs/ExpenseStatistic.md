# Game.Prefabs.ExpenseStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExpenseStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ExpenseSourceInfo[] m_Expenses;

    public ExpenseStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.ExpenseSourceInfo[] m_Expenses`  

```csharp
public Game.Prefabs.ExpenseSourceInfo[] m_Expenses;
```


## Constructors

- `public ExpenseStatistic()`  

```csharp
public ExpenseStatistic();
```


## Methods

- `public virtual GetParameterName(System.Int32 parameter) : System.String`  

```csharp
public override string GetParameterName(int parameter)
	{
		return Enum.GetName(typeof(ExpenseSource), parameter);
	}
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public override IEnumerable<StatisticParameterData> GetParameters()
	{
		if (m_Expenses != null)
		{
			int i = 0;
			while (i < m_Expenses.Length)
			{
				yield return new StatisticParameterData((int)m_Expenses[i].m_ExpenseSource, m_Expenses[i].m_Color);
				int num = i + 1;
				i = num;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.ExpenseStatistic+<GetParameters>d__1`  


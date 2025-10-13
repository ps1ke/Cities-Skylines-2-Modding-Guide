# Game.Prefabs.IncomeStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class IncomeStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.IncomeSourceInfo[] m_Incomes;

    public IncomeStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.IncomeSourceInfo[] m_Incomes`  

```csharp
public Game.Prefabs.IncomeSourceInfo[] m_Incomes;
```


## Constructors

- `public IncomeStatistic()`  

```csharp
public IncomeStatistic();
```


## Methods

- `public virtual GetParameterName(System.Int32 parameter) : System.String`  

```csharp
public override string GetParameterName(int parameter)
	{
		return Enum.GetName(typeof(IncomeSource), parameter);
	}
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public override IEnumerable<StatisticParameterData> GetParameters()
	{
		if (m_Incomes != null)
		{
			int i = 0;
			while (i < m_Incomes.Length)
			{
				yield return new StatisticParameterData((int)m_Incomes[i].m_IncomeSource, m_Incomes[i].m_Color);
				int num = i + 1;
				i = num;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.IncomeStatistic+<GetParameters>d__1`  


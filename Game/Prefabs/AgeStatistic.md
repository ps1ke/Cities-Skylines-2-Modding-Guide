# Game.Prefabs.AgeStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AgeStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PopulationAgeGroupInfo[] m_AgeGroups;

    public AgeStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.PopulationAgeGroupInfo[] m_AgeGroups`  

```csharp
public Game.Prefabs.PopulationAgeGroupInfo[] m_AgeGroups;
```


## Constructors

- `public AgeStatistic()`  

```csharp
public AgeStatistic();
```


## Methods

- `public virtual GetParameterName(System.Int32 parameter) : System.String`  

```csharp
public override string GetParameterName(int parameter)
	{
		return Enum.GetName(typeof(CitizenAge), parameter);
	}
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public override IEnumerable<StatisticParameterData> GetParameters()
	{
		if (m_AgeGroups != null)
		{
			int i = 0;
			while (i < m_AgeGroups.Length)
			{
				yield return new StatisticParameterData((int)m_AgeGroups[i].m_Group, m_AgeGroups[i].m_Color);
				int num = i + 1;
				i = num;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.AgeStatistic+<GetParameters>d__1`  


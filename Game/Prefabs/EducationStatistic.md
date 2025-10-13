# Game.Prefabs.EducationStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EducationStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.EducationLevelInfo[] m_Levels;

    public EducationStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.EducationLevelInfo[] m_Levels`  

```csharp
public Game.Prefabs.EducationLevelInfo[] m_Levels;
```


## Constructors

- `public EducationStatistic()`  

```csharp
public EducationStatistic();
```


## Methods

- `public virtual GetParameterName(System.Int32 parameter) : System.String`  

```csharp
public override string GetParameterName(int parameter)
	{
		return Enum.GetName(typeof(CitizenEducationLevel), parameter);
	}
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public override IEnumerable<StatisticParameterData> GetParameters()
	{
		if (m_Levels != null)
		{
			int i = 0;
			while (i < m_Levels.Length)
			{
				yield return new StatisticParameterData((int)m_Levels[i].m_EducationLevel, m_Levels[i].m_Color);
				int num = i + 1;
				i = num;
			}
		}
	}
```


## Nested types

- `Game.Prefabs.EducationStatistic+<GetParameters>d__1`  


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
public virtual System.String GetParameterName(System.Int32 parameter);
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
```


## Nested types

- `Game.Prefabs.IncomeStatistic+<GetParameters>d__1`  


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
public virtual System.String GetParameterName(System.Int32 parameter);
```

- `public virtual GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
```


## Nested types

- `Game.Prefabs.ExpenseStatistic+<GetParameters>d__1`  


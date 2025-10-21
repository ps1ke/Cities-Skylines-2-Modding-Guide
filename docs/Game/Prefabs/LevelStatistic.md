# Game.Prefabs.LevelStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LevelStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.LevelInfo[] m_Levels;

    public LevelStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.LevelInfo[] m_Levels`  

```csharp
public Game.Prefabs.LevelInfo[] m_Levels;
```


## Constructors

- `public LevelStatistic()`  

```csharp
public LevelStatistic();
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

- `Game.Prefabs.LevelStatistic+<GetParameters>d__1`  


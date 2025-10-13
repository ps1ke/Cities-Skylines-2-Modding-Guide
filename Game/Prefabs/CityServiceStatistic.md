# Game.Prefabs.CityServiceStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CityServiceStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.CityServiceInfo[] m_CityServices;

    public CityServiceStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.CityServiceInfo[] m_CityServices`  

```csharp
public Game.Prefabs.CityServiceInfo[] m_CityServices;
```


## Constructors

- `public CityServiceStatistic()`  

```csharp
public CityServiceStatistic();
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

- `Game.Prefabs.CityServiceStatistic+<GetParameters>d__1`  


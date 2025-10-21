# Game.Prefabs.PassengerStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ParametricStatistic`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PassengerStatistic : Game.Prefabs.ParametricStatistic, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PassengerTypeInfo[] m_PassengerTypes;

    public PassengerStatistic();

    public virtual System.String GetParameterName(System.Int32 parameter);
    public virtual System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
}
```


## Fields

- `public Game.Prefabs.PassengerTypeInfo[] m_PassengerTypes`  

```csharp
public Game.Prefabs.PassengerTypeInfo[] m_PassengerTypes;
```


## Constructors

- `public PassengerStatistic()`  

```csharp
public PassengerStatistic();
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

- `Game.Prefabs.PassengerStatistic+<GetParameters>d__1`  


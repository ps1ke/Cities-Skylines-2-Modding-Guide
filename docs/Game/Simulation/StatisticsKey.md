# Game.Simulation.CityStatisticsSystem+StatisticsKey

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Simulation.CityStatisticsSystem+StatisticsKey>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct StatisticsKey : System.IEquatable<Game.Simulation.CityStatisticsSystem+StatisticsKey>
{
    private readonly Game.City.StatisticType <type>k__BackingField;
    private readonly System.Int32 <parameter>k__BackingField;

    public Game.City.StatisticType type { get; }
    public System.Int32 parameter { get; }

    public StatisticsKey(Game.City.StatisticType type, System.Int32 parameter);

    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Game.Simulation.CityStatisticsSystem+StatisticsKey other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private readonly Game.City.StatisticType <type>k__BackingField`  

```csharp
private readonly Game.City.StatisticType <type>k__BackingField;
```

- `private readonly System.Int32 <parameter>k__BackingField`  

```csharp
private readonly System.Int32 <parameter>k__BackingField;
```


## Properties

- `public Game.City.StatisticType type { get }`  

```csharp
public Game.City.StatisticType type { get; }
```

- `public System.Int32 parameter { get }`  

```csharp
public System.Int32 parameter { get; }
```


## Constructors

- `public StatisticsKey(Game.City.StatisticType type, System.Int32 parameter)`  

```csharp
public StatisticsKey(Game.City.StatisticType type, System.Int32 parameter);
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Game.Simulation.CityStatisticsSystem+StatisticsKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Simulation.CityStatisticsSystem+StatisticsKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```



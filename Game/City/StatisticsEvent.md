# Game.City.StatisticsEvent

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public sealed struct StatisticsEvent : Colossal.Serialization.Entities.ISerializable
{
    public Game.City.StatisticType m_Statistic;
    public System.Int32 m_Parameter;
    public System.Single m_Change;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.City.StatisticType m_Statistic`  

```csharp
public Game.City.StatisticType m_Statistic;
```

- `public System.Int32 m_Parameter`  

```csharp
public System.Int32 m_Parameter;
```

- `public System.Single m_Change`  

```csharp
public System.Single m_Change;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



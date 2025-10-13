# Game.City.CityStatistic

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CityStatistic : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public System.Double m_Value;
    public System.Double m_TotalValue;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Double m_Value`  

```csharp
public System.Double m_Value;
```

- `public System.Double m_TotalValue`  

```csharp
public System.Double m_TotalValue;
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



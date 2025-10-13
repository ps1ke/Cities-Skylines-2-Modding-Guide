# Game.Events.EventJournalCityEffect

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct EventJournalCityEffect : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.Events.EventCityEffectTrackingType m_Type;
    public System.Int32 m_StartValue;
    public System.Int32 m_Value;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Events.EventCityEffectTrackingType m_Type`  

```csharp
public Game.Events.EventCityEffectTrackingType m_Type;
```

- `public System.Int32 m_StartValue`  

```csharp
public System.Int32 m_StartValue;
```

- `public System.Int32 m_Value`  

```csharp
public System.Int32 m_Value;
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



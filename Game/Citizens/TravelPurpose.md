# Game.Citizens.TravelPurpose

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TravelPurpose : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Citizens.Purpose m_Purpose;
    public System.Int32 m_Data;
    public Game.Economy.Resource m_Resource;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Citizens.Purpose m_Purpose`  

```csharp
public Game.Citizens.Purpose m_Purpose;
```

- `public System.Int32 m_Data`  

```csharp
public System.Int32 m_Data;
```

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
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



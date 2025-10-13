# Game.Buildings.WaterConsumer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterConsumer : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Pollution;
    public System.Int32 m_WantedConsumption;
    public System.Int32 m_FulfilledFresh;
    public System.Int32 m_FulfilledSewage;
    public System.Byte m_FreshCooldownCounter;
    public System.Byte m_SewageCooldownCounter;
    public Game.Buildings.WaterConsumerFlags m_Flags;

    public System.Boolean waterConnected { get; }
    public System.Boolean sewageConnected { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Pollution`  

```csharp
public System.Single m_Pollution;
```

- `public System.Int32 m_WantedConsumption`  

```csharp
public System.Int32 m_WantedConsumption;
```

- `public System.Int32 m_FulfilledFresh`  

```csharp
public System.Int32 m_FulfilledFresh;
```

- `public System.Int32 m_FulfilledSewage`  

```csharp
public System.Int32 m_FulfilledSewage;
```

- `public System.Byte m_FreshCooldownCounter`  

```csharp
public System.Byte m_FreshCooldownCounter;
```

- `public System.Byte m_SewageCooldownCounter`  

```csharp
public System.Byte m_SewageCooldownCounter;
```

- `public Game.Buildings.WaterConsumerFlags m_Flags`  

```csharp
public Game.Buildings.WaterConsumerFlags m_Flags;
```


## Properties

- `public System.Boolean waterConnected { get }`  

```csharp
public System.Boolean waterConnected { get; }
```

- `public System.Boolean sewageConnected { get }`  

```csharp
public System.Boolean sewageConnected { get; }
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



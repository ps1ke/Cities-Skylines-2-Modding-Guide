# Game.Buildings.ElectricityConsumer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ElectricityConsumer : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_WantedConsumption;
    public System.Int32 m_FulfilledConsumption;
    public System.Int16 m_CooldownCounter;
    public Game.Buildings.ElectricityConsumerFlags m_Flags;

    public System.Boolean electricityConnected { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_WantedConsumption`  

```csharp
public System.Int32 m_WantedConsumption;
```

- `public System.Int32 m_FulfilledConsumption`  

```csharp
public System.Int32 m_FulfilledConsumption;
```

- `public System.Int16 m_CooldownCounter`  

```csharp
public System.Int16 m_CooldownCounter;
```

- `public Game.Buildings.ElectricityConsumerFlags m_Flags`  

```csharp
public Game.Buildings.ElectricityConsumerFlags m_Flags;
```


## Properties

- `public System.Boolean electricityConnected { get }`  

```csharp
public System.Boolean electricityConnected { get; }
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



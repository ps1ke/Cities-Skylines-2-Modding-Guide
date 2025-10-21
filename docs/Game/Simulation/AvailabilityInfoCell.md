# Game.Simulation.AvailabilityInfoCell

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.Simulation.IAvailabilityInfoCell`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AvailabilityInfoCell : Game.Simulation.IAvailabilityInfoCell, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float4 m_AvailabilityInfo;

    public System.Void AddAttractiveness(System.Single amount);
    public System.Void AddConsumers(System.Single amount);
    public System.Void AddServices(System.Single amount);
    public System.Void AddWorkplaces(System.Single amount);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float4 m_AvailabilityInfo`  

```csharp
public Unity.Mathematics.float4 m_AvailabilityInfo;
```


## Methods

- `public AddAttractiveness(System.Single amount) : System.Void`  

```csharp
public System.Void AddAttractiveness(System.Single amount);
```

- `public AddConsumers(System.Single amount) : System.Void`  

```csharp
public System.Void AddConsumers(System.Single amount);
```

- `public AddServices(System.Single amount) : System.Void`  

```csharp
public System.Void AddServices(System.Single amount);
```

- `public AddWorkplaces(System.Single amount) : System.Void`  

```csharp
public System.Void AddWorkplaces(System.Single amount);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



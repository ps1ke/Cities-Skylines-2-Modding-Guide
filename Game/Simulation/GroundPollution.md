# Game.Simulation.GroundPollution

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.Simulation.IPollution`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GroundPollution : Game.Simulation.IPollution, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Int16 m_Pollution;

    public System.Void Add(System.Int16 amount);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int16 m_Pollution`  

```csharp
public System.Int16 m_Pollution;
```


## Methods

- `public Add(System.Int16 amount) : System.Void`  

```csharp
public System.Void Add(System.Int16 amount);
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



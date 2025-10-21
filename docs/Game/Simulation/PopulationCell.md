# Game.Simulation.PopulationCell

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.Simulation.IPopulationCell`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PopulationCell : Game.Simulation.IPopulationCell, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Population;

    public System.Void Add(System.Single amount);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single Get();
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Population`  

```csharp
public System.Single m_Population;
```


## Methods

- `public Add(System.Single amount) : System.Void`  

```csharp
public System.Void Add(System.Single amount);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Get() : System.Single`  

```csharp
public System.Single Get();
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



# Game.Simulation.ZoneAmbienceCell

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ZoneAmbienceCell : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Game.Simulation.ZoneAmbiences m_Accumulator;
    public Game.Simulation.ZoneAmbiences m_Value;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Simulation.ZoneAmbiences m_Accumulator`  

```csharp
public Game.Simulation.ZoneAmbiences m_Accumulator;
```

- `public Game.Simulation.ZoneAmbiences m_Value`  

```csharp
public Game.Simulation.ZoneAmbiences m_Value;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		return m_Accumulator.GetStride(context) + m_Value.GetStride(context);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



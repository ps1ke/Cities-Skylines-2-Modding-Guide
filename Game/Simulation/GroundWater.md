# Game.Simulation.GroundWater

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GroundWater : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Int16 m_Amount;
    public System.Int16 m_Polluted;
    public System.Int16 m_Max;

    public System.Void Consume(System.Int32 amount);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int16 m_Amount`  

```csharp
public System.Int16 m_Amount;
```

- `public System.Int16 m_Polluted`  

```csharp
public System.Int16 m_Polluted;
```

- `public System.Int16 m_Max`  

```csharp
public System.Int16 m_Max;
```


## Methods

- `public Consume(System.Int32 amount) : System.Void`  

```csharp
public void Consume(int amount)
	{
		if (m_Amount > 0)
		{
			float num = (float)m_Polluted / (float)m_Amount;
			m_Amount -= (short)math.clamp(amount, 0, m_Amount);
			m_Polluted = (short)math.clamp(math.round(num * (float)m_Amount), 0f, m_Amount);
		}
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		return 6;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



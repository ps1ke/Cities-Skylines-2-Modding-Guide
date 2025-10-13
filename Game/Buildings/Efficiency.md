# Game.Buildings.Efficiency

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`, `System.IComparable<Game.Buildings.Efficiency>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Efficiency : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable, System.IComparable<Game.Buildings.Efficiency>
{
    public Game.Buildings.EfficiencyFactor m_Factor;
    public System.Single m_Efficiency;

    public Efficiency(Game.Buildings.EfficiencyFactor factor, System.Single efficiency);

    public System.Int32 CompareTo(Game.Buildings.Efficiency other);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Buildings.EfficiencyFactor m_Factor`  

```csharp
public Game.Buildings.EfficiencyFactor m_Factor;
```

- `public System.Single m_Efficiency`  

```csharp
public System.Single m_Efficiency;
```


## Constructors

- `public Efficiency(Game.Buildings.EfficiencyFactor factor, System.Single efficiency)`  

```csharp
public Efficiency(EfficiencyFactor factor, float efficiency)
	{
		m_Factor = factor;
		m_Efficiency = efficiency;
	}
```


## Methods

- `public CompareTo(Game.Buildings.Efficiency other) : System.Int32`  

```csharp
public int CompareTo(Efficiency other)
	{
		int num = other.m_Efficiency.CompareTo(m_Efficiency);
		if (num != 0)
		{
			return num;
		}
		return m_Factor.CompareTo(other.m_Factor);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



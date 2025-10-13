# Game.Simulation.NaturalResourceCell

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NaturalResourceCell : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Game.Simulation.NaturalResourceAmount m_Fertility;
    public Game.Simulation.NaturalResourceAmount m_Ore;
    public Game.Simulation.NaturalResourceAmount m_Oil;
    public Game.Simulation.NaturalResourceAmount m_Fish;

    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Mathematics.float4 GetBaseResources();
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public Unity.Mathematics.float4 GetUsedResources();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Simulation.NaturalResourceAmount m_Fertility`  

```csharp
public Game.Simulation.NaturalResourceAmount m_Fertility;
```

- `public Game.Simulation.NaturalResourceAmount m_Ore`  

```csharp
public Game.Simulation.NaturalResourceAmount m_Ore;
```

- `public Game.Simulation.NaturalResourceAmount m_Oil`  

```csharp
public Game.Simulation.NaturalResourceAmount m_Oil;
```

- `public Game.Simulation.NaturalResourceAmount m_Fish`  

```csharp
public Game.Simulation.NaturalResourceAmount m_Fish;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetBaseResources() : Unity.Mathematics.float4`  

```csharp
public float4 GetBaseResources()
	{
		return new float4((int)m_Fertility.m_Base, (int)m_Ore.m_Base, (int)m_Oil.m_Base, (int)m_Fish.m_Base);
	}
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		return m_Fertility.GetStride(context) + m_Ore.GetStride(context) + m_Oil.GetStride(context);
	}
```

- `public GetUsedResources() : Unity.Mathematics.float4`  

```csharp
public float4 GetUsedResources()
	{
		return new float4((int)m_Fertility.m_Used, (int)m_Ore.m_Used, (int)m_Oil.m_Used, (int)m_Oil.m_Used);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



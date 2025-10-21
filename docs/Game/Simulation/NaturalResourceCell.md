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
public Unity.Mathematics.float4 GetBaseResources();
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public GetUsedResources() : Unity.Mathematics.float4`  

```csharp
public Unity.Mathematics.float4 GetUsedResources();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



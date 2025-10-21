# Game.Simulation.Wind

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Wind : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float2 m_Wind;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public static Unity.Mathematics.float2 SampleWind(Game.Simulation.CellMapData<Game.Simulation.Wind> wind, Unity.Mathematics.float3 position);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float2 m_Wind`  

```csharp
public Unity.Mathematics.float2 m_Wind;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public static SampleWind(Game.Simulation.CellMapData<Game.Simulation.Wind> wind, Unity.Mathematics.float3 position) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 SampleWind(Game.Simulation.CellMapData<Game.Simulation.Wind> wind, Unity.Mathematics.float3 position);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



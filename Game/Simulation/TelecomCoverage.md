# Game.Simulation.TelecomCoverage

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TelecomCoverage : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Byte m_SignalStrength;
    public System.Byte m_NetworkLoad;

    public System.Int32 networkQuality { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public static System.Single SampleNetworkQuality(Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> coverage, Unity.Mathematics.float3 position);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Byte m_SignalStrength`  

```csharp
public System.Byte m_SignalStrength;
```

- `public System.Byte m_NetworkLoad`  

```csharp
public System.Byte m_NetworkLoad;
```


## Properties

- `public System.Int32 networkQuality { get }`  

```csharp
public System.Int32 networkQuality { get; }
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

- `public static SampleNetworkQuality(Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> coverage, Unity.Mathematics.float3 position) : System.Single`  

```csharp
public static System.Single SampleNetworkQuality(Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> coverage, Unity.Mathematics.float3 position);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



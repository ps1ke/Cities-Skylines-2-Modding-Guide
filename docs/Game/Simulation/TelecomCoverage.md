# Game.Simulation.TelecomCoverage

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Byte m_SignalStrength`  
- `public System.Byte m_NetworkLoad`  

## Properties

- `public System.Int32 networkQuality { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  
- `public static SampleNetworkQuality(Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> coverage, Unity.Mathematics.float3 position) : System.Single`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


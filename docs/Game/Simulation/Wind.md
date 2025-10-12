# Game.Simulation.Wind

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Mathematics.float2 m_Wind`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  
- `public static SampleWind(Game.Simulation.CellMapData<Game.Simulation.Wind> wind, Unity.Mathematics.float3 position) : Unity.Mathematics.float2`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


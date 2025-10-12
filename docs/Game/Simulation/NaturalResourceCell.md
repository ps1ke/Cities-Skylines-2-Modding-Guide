# Game.Simulation.NaturalResourceCell

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Simulation.NaturalResourceAmount m_Fertility`  
- `public Game.Simulation.NaturalResourceAmount m_Ore`  
- `public Game.Simulation.NaturalResourceAmount m_Oil`  
- `public Game.Simulation.NaturalResourceAmount m_Fish`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetBaseResources() : Unity.Mathematics.float4`  
- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  
- `public GetUsedResources() : Unity.Mathematics.float4`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


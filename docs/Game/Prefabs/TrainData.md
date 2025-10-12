# Game.Prefabs.TrainData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.Net.TrackTypes m_TrackType`  
- `public Game.Vehicles.EnergyTypes m_EnergyType`  
- `public Game.Prefabs.TrainFlags m_TrainFlags`  
- `public System.Single m_MaxSpeed`  
- `public System.Single m_Acceleration`  
- `public System.Single m_Braking`  
- `public Unity.Mathematics.float2 m_Turning`  
- `public Unity.Mathematics.float2 m_BogieOffsets`  
- `public Unity.Mathematics.float2 m_AttachOffsets`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


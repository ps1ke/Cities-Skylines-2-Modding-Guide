# Game.Net.CarLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_AccessRestriction`  
- `public Game.Net.CarLaneFlags m_Flags`  
- `public System.Single m_DefaultSpeedLimit`  
- `public System.Single m_SpeedLimit`  
- `public System.Single m_Curviness`  
- `public System.UInt16 m_CarriagewayGroup`  
- `public System.Byte m_BlockageStart`  
- `public System.Byte m_BlockageEnd`  
- `public System.Byte m_CautionStart`  
- `public System.Byte m_CautionEnd`  
- `public System.Byte m_FlowOffset`  
- `public System.Byte m_LaneCrossCount`  

## Properties

- `public Colossal.Mathematics.Bounds1 blockageBounds { get }`  
- `public Colossal.Mathematics.Bounds1 cautionBounds { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


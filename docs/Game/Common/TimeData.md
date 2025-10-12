# Game.Common.TimeData

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.UInt32 m_FirstFrame`  
- `public System.Int32 m_StartingYear`  
- `public System.Byte m_StartingMonth`  
- `public System.Byte m_StartingHour`  
- `public System.Byte m_StartingMinutes`  

## Properties

- `public System.Single TimeOffset { get; set }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetDateOffset(System.Int32 daysPerYear) : System.Single`  
- `public static GetSingleton(Unity.Entities.EntityQuery query) : Game.Common.TimeData`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  


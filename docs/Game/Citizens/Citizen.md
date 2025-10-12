# Game.Citizens.Citizen

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.UInt16 m_PseudoRandom`  
- `public Game.Citizens.CitizenFlags m_State`  
- `public System.Byte m_WellBeing`  
- `public System.Byte m_Health`  
- `public System.Byte m_LeisureCounter`  
- `public System.Byte m_PenaltyCounter`  
- `public System.Int32 m_UnemploymentCounter`  
- `public System.Int16 m_BirthDay`  

## Properties

- `public System.Int32 Happiness { get }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetAge() : Game.Citizens.CitizenAge`  
- `public GetAgeInDays(System.UInt32 simulationFrame, Game.Common.TimeData timeData) : System.Single`  
- `public GetEducationLevel() : System.Int32`  
- `public GetFailedEducationCount() : System.Int32`  
- `public GetPseudoRandom(Game.Citizens.CitizenPseudoRandom reason) : Unity.Mathematics.Random`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetAge(Game.Citizens.CitizenAge newAge) : System.Void`  
- `public SetEducationLevel(System.Int32 level) : System.Void`  
- `public SetFailedEducationCount(System.Int32 fails) : System.Void`  


# Game.Vehicles.Taxi

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_TargetRequest`  
- `public Game.Vehicles.TaxiFlags m_State`  
- `public System.Single m_PathElementTime`  
- `public System.Single m_StartDistance`  
- `public System.Single m_MaxBoardingDistance`  
- `public System.Single m_MinWaitingDistance`  
- `public System.Int32 m_ExtraPathElementCount`  
- `public System.UInt16 m_NextStartingFee`  
- `public System.UInt16 m_CurrentFee`  

## Constructors

- `public Taxi(Game.Vehicles.TaxiFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


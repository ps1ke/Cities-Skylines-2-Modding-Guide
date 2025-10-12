# Game.Prefabs.PoliceCarData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_CriminalCapacity`  
- `public System.Single m_CrimeReductionRate`  
- `public System.UInt32 m_ShiftDuration`  
- `public Game.Prefabs.PolicePurpose m_PurposeMask`  

## Constructors

- `public PoliceCarData(System.Int32 criminalCapacity, System.Single crimeReductionRate, System.UInt32 shiftDuration, Game.Prefabs.PolicePurpose purposeMask)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


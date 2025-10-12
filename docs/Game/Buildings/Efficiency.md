# Game.Buildings.Efficiency

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`, `System.IComparable<Game.Buildings.Efficiency>`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Game.Buildings.EfficiencyFactor m_Factor`  
- `public System.Single m_Efficiency`  

## Constructors

- `public Efficiency(Game.Buildings.EfficiencyFactor factor, System.Single efficiency)`  

## Methods

- `public CompareTo(Game.Buildings.Efficiency other) : System.Int32`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


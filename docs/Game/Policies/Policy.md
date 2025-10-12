# Game.Policies.Policy

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Entities.Entity m_Policy`  
- `public Game.Policies.PolicyFlags m_Flags`  
- `public System.Single m_Adjustment`  

## Constructors

- `public Policy(Unity.Entities.Entity policy, Game.Policies.PolicyFlags flags, System.Single adjustment)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


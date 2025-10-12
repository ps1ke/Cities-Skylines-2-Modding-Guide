# Game.Objects.Attached

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Parent`  
- `public Unity.Entities.Entity m_OldParent`  
- `public System.Single m_CurvePosition`  

## Constructors

- `public Attached(Unity.Entities.Entity parent, Unity.Entities.Entity oldParent, System.Single curvePosition)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


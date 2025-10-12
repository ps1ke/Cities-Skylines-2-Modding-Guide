# Game.Buildings.MailProducer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_MailRequest`  
- `public System.UInt16 m_SendingMail`  
- `public System.UInt16 m_ReceivingMail`  
- `public System.Byte m_DispatchIndex`  

## Properties

- `public System.Int32 receivingMail { get; set }`  
- `public System.Boolean mailDelivered { get; set }`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  


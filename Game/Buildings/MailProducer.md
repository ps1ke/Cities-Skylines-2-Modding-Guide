# Game.Buildings.MailProducer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct MailProducer : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_MailRequest;
    public System.UInt16 m_SendingMail;
    public System.UInt16 m_ReceivingMail;
    public System.Byte m_DispatchIndex;

    public System.Int32 receivingMail { get; set; }
    public System.Boolean mailDelivered { get; set; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_MailRequest`  

```csharp
public Unity.Entities.Entity m_MailRequest;
```

- `public System.UInt16 m_SendingMail`  

```csharp
public System.UInt16 m_SendingMail;
```

- `public System.UInt16 m_ReceivingMail`  

```csharp
public System.UInt16 m_ReceivingMail;
```

- `public System.Byte m_DispatchIndex`  

```csharp
public System.Byte m_DispatchIndex;
```


## Properties

- `public System.Int32 receivingMail { get; set }`  

```csharp
public System.Int32 receivingMail { get; set; }
```

- `public System.Boolean mailDelivered { get; set }`  

```csharp
public System.Boolean mailDelivered { get; set; }
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



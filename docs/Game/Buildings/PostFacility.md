# Game.Buildings.PostFacility

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PostFacility : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_MailDeliverRequest;
    public Unity.Entities.Entity m_MailReceiveRequest;
    public Unity.Entities.Entity m_TargetRequest;
    public System.Single m_AcceptMailPriority;
    public System.Single m_DeliverMailPriority;
    public Game.Buildings.PostFacilityFlags m_Flags;
    public System.Byte m_ProcessingFactor;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_MailDeliverRequest`  

```csharp
public Unity.Entities.Entity m_MailDeliverRequest;
```

- `public Unity.Entities.Entity m_MailReceiveRequest`  

```csharp
public Unity.Entities.Entity m_MailReceiveRequest;
```

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public System.Single m_AcceptMailPriority`  

```csharp
public System.Single m_AcceptMailPriority;
```

- `public System.Single m_DeliverMailPriority`  

```csharp
public System.Single m_DeliverMailPriority;
```

- `public Game.Buildings.PostFacilityFlags m_Flags`  

```csharp
public Game.Buildings.PostFacilityFlags m_Flags;
```

- `public System.Byte m_ProcessingFactor`  

```csharp
public System.Byte m_ProcessingFactor;
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



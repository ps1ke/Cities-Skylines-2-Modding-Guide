# PDX.SDK.Contracts.Events.IEventWithAcknowledgementBase

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Events`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IEventWithAcknowledgementBase
{
    public System.Guid EventId { get; }
    public System.Action<PDX.SDK.Contracts.Events.EventAcknowledgement> Acknowledgement { get; }

}
```


## Properties

- `public System.Guid EventId { get }`  

```csharp
public System.Guid EventId { get; }
```

- `public System.Action<PDX.SDK.Contracts.Events.EventAcknowledgement> Acknowledgement { get }`  

```csharp
public System.Action<PDX.SDK.Contracts.Events.EventAcknowledgement> Acknowledgement { get; }
```



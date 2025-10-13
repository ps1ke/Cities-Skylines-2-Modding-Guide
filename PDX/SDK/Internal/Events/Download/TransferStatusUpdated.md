# PDX.SDK.Internal.Events.Download.TransferStatusUpdated

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Download`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Download.ITransferStatusUpdated`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class TransferStatusUpdated : PDX.SDK.Contracts.Events.Download.ITransferStatusUpdated, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private PDX.SDK.Contracts.Network.ITransferStatus <TransferStatus>k__BackingField;

    public System.Guid EventId { get; set; }
    public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; set; }

    public TransferStatusUpdated();

}
```


## Fields

- `private System.Guid <EventId>k__BackingField`  

```csharp
private System.Guid <EventId>k__BackingField;
```

- `private PDX.SDK.Contracts.Network.ITransferStatus <TransferStatus>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Network.ITransferStatus <TransferStatus>k__BackingField;
```


## Properties

- `public System.Guid EventId { get; set }`  

```csharp
public System.Guid EventId { get; set; }
```

- `public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; set }`  

```csharp
public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; set; }
```


## Constructors

- `public TransferStatusUpdated()`  

```csharp
public TransferStatusUpdated();
```



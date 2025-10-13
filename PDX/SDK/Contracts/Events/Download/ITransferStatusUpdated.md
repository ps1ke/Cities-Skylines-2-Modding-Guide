# PDX.SDK.Contracts.Events.Download.ITransferStatusUpdated

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Events.Download`  

**Type:** interface abstract public  

**Implements:** `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public abstract interface ITransferStatusUpdated : PDX.SDK.Contracts.Events.IEventBase
{
    public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; }

}
```


## Properties

- `public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get }`  

```csharp
public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; }
```



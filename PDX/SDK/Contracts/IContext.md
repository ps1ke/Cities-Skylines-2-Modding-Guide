# PDX.SDK.Contracts.IContext

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts`  

**Type:** interface abstract public  


**Attributes:** `Preserve`  

## Code

```csharp
public abstract interface IContext
{
    public PDX.SDK.Contracts.Service.Account.IAccountService Account { get; }
    public PDX.SDK.Contracts.Configuration.Config Config { get; }
    public PDX.SDK.Contracts.Service.DataStorage.IDataStorageService DataStorage { get; }
    public PDX.SDK.Contracts.Service.Inventory.IInventoryService Inventory { get; }
    public PDX.SDK.Contracts.Service.Legal.ILegalService Legal { get; }
    public PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService Loyalty { get; }
    public PDX.SDK.Contracts.Service.Mods.IModsService Mods { get; }
    public System.String Namespace { get; }
    public PDX.SDK.Contracts.Enums.Platform Platform { get; }
    public PDX.SDK.Contracts.Service.Profile.IProfileService Profile { get; }
    public PDX.SDK.Contracts.Service.Telemetry.ITelemetryService Telemetry { get; }
    public PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService ThirdParty { get; }
    public PDX.SDK.Contracts.Events.IEventHub Events { get; }

    public abstract PDX.SDK.Contracts.Service.Generic.IStorageInformation GetStorageInformation();
    public abstract System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers(System.Nullable<PDX.SDK.Contracts.Enums.ETransferType> transferType, System.Nullable<PDX.SDK.Contracts.Enums.ETransferState> state, System.Nullable<PDX.SDK.Contracts.Enums.ETransferServiceType> serviceType, System.String transferId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Shutdown();
    public abstract System.Threading.Tasks.Task UpdateConfig(PDX.SDK.Contracts.Configuration.Config cfg);
}
```


## Properties

- `public PDX.SDK.Contracts.Service.Account.IAccountService Account { get }`  

```csharp
public PDX.SDK.Contracts.Service.Account.IAccountService Account { get; }
```

- `public PDX.SDK.Contracts.Configuration.Config Config { get }`  

```csharp
public PDX.SDK.Contracts.Configuration.Config Config { get; }
```

- `public PDX.SDK.Contracts.Service.DataStorage.IDataStorageService DataStorage { get }`  

```csharp
public PDX.SDK.Contracts.Service.DataStorage.IDataStorageService DataStorage { get; }
```

- `public PDX.SDK.Contracts.Service.Inventory.IInventoryService Inventory { get }`  

```csharp
public PDX.SDK.Contracts.Service.Inventory.IInventoryService Inventory { get; }
```

- `public PDX.SDK.Contracts.Service.Legal.ILegalService Legal { get }`  

```csharp
public PDX.SDK.Contracts.Service.Legal.ILegalService Legal { get; }
```

- `public PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService Loyalty { get }`  

```csharp
public PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService Loyalty { get; }
```

- `public PDX.SDK.Contracts.Service.Mods.IModsService Mods { get }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.IModsService Mods { get; }
```

- `public System.String Namespace { get }`  

```csharp
public System.String Namespace { get; }
```

- `public PDX.SDK.Contracts.Enums.Platform Platform { get }`  

```csharp
public PDX.SDK.Contracts.Enums.Platform Platform { get; }
```

- `public PDX.SDK.Contracts.Service.Profile.IProfileService Profile { get }`  

```csharp
public PDX.SDK.Contracts.Service.Profile.IProfileService Profile { get; }
```

- `public PDX.SDK.Contracts.Service.Telemetry.ITelemetryService Telemetry { get }`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.ITelemetryService Telemetry { get; }
```

- `public PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService ThirdParty { get }`  

```csharp
public PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService ThirdParty { get; }
```

- `public PDX.SDK.Contracts.Events.IEventHub Events { get }`  

```csharp
public PDX.SDK.Contracts.Events.IEventHub Events { get; }
```


## Methods

- `public abstract GetStorageInformation() : PDX.SDK.Contracts.Service.Generic.IStorageInformation`  

```csharp
public abstract PDX.SDK.Contracts.Service.Generic.IStorageInformation GetStorageInformation();
```

- `public abstract GetTransfers(System.Nullable<PDX.SDK.Contracts.Enums.ETransferType> transferType = null, System.Nullable<PDX.SDK.Contracts.Enums.ETransferState> state = null, System.Nullable<PDX.SDK.Contracts.Enums.ETransferServiceType> serviceType = null, System.String transferId = null) : System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus>`  

```csharp
public abstract System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers(System.Nullable<PDX.SDK.Contracts.Enums.ETransferType> transferType, System.Nullable<PDX.SDK.Contracts.Enums.ETransferState> state, System.Nullable<PDX.SDK.Contracts.Enums.ETransferServiceType> serviceType, System.String transferId);
```

- `public abstract Shutdown() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Shutdown();
```

- `public abstract UpdateConfig(PDX.SDK.Contracts.Configuration.Config cfg) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task UpdateConfig(PDX.SDK.Contracts.Configuration.Config cfg);
```



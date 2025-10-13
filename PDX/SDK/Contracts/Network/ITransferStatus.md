# PDX.SDK.Contracts.Network.ITransferStatus

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Network`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ITransferStatus
{
    public PDX.SDK.Contracts.Enums.ETransferType Type { get; }
    public PDX.SDK.Contracts.Enums.ETransferServiceType ServiceType { get; }
    public PDX.SDK.Contracts.Enums.ETransferState State { get; }
    public System.String Id { get; }
    public System.UInt64 ProcessedBytes { get; }
    public System.UInt64 Size { get; }
    public System.Single Progress { get; }
    public System.DateTime StartTime { get; }

}
```


## Properties

- `public PDX.SDK.Contracts.Enums.ETransferType Type { get }`  

```csharp
public PDX.SDK.Contracts.Enums.ETransferType Type { get; }
```

- `public PDX.SDK.Contracts.Enums.ETransferServiceType ServiceType { get }`  

```csharp
public PDX.SDK.Contracts.Enums.ETransferServiceType ServiceType { get; }
```

- `public PDX.SDK.Contracts.Enums.ETransferState State { get }`  

```csharp
public PDX.SDK.Contracts.Enums.ETransferState State { get; }
```

- `public System.String Id { get }`  

```csharp
public System.String Id { get; }
```

- `public System.UInt64 ProcessedBytes { get }`  

```csharp
public System.UInt64 ProcessedBytes { get; }
```

- `public System.UInt64 Size { get }`  

```csharp
public System.UInt64 Size { get; }
```

- `public System.Single Progress { get }`  

```csharp
public System.Single Progress { get; }
```

- `public System.DateTime StartTime { get }`  

```csharp
public System.DateTime StartTime { get; }
```



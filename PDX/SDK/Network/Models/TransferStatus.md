# PDX.SDK.Network.Models.TransferStatus

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network.Models`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Network.ITransferStatus`  

## Code

```csharp
public class TransferStatus : PDX.SDK.Contracts.Network.ITransferStatus
{
    private readonly PDX.SDK.Contracts.Enums.ETransferType <Type>k__BackingField;
    private readonly PDX.SDK.Contracts.Enums.ETransferServiceType <ServiceType>k__BackingField;
    private PDX.SDK.Contracts.Enums.ETransferState <State>k__BackingField;
    private readonly System.String <Id>k__BackingField;
    private System.UInt64 <ProcessedBytes>k__BackingField;
    private System.UInt64 <Size>k__BackingField;
    private System.DateTime <StartTime>k__BackingField;

    public PDX.SDK.Contracts.Enums.ETransferType Type { get; }
    public PDX.SDK.Contracts.Enums.ETransferServiceType ServiceType { get; }
    public PDX.SDK.Contracts.Enums.ETransferState State { get; set; }
    public System.String Id { get; }
    public System.UInt64 ProcessedBytes { get; private set; }
    public System.UInt64 Size { get; private set; }
    public System.Single Progress { get; }
    public System.DateTime StartTime { get; private set; }

    public TransferStatus(PDX.SDK.Contracts.Enums.ETransferType type, PDX.SDK.Contracts.Enums.ETransferServiceType service, System.String id);

    public System.Void AddToProcessedBytes(System.UInt64 add);
    public System.Void SetSize(System.UInt64 size);
    public System.Void Start();
}
```


## Fields

- `private readonly PDX.SDK.Contracts.Enums.ETransferType <Type>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Enums.ETransferType <Type>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Enums.ETransferServiceType <ServiceType>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Enums.ETransferServiceType <ServiceType>k__BackingField;
```

- `private PDX.SDK.Contracts.Enums.ETransferState <State>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Enums.ETransferState <State>k__BackingField;
```

- `private readonly System.String <Id>k__BackingField`  

```csharp
private readonly System.String <Id>k__BackingField;
```

- `private System.UInt64 <ProcessedBytes>k__BackingField`  

```csharp
private System.UInt64 <ProcessedBytes>k__BackingField;
```

- `private System.UInt64 <Size>k__BackingField`  

```csharp
private System.UInt64 <Size>k__BackingField;
```

- `private System.DateTime <StartTime>k__BackingField`  

```csharp
private System.DateTime <StartTime>k__BackingField;
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

- `public PDX.SDK.Contracts.Enums.ETransferState State { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.ETransferState State { get; set; }
```

- `public System.String Id { get }`  

```csharp
public System.String Id { get; }
```

- `public System.UInt64 ProcessedBytes { get; private set }`  

```csharp
public System.UInt64 ProcessedBytes { get; private set; }
```

- `public System.UInt64 Size { get; private set }`  

```csharp
public System.UInt64 Size { get; private set; }
```

- `public System.Single Progress { get }`  

```csharp
public System.Single Progress { get; }
```

- `public System.DateTime StartTime { get; private set }`  

```csharp
public System.DateTime StartTime { get; private set; }
```


## Constructors

- `public TransferStatus(PDX.SDK.Contracts.Enums.ETransferType type, PDX.SDK.Contracts.Enums.ETransferServiceType service, System.String id)`  

```csharp
public TransferStatus(PDX.SDK.Contracts.Enums.ETransferType type, PDX.SDK.Contracts.Enums.ETransferServiceType service, System.String id);
```


## Methods

- `public AddToProcessedBytes(System.UInt64 add) : System.Void`  

```csharp
public System.Void AddToProcessedBytes(System.UInt64 add);
```

- `public SetSize(System.UInt64 size) : System.Void`  

```csharp
public System.Void SetSize(System.UInt64 size);
```

- `public Start() : System.Void`  

```csharp
public System.Void Start();
```



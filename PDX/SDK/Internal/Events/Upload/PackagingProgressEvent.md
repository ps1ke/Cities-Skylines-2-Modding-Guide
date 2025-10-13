# PDX.SDK.Internal.Events.Upload.PackagingProgressEvent

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Upload`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Upload.IPackagingProgressEvent`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class PackagingProgressEvent : PDX.SDK.Contracts.Events.Upload.IPackagingProgressEvent, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private PDX.SDK.Contracts.Enums.PackagingStage <CurrentStage>k__BackingField;
    private System.Single <Progress>k__BackingField;
    private System.String <SourceFolder>k__BackingField;
    private System.String <Reference>k__BackingField;

    public System.Guid EventId { get; set; }
    public PDX.SDK.Contracts.Enums.PackagingStage CurrentStage { get; set; }
    public System.Single Progress { get; set; }
    public System.String SourceFolder { get; set; }
    public System.String Reference { get; set; }

    public PackagingProgressEvent();

}
```


## Fields

- `private System.Guid <EventId>k__BackingField`  

```csharp
private System.Guid <EventId>k__BackingField;
```

- `private PDX.SDK.Contracts.Enums.PackagingStage <CurrentStage>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Enums.PackagingStage <CurrentStage>k__BackingField;
```

- `private System.Single <Progress>k__BackingField`  

```csharp
private System.Single <Progress>k__BackingField;
```

- `private System.String <SourceFolder>k__BackingField`  

```csharp
private System.String <SourceFolder>k__BackingField;
```

- `private System.String <Reference>k__BackingField`  

```csharp
private System.String <Reference>k__BackingField;
```


## Properties

- `public System.Guid EventId { get; set }`  

```csharp
public System.Guid EventId { get; set; }
```

- `public PDX.SDK.Contracts.Enums.PackagingStage CurrentStage { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.PackagingStage CurrentStage { get; set; }
```

- `public System.Single Progress { get; set }`  

```csharp
public System.Single Progress { get; set; }
```

- `public System.String SourceFolder { get; set }`  

```csharp
public System.String SourceFolder { get; set; }
```

- `public System.String Reference { get; set }`  

```csharp
public System.String Reference { get; set; }
```


## Constructors

- `public PackagingProgressEvent()`  

```csharp
public PackagingProgressEvent();
```



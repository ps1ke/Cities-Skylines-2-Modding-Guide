# PDX.SDK.Internal.Events.Download.InstallProgressEvent

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events.Download`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Events.Download.IInstallProgressEvent`, `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public class InstallProgressEvent : PDX.SDK.Contracts.Events.Download.IInstallProgressEvent, PDX.SDK.Contracts.Events.IEventBase
{
    private System.Guid <EventId>k__BackingField;
    private PDX.SDK.Contracts.Enums.InstallStage <CurrentStage>k__BackingField;
    private System.Single <Progress>k__BackingField;
    private System.String <RepositoryName>k__BackingField;
    private System.String <AppName>k__BackingField;
    private System.String <InstallFolder>k__BackingField;
    private System.String <InstallingVersion>k__BackingField;
    private System.String <Reference>k__BackingField;

    public System.Guid EventId { get; set; }
    public PDX.SDK.Contracts.Enums.InstallStage CurrentStage { get; set; }
    public System.Single Progress { get; set; }
    public System.String RepositoryName { get; set; }
    public System.String AppName { get; set; }
    public System.String InstallFolder { get; set; }
    public System.String InstallingVersion { get; set; }
    public System.String Reference { get; set; }

    public InstallProgressEvent();

}
```


## Fields

- `private System.Guid <EventId>k__BackingField`  

```csharp
private System.Guid <EventId>k__BackingField;
```

- `private PDX.SDK.Contracts.Enums.InstallStage <CurrentStage>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Enums.InstallStage <CurrentStage>k__BackingField;
```

- `private System.Single <Progress>k__BackingField`  

```csharp
private System.Single <Progress>k__BackingField;
```

- `private System.String <RepositoryName>k__BackingField`  

```csharp
private System.String <RepositoryName>k__BackingField;
```

- `private System.String <AppName>k__BackingField`  

```csharp
private System.String <AppName>k__BackingField;
```

- `private System.String <InstallFolder>k__BackingField`  

```csharp
private System.String <InstallFolder>k__BackingField;
```

- `private System.String <InstallingVersion>k__BackingField`  

```csharp
private System.String <InstallingVersion>k__BackingField;
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

- `public PDX.SDK.Contracts.Enums.InstallStage CurrentStage { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.InstallStage CurrentStage { get; set; }
```

- `public System.Single Progress { get; set }`  

```csharp
public System.Single Progress { get; set; }
```

- `public System.String RepositoryName { get; set }`  

```csharp
public System.String RepositoryName { get; set; }
```

- `public System.String AppName { get; set }`  

```csharp
public System.String AppName { get; set; }
```

- `public System.String InstallFolder { get; set }`  

```csharp
public System.String InstallFolder { get; set; }
```

- `public System.String InstallingVersion { get; set }`  

```csharp
public System.String InstallingVersion { get; set; }
```

- `public System.String Reference { get; set }`  

```csharp
public System.String Reference { get; set; }
```


## Constructors

- `public InstallProgressEvent()`  

```csharp
public InstallProgressEvent();
```



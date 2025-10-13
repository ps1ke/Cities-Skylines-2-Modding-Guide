# PDX.SDK.Contracts.Events.Upload.IPackagingProgressEvent

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Events.Upload`  

**Type:** interface abstract public  

**Implements:** `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public abstract interface IPackagingProgressEvent : PDX.SDK.Contracts.Events.IEventBase
{
    public PDX.SDK.Contracts.Enums.PackagingStage CurrentStage { get; }
    public System.Single Progress { get; }
    public System.String Reference { get; }
    public System.String SourceFolder { get; }

}
```


## Properties

- `public PDX.SDK.Contracts.Enums.PackagingStage CurrentStage { get }`  

```csharp
public PDX.SDK.Contracts.Enums.PackagingStage CurrentStage { get; }
```

- `public System.Single Progress { get }`  

```csharp
public System.Single Progress { get; }
```

- `public System.String Reference { get }`  

```csharp
public System.String Reference { get; }
```

- `public System.String SourceFolder { get }`  

```csharp
public System.String SourceFolder { get; }
```



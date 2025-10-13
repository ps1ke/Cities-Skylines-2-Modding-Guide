# PDX.SDK.Contracts.Events.Download.IInstallProgressEvent

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Events.Download`  

**Type:** interface abstract public  

**Implements:** `PDX.SDK.Contracts.Events.IEventBase`  

## Code

```csharp
public abstract interface IInstallProgressEvent : PDX.SDK.Contracts.Events.IEventBase
{
    public PDX.SDK.Contracts.Enums.InstallStage CurrentStage { get; }
    public System.Single Progress { get; }
    public System.String Reference { get; }
    public System.String RepositoryName { get; }
    public System.String AppName { get; }
    public System.String InstallFolder { get; }
    public System.String InstallingVersion { get; }

}
```


## Properties

- `public PDX.SDK.Contracts.Enums.InstallStage CurrentStage { get }`  

```csharp
public PDX.SDK.Contracts.Enums.InstallStage CurrentStage { get; }
```

- `public System.Single Progress { get }`  

```csharp
public System.Single Progress { get; }
```

- `public System.String Reference { get }`  

```csharp
public System.String Reference { get; }
```

- `public System.String RepositoryName { get }`  

```csharp
public System.String RepositoryName { get; }
```

- `public System.String AppName { get }`  

```csharp
public System.String AppName { get; }
```

- `public System.String InstallFolder { get }`  

```csharp
public System.String InstallFolder { get; }
```

- `public System.String InstallingVersion { get }`  

```csharp
public System.String InstallingVersion { get; }
```



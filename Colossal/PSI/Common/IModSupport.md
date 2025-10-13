# Colossal.PSI.Common.IModSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IModSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    // (no members)
}
```


## Events

- `onModSubscriptionChanged` : `Colossal.PSI.Common.ModSubscriptionEventHandler`  

```csharp
public event Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged;
```

- `onModDownloadStarted` : `Colossal.PSI.Common.ModEventHandler`  

```csharp
public event Colossal.PSI.Common.ModEventHandler onModDownloadStarted;
```

- `onModDownloadCompleted` : `Colossal.PSI.Common.ModEventHandler`  

```csharp
public event Colossal.PSI.Common.ModEventHandler onModDownloadCompleted;
```

- `onModDownloadFailed` : `Colossal.PSI.Common.ModEventHandler`  

```csharp
public event Colossal.PSI.Common.ModEventHandler onModDownloadFailed;
```

- `onModSyncCompleted` : `Colossal.PSI.Common.ModSyncEventHandler`  

```csharp
public event Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted;
```

- `onModInstallProgress` : `Colossal.PSI.Common.ModInstallProgressEventHandler`  

```csharp
public event Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress;
```



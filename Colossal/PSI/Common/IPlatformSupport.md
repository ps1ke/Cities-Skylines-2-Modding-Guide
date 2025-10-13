# Colossal.PSI.Common.IPlatformSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IPlatformSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public abstract System.Void DisableSharing();
    public abstract System.Void EnableSharing();
    public abstract System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
    public abstract System.Threading.Tasks.Task SignOut();
}
```


## Methods

- `public abstract DisableSharing() : System.Void`  

```csharp
public abstract System.Void DisableSharing();
```

- `public abstract EnableSharing() : System.Void`  

```csharp
public abstract System.Void EnableSharing();
```

- `public abstract GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available) : System.Void`  

```csharp
public abstract System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
```

- `public abstract SignOut() : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task SignOut();
```



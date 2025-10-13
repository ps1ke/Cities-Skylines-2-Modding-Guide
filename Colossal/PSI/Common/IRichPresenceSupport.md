# Colossal.PSI.Common.IRichPresenceSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IRichPresenceSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public abstract System.Threading.Tasks.Task ClearRichPresence();
    public abstract System.Void SetRichPresence(System.String key);
}
```


## Methods

- `public abstract ClearRichPresence() : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task ClearRichPresence();
```

- `public abstract SetRichPresence(System.String key) : System.Void`  

```csharp
public abstract System.Void SetRichPresence(System.String key);
```



# Colossal.PSI.Common.IModsUploadSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IModsUploadSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public abstract System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListMods();
    public abstract System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
}
```


## Methods

- `public abstract ListMods() : System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListMods();
```

- `public abstract Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public abstract System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```


## Nested types

- `Colossal.PSI.Common.IModsUploadSupport+ModInfo`  
- `Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData`  
- `Colossal.PSI.Common.IModsUploadSupport+ExternalLinkInfo`  
- `Colossal.PSI.Common.IModsUploadSupport+ModLocalData`  
- `Colossal.PSI.Common.IModsUploadSupport+ModTag`  
- `Colossal.PSI.Common.IModsUploadSupport+DLCTag`  
- `Colossal.PSI.Common.IModsUploadSupport+ModOperationResult`  
- `Colossal.PSI.Common.IModsUploadSupport+ModError`  
- `Colossal.PSI.Common.IModsUploadSupport+SocialProfile`  


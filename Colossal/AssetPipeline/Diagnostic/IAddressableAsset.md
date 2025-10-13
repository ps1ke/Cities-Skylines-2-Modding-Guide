# Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Diagnostic`  

**Type:** interface abstract public  

**Implements:** `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public abstract interface IAddressableAsset : Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    public Colossal.Hash128 guid { get; }
    public System.Type type { get; }

}
```


## Properties

- `public Colossal.Hash128 guid { get }`  

```csharp
public Colossal.Hash128 guid { get; }
```

- `public System.Type type { get }`  

```csharp
public System.Type type { get; }
```



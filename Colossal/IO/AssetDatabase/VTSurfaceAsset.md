# Colossal.IO.AssetDatabase.VTSurfaceAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class VTSurfaceAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    private UnityEngine.Material m_Instance;
    public static const System.String kExtension;

    public Colossal.IO.AssetDatabase.LoadState state { get; }

    public VTSurfaceAsset();

    private System.Void <Save>b__5_0(System.TimeSpan t);
    public UnityEngine.Material Load();
    public System.Void Save(Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private UnityEngine.Material m_Instance`  

```csharp
private UnityEngine.Material m_Instance;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```


## Constructors

- `public VTSurfaceAsset()`  

```csharp
public VTSurfaceAsset();
```


## Methods

- `private <Save>b__5_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__5_0(System.TimeSpan t);
```

- `public Load() : UnityEngine.Material`  

```csharp
public UnityEngine.Material Load();
```

- `public Save(Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler) : System.Void`  

```csharp
public System.Void Save(Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```



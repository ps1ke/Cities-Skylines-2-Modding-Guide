# Colossal.IO.AssetDatabase.AnimationAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.Animations.AnimationClip>`  

## Code

```csharp
public class AnimationAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<Colossal.Animations.AnimationClip>
{
    private Colossal.Animations.AnimationClip m_Data;
    private Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncReadHandle;
    private Unity.Collections.NativeArray<System.Byte> m_AsyncLoadBuffer;
    public static const System.String kExtension;
    public static const System.UInt16 kFormatVersion;

    public Colossal.IO.AssetDatabase.LoadState state { get; }

    public AnimationAsset();

    private System.Void <AsyncLoad>b__10_0(System.TimeSpan t);
    private System.Void <Load>b__8_0(System.TimeSpan t);
    private System.Void <Save>b__11_0(System.TimeSpan t);
    public System.Boolean AsyncLoad(Colossal.Animations.AnimationClip& clip);
    public Colossal.Animations.AnimationClip Load(System.Int32 framerateBias);
    private System.Void Load(System.IO.Stream stream);
    public virtual System.Void Save(System.Boolean force);
    public System.Void SetData(Colossal.Animations.AnimationClip animation);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private Colossal.Animations.AnimationClip m_Data`  

```csharp
private Colossal.Animations.AnimationClip m_Data;
```

- `private Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncReadHandle`  

```csharp
private Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncReadHandle;
```

- `private Unity.Collections.NativeArray<System.Byte> m_AsyncLoadBuffer`  

```csharp
private Unity.Collections.NativeArray<System.Byte> m_AsyncLoadBuffer;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `public static const System.UInt16 kFormatVersion`  

```csharp
public static const System.UInt16 kFormatVersion;
```


## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```


## Constructors

- `public AnimationAsset()`  

```csharp
public AnimationAsset();
```


## Methods

- `private <AsyncLoad>b__10_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <AsyncLoad>b__10_0(System.TimeSpan t);
```

- `private <Load>b__8_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Load>b__8_0(System.TimeSpan t);
```

- `private <Save>b__11_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__11_0(System.TimeSpan t);
```

- `public AsyncLoad(Colossal.Animations.AnimationClip& clip) : System.Boolean`  

```csharp
public System.Boolean AsyncLoad(Colossal.Animations.AnimationClip& clip);
```

- `public Load(System.Int32 framerateBias = -1) : Colossal.Animations.AnimationClip`  

```csharp
public Colossal.Animations.AnimationClip Load(System.Int32 framerateBias);
```

- `private Load(System.IO.Stream stream) : System.Void`  

```csharp
private System.Void Load(System.IO.Stream stream);
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public SetData(Colossal.Animations.AnimationClip animation) : System.Void`  

```csharp
public System.Void SetData(Colossal.Animations.AnimationClip animation);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```



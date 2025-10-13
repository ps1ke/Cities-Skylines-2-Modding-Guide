# Colossal.IO.AssetDatabase.AudioAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class AudioAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    private UnityEngine.AudioClip m_Instance;
    private System.Int32 m_InstanceRefCount;
    private System.Double <durationMs>k__BackingField;
    private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> m_Metatags;
    private System.Double <loopStart>k__BackingField;
    private System.Double <loopEnd>k__BackingField;
    private System.Double <alternativeStart>k__BackingField;
    private System.Single <fadeoutTime>k__BackingField;
    public static const System.String kExtension;

    public System.Double durationMs { get; private set; }
    public System.Double loopStart { get; private set; }
    public System.Double loopEnd { get; private set; }
    public System.Double loopDuration { get; }
    public System.Double alternativeStart { get; private set; }
    public System.Boolean hasLoop { get; }
    public System.Boolean hasAlternativeStart { get; }
    public System.Single fadeoutTime { get; private set; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.Collections.Generic.IReadOnlyDictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> metaTags { get; }

    public AudioAsset();

    private System.Void <LoadAsyncFile>b__44_0(System.TimeSpan t);
    private System.Void AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, System.String value);
    private System.Void AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, ATL.Track trackMeta, System.String oggTag);
    private static System.String GetExtendedTag(ATL.Track trackMeta, System.String tag);
    public System.String GetMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag);
    private static System.Boolean GetTimeTag(ATL.Track trackMeta, System.String tag, System.Double& time);
    private static System.Boolean GetTimeTag(ATL.Track trackMeta, System.String tag, System.Single& time);
    public System.Threading.Tasks.Task<UnityEngine.AudioClip> LoadAsync(System.Boolean useCached, System.Boolean streamAudio, UnityEngine.AudioType audioType);
    public System.Threading.Tasks.Task<UnityEngine.AudioClip> LoadAsyncFile(System.Boolean useCached, System.Boolean streamAudio, UnityEngine.AudioType audioType);
    public virtual System.Void PostCreate();
    public virtual System.Void Unload(System.Boolean force);
    private System.Void UpdateMetaTags();
}
```


## Fields

- `private UnityEngine.AudioClip m_Instance`  

```csharp
private UnityEngine.AudioClip m_Instance;
```

- `private System.Int32 m_InstanceRefCount`  

```csharp
private System.Int32 m_InstanceRefCount;
```

- `private System.Double <durationMs>k__BackingField`  

```csharp
private System.Double <durationMs>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> m_Metatags`  

```csharp
private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> m_Metatags;
```

- `private System.Double <loopStart>k__BackingField`  

```csharp
private System.Double <loopStart>k__BackingField;
```

- `private System.Double <loopEnd>k__BackingField`  

```csharp
private System.Double <loopEnd>k__BackingField;
```

- `private System.Double <alternativeStart>k__BackingField`  

```csharp
private System.Double <alternativeStart>k__BackingField;
```

- `private System.Single <fadeoutTime>k__BackingField`  

```csharp
private System.Single <fadeoutTime>k__BackingField;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Properties

- `public System.Double durationMs { get; private set }`  

```csharp
public System.Double durationMs { get; private set; }
```

- `public System.Double loopStart { get; private set }`  

```csharp
public System.Double loopStart { get; private set; }
```

- `public System.Double loopEnd { get; private set }`  

```csharp
public System.Double loopEnd { get; private set; }
```

- `public System.Double loopDuration { get }`  

```csharp
public System.Double loopDuration { get; }
```

- `public System.Double alternativeStart { get; private set }`  

```csharp
public System.Double alternativeStart { get; private set; }
```

- `public System.Boolean hasLoop { get }`  

```csharp
public System.Boolean hasLoop { get; }
```

- `public System.Boolean hasAlternativeStart { get }`  

```csharp
public System.Boolean hasAlternativeStart { get; }
```

- `public System.Single fadeoutTime { get; private set }`  

```csharp
public System.Single fadeoutTime { get; private set; }
```

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> metaTags { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> metaTags { get; }
```


## Constructors

- `public AudioAsset()`  

```csharp
public AudioAsset();
```


## Methods

- `private <LoadAsyncFile>b__44_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <LoadAsyncFile>b__44_0(System.TimeSpan t);
```

- `private AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, System.String value) : System.Void`  

```csharp
private System.Void AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, System.String value);
```

- `private AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, ATL.Track trackMeta, System.String oggTag) : System.Void`  

```csharp
private System.Void AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, ATL.Track trackMeta, System.String oggTag);
```

- `private static GetExtendedTag(ATL.Track trackMeta, System.String tag) : System.String`  

```csharp
private static System.String GetExtendedTag(ATL.Track trackMeta, System.String tag);
```

- `public GetMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag) : System.String`  

```csharp
public System.String GetMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag);
```

- `private static GetTimeTag(ATL.Track trackMeta, System.String tag, System.Double& time) : System.Boolean`  

```csharp
private static System.Boolean GetTimeTag(ATL.Track trackMeta, System.String tag, System.Double& time);
```

- `private static GetTimeTag(ATL.Track trackMeta, System.String tag, System.Single& time) : System.Boolean`  

```csharp
private static System.Boolean GetTimeTag(ATL.Track trackMeta, System.String tag, System.Single& time);
```

- `public LoadAsync(System.Boolean useCached = True, System.Boolean streamAudio = True, UnityEngine.AudioType audioType = OGGVORBIS) : System.Threading.Tasks.Task<UnityEngine.AudioClip>`  

```csharp
public System.Threading.Tasks.Task<UnityEngine.AudioClip> LoadAsync(System.Boolean useCached, System.Boolean streamAudio, UnityEngine.AudioType audioType);
```

- `public LoadAsyncFile(System.Boolean useCached = True, System.Boolean streamAudio = True, UnityEngine.AudioType audioType = OGGVORBIS) : System.Threading.Tasks.Task<UnityEngine.AudioClip>`  

```csharp
public System.Threading.Tasks.Task<UnityEngine.AudioClip> LoadAsyncFile(System.Boolean useCached, System.Boolean streamAudio, UnityEngine.AudioType audioType);
```

- `public virtual PostCreate() : System.Void`  

```csharp
public virtual System.Void PostCreate();
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```

- `private UpdateMetaTags() : System.Void`  

```csharp
private System.Void UpdateMetaTags();
```


## Nested types

- `Colossal.IO.AssetDatabase.AudioAsset+Metatag`  
- `Colossal.IO.AssetDatabase.AudioAsset+<LoadAsync>d__43`  
- `Colossal.IO.AssetDatabase.AudioAsset+<LoadAsyncFile>d__44`  


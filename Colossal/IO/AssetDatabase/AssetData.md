# Colossal.IO.AssetDatabase.AssetData

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public abstract class AssetData : Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    private System.Int32 m_InstanceId;
    private Colossal.IO.AssetDatabase.Identifier m_Id;
    private Colossal.IO.AssetDatabase.ILocalAssetDatabase <database>k__BackingField;
    private System.Collections.Generic.List<System.String> m_Tags;
    private System.Boolean <isDirty>k__BackingField;
    protected static readonly Colossal.Logging.ILog log;
    private static System.Int32 sInstanceId;
    public static const System.String k_DebuggerDisplay;
    public static const System.String kMetaExtension;
    public static const System.String kCacheExtension;

    public System.String identifier { get; }
    private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get; }
    private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get; }
    private System.Type Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.type { private get; }
    private Colossal.Hash128 Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.guid { private get; }
    public System.String path { get; }
    public System.String subPath { get; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.String name { get; }
    public System.String uniqueName { get; }
    public System.Boolean isValid { get; }
    public System.Boolean isPersistent { get; }
    public Colossal.IO.AssetDatabase.Identifier id { get; set; }
    public System.String uri { get; set; }
    public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set; }
    public System.Boolean isDummy { get; }
    public System.Collections.Generic.IReadOnlyList<System.String> tags { get; }
    public System.Boolean isDirty { get; protected set; }
    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public AssetData();

    public System.Void AddTag(System.String tag);
    public System.Void AddTags(System.Collections.Generic.IEnumerable<System.String> tags);
    protected System.Void ClearTags();
    public System.Int32 CompareTo(Colossal.IO.AssetDatabase.IAssetData other);
    public System.Boolean ContainsTag(System.String tag);
    public System.Void Delete();
    public static System.Void Destroy(UnityEngine.Object obj);
    public System.Void Dispose();
    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Colossal.IO.AssetDatabase.IAssetData other);
    public Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor();
    public virtual System.Int32 GetHashCode();
    public Colossal.IO.AssetDatabase.SourceMeta GetMeta();
    public Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter();
    public System.IO.Stream GetReadStream();
    public System.IO.Stream GetWriteStream();
    public System.Boolean MarkDirty();
    public System.Void MoveTo(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath);
    public virtual System.Void PostCreate();
    public virtual System.Void Save(System.Boolean force);
    public virtual System.String ToString();
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private System.Int32 m_InstanceId`  

```csharp
private System.Int32 m_InstanceId;
```

- `private Colossal.IO.AssetDatabase.Identifier m_Id`  

```csharp
private Colossal.IO.AssetDatabase.Identifier m_Id;
```

- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase <database>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.ILocalAssetDatabase <database>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> m_Tags`  

```csharp
private System.Collections.Generic.List<System.String> m_Tags;
```

- `private System.Boolean <isDirty>k__BackingField`  

```csharp
private System.Boolean <isDirty>k__BackingField;
```

- `protected static readonly Colossal.Logging.ILog log`  

```csharp
protected static readonly Colossal.Logging.ILog log;
```

- `private static System.Int32 sInstanceId`  

```csharp
private static System.Int32 sInstanceId;
```

- `public static const System.String k_DebuggerDisplay`  

```csharp
public static const System.String k_DebuggerDisplay;
```

- `public static const System.String kMetaExtension`  

```csharp
public static const System.String kMetaExtension;
```

- `public static const System.String kCacheExtension`  

```csharp
public static const System.String kCacheExtension;
```


## Properties

- `public System.String identifier { get }`  

```csharp
public System.String identifier { get; }
```

- `private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get }`  

```csharp
private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get; }
```

- `private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get }`  

```csharp
private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get; }
```

- `private System.Type Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.type { private get }`  

```csharp
private System.Type Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.type { private get; }
```

- `private Colossal.Hash128 Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.guid { private get }`  

```csharp
private Colossal.Hash128 Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.guid { private get; }
```

- `public System.String path { get }`  

```csharp
public System.String path { get; }
```

- `public System.String subPath { get }`  

```csharp
public System.String subPath { get; }
```

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String uniqueName { get }`  

```csharp
public System.String uniqueName { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Boolean isPersistent { get }`  

```csharp
public System.Boolean isPersistent { get; }
```

- `public Colossal.IO.AssetDatabase.Identifier id { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.Identifier id { get; set; }
```

- `public System.String uri { get; set }`  

```csharp
public System.String uri { get; set; }
```

- `public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set; }
```

- `public System.Boolean isDummy { get }`  

```csharp
public System.Boolean isDummy { get; }
```

- `public System.Collections.Generic.IReadOnlyList<System.String> tags { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<System.String> tags { get; }
```

- `public System.Boolean isDirty { get; protected set }`  

```csharp
public System.Boolean isDirty { get; protected set; }
```

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public AssetData()`  

```csharp
public AssetData();
```


## Methods

- `public AddTag(System.String tag) : System.Void`  

```csharp
public System.Void AddTag(System.String tag);
```

- `public AddTags(System.Collections.Generic.IEnumerable<System.String> tags) : System.Void`  

```csharp
public System.Void AddTags(System.Collections.Generic.IEnumerable<System.String> tags);
```

- `protected ClearTags() : System.Void`  

```csharp
protected System.Void ClearTags();
```

- `public CompareTo(Colossal.IO.AssetDatabase.IAssetData other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.IO.AssetDatabase.IAssetData other);
```

- `public ContainsTag(System.String tag) : System.Boolean`  

```csharp
public System.Boolean ContainsTag(System.String tag);
```

- `public Delete() : System.Void`  

```csharp
public System.Void Delete();
```

- `public static Destroy(UnityEngine.Object obj) : System.Void`  

```csharp
public static System.Void Destroy(UnityEngine.Object obj);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Colossal.IO.AssetDatabase.IAssetData other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.IAssetData other);
```

- `public GetAsyncReadDescriptor() : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  

```csharp
public Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor();
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public GetMeta() : Colossal.IO.AssetDatabase.SourceMeta`  

```csharp
public Colossal.IO.AssetDatabase.SourceMeta GetMeta();
```

- `public GetPackageWriter() : Colossal.IO.AssetDatabase.IPackageWriter`  

```csharp
public Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter();
```

- `public GetReadStream() : System.IO.Stream`  

```csharp
public System.IO.Stream GetReadStream();
```

- `public GetWriteStream() : System.IO.Stream`  

```csharp
public System.IO.Stream GetWriteStream();
```

- `public MarkDirty() : System.Boolean`  

```csharp
public System.Boolean MarkDirty();
```

- `public MoveTo(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath = null) : System.Void`  

```csharp
public System.Void MoveTo(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath);
```

- `public virtual PostCreate() : System.Void`  

```csharp
public virtual System.Void PostCreate();
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```



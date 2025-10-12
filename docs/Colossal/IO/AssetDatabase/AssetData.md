# Colossal.IO.AssetDatabase.AssetData

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private System.Int32 m_InstanceId`  
- `private Colossal.IO.AssetDatabase.Identifier m_Id`  
- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase <database>k__BackingField`  
- `private System.Collections.Generic.List<System.String> m_Tags`  
- `private System.Boolean <isDirty>k__BackingField`  
- `protected static readonly Colossal.Logging.ILog log`  
- `private static System.Int32 sInstanceId`  
- `public static const System.String k_DebuggerDisplay`  
- `public static const System.String kMetaExtension`  
- `public static const System.String kCacheExtension`  

## Properties

- `public System.String identifier { get }`  
- `private System.String Colossal.AssetPipeline.Diagnostic.Report.IFile.path { private get }`  
- `private System.Int64 Colossal.AssetPipeline.Diagnostic.Report.IFile.size { private get }`  
- `private System.Type Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.type { private get }`  
- `private Colossal.Hash128 Colossal.AssetPipeline.Diagnostic.Report.IAddressableAsset.guid { private get }`  
- `public System.String path { get }`  
- `public System.String subPath { get }`  
- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.String name { get }`  
- `public System.String uniqueName { get }`  
- `public System.Boolean isValid { get }`  
- `public System.Boolean isPersistent { get }`  
- `public Colossal.IO.AssetDatabase.Identifier id { get; set }`  
- `public System.String uri { get; set }`  
- `public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set }`  
- `public System.Boolean isDummy { get }`  
- `public System.Collections.Generic.IReadOnlyList<System.String> tags { get }`  
- `public System.Boolean isDirty { get; protected set }`  
- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

## Constructors

- `public AssetData()`  

## Methods

- `public AddTag(System.String tag) : System.Void`  
- `public AddTags(System.Collections.Generic.IEnumerable<System.String> tags) : System.Void`  
- `protected ClearTags() : System.Void`  
- `public CompareTo(Colossal.IO.AssetDatabase.IAssetData other) : System.Int32`  
- `public ContainsTag(System.String tag) : System.Boolean`  
- `public Delete() : System.Void`  
- `public static Destroy(UnityEngine.Object obj) : System.Void`  
- `public Dispose() : System.Void`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public Equals(Colossal.IO.AssetDatabase.IAssetData other) : System.Boolean`  
- `public GetAsyncReadDescriptor() : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetMeta() : Colossal.IO.AssetDatabase.SourceMeta`  
- `public GetPackageWriter() : Colossal.IO.AssetDatabase.IPackageWriter`  
- `public GetReadStream() : System.IO.Stream`  
- `public GetWriteStream() : System.IO.Stream`  
- `public MarkDirty() : System.Boolean`  
- `public MoveTo(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath = null) : System.Void`  
- `public virtual PostCreate() : System.Void`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public virtual ToString() : System.String`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  


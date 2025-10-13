# Colossal.IO.AssetDatabase.GdkCloudDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Code

```csharp
public class GdkCloudDataSource : Colossal.IO.AssetDatabase.IDataSourceProvider, System.IDisposable
{
    private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
    private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager;
    private Colossal.IO.AssetDatabase.DataSourceCacheState m_CacheState;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo> m_GuidToCloudData;
    private readonly System.Boolean[] m_DataCached;
    private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField;
    private static Colossal.Logging.ILog log;
    internal static readonly Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy kPathEscapePolicy;
    public static const System.Int64 kGsMaxBlobSize;
    public static const System.Int32 kGsMaxContainerNameSize;
    public static const System.Int32 kGsMaxBlobNameSize;

    public System.Int32 maxSupportedFileLength { get; }
    public System.Int64 maxSupportedChunkSize { get; }
    public System.Boolean isRemoteStorageSource { get; }
    public System.String remoteStorageSourceName { get; }
    public System.String scheme { get; }
    public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
    public System.String rootPath { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public System.Int32 count { get; }
    public System.Boolean hasCache { get; }

    public GdkCloudDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory);

    public Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
    internal Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
    public Colossal.IO.AssetDatabase.Identifier AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
    public System.Boolean Contains(Colossal.Hash128 guid);
    private System.Void Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi);
    public System.Void DeleteCache();
    public System.Void DeleteData();
    private System.Void DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid);
    public System.Void DeleteEntry(Colossal.Hash128 guid);
    public System.Void Dispose();
    public System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>> Enumerate();
    public System.Boolean Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid);
    private System.Boolean Exists(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.DateTime& lastModified);
    public Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
    private System.Void GetContainerBlobGuidNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName);
    private System.Void GetContainerBlobNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName);
    public Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
    public System.String GetName(Colossal.Hash128 guid);
    public Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter(Colossal.Hash128 guid);
    public System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public System.IO.Stream GetReadStream(Colossal.Hash128 guid);
    private System.IO.Stream GetReadStream(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo guid);
    public System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
    private System.Boolean IsDataCached(System.Boolean priorityData);
    public System.Boolean IsPersistent(Colossal.Hash128 guid);
    private System.Boolean IsSystemData(System.String path, System.Type type);
    private Colossal.Hash128 LoadOrCreateGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, System.Boolean& isNew);
    public static System.String MakeBlobName(System.String displayName, System.Boolean escape, System.String extension);
    private System.Void MarkDataCached(System.Boolean priorityData);
    public System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
    public System.Threading.Tasks.Task ResaveCache();
    public System.Void SaveCache();
    public System.Void SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime);
    public virtual System.String ToString();
    private System.Boolean TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo& fi);
    public System.String Unescape(System.String input);
    public System.Void WriteCompleted(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid);
    private System.Void WriteGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified`  

```csharp
private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
```

- `private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager`  

```csharp
private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager;
```

- `private Colossal.IO.AssetDatabase.DataSourceCacheState m_CacheState`  

```csharp
private Colossal.IO.AssetDatabase.DataSourceCacheState m_CacheState;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo> m_GuidToCloudData`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo> m_GuidToCloudData;
```

- `private readonly System.Boolean[] m_DataCached`  

```csharp
private readonly System.Boolean[] m_DataCached;
```

- `private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField`  

```csharp
private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `internal static readonly Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy kPathEscapePolicy`  

```csharp
internal static readonly Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy kPathEscapePolicy;
```

- `public static const System.Int64 kGsMaxBlobSize`  

```csharp
public static const System.Int64 kGsMaxBlobSize;
```

- `public static const System.Int32 kGsMaxContainerNameSize`  

```csharp
public static const System.Int32 kGsMaxContainerNameSize;
```

- `public static const System.Int32 kGsMaxBlobNameSize`  

```csharp
public static const System.Int32 kGsMaxBlobNameSize;
```


## Properties

- `public System.Int32 maxSupportedFileLength { get }`  

```csharp
public System.Int32 maxSupportedFileLength { get; }
```

- `public System.Int64 maxSupportedChunkSize { get }`  

```csharp
public System.Int64 maxSupportedChunkSize { get; }
```

- `public System.Boolean isRemoteStorageSource { get }`  

```csharp
public System.Boolean isRemoteStorageSource { get; }
```

- `public System.String remoteStorageSourceName { get }`  

```csharp
public System.String remoteStorageSourceName { get; }
```

- `public System.String scheme { get }`  

```csharp
public System.String scheme { get; }
```

- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  

```csharp
public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
```

- `public System.String rootPath { get }`  

```csharp
public System.String rootPath { get; }
```

- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  

```csharp
public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
```

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```

- `public System.Boolean hasCache { get }`  

```csharp
public System.Boolean hasCache { get; }
```


## Constructors

- `public GdkCloudDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory)`  

```csharp
public GdkCloudDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory);
```


## Methods

- `public AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
public Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
```

- `internal AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
internal Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
```

- `public AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
public Colossal.IO.AssetDatabase.Identifier AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
```

- `public Contains(Colossal.Hash128 guid) : System.Boolean`  

```csharp
public System.Boolean Contains(Colossal.Hash128 guid);
```

- `private Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi) : System.Void`  

```csharp
private System.Void Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi);
```

- `public DeleteCache() : System.Void`  

```csharp
public System.Void DeleteCache();
```

- `public DeleteData() : System.Void`  

```csharp
public System.Void DeleteData();
```

- `private DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid);
```

- `public DeleteEntry(Colossal.Hash128 guid) : System.Void`  

```csharp
public System.Void DeleteEntry(Colossal.Hash128 guid);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Enumerate() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>> Enumerate();
```

- `public Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid) : System.Boolean`  

```csharp
public System.Boolean Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid);
```

- `private Exists(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.DateTime& lastModified) : System.Boolean`  

```csharp
private System.Boolean Exists(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.DateTime& lastModified);
```

- `public GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  

```csharp
public Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
```

- `private GetContainerBlobGuidNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName) : System.Void`  

```csharp
private System.Void GetContainerBlobGuidNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName);
```

- `private GetContainerBlobNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName) : System.Void`  

```csharp
private System.Void GetContainerBlobNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName);
```

- `public GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  

```csharp
public Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
```

- `public GetName(Colossal.Hash128 guid) : System.String`  

```csharp
public System.String GetName(Colossal.Hash128 guid);
```

- `public GetPackageWriter(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IPackageWriter`  

```csharp
public Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter(Colossal.Hash128 guid);
```

- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  

```csharp
public System.ValueTuple<System.Int64, System.Int64> GetQuota();
```

- `public GetReadStream(Colossal.Hash128 guid) : System.IO.Stream`  

```csharp
public System.IO.Stream GetReadStream(Colossal.Hash128 guid);
```

- `private GetReadStream(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo guid) : System.IO.Stream`  

```csharp
private System.IO.Stream GetReadStream(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo guid);
```

- `public GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  

```csharp
public System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
```

- `private IsDataCached(System.Boolean priorityData) : System.Boolean`  

```csharp
private System.Boolean IsDataCached(System.Boolean priorityData);
```

- `public IsPersistent(Colossal.Hash128 guid) : System.Boolean`  

```csharp
public System.Boolean IsPersistent(Colossal.Hash128 guid);
```

- `private IsSystemData(System.String path, System.Type type) : System.Boolean`  

```csharp
private System.Boolean IsSystemData(System.String path, System.Type type);
```

- `private LoadOrCreateGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, System.Boolean& isNew) : Colossal.Hash128`  

```csharp
private Colossal.Hash128 LoadOrCreateGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, System.Boolean& isNew);
```

- `public static MakeBlobName(System.String displayName, System.Boolean escape, System.String extension) : System.String`  

```csharp
public static System.String MakeBlobName(System.String displayName, System.Boolean escape, System.String extension);
```

- `private MarkDataCached(System.Boolean priorityData) : System.Void`  

```csharp
private System.Void MarkDataCached(System.Boolean priorityData);
```

- `public PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
```

- `public ResaveCache() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task ResaveCache();
```

- `public SaveCache() : System.Void`  

```csharp
public System.Void SaveCache();
```

- `public SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime) : System.Void`  

```csharp
public System.Void SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `private TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo& fi) : System.Boolean`  

```csharp
private System.Boolean TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo& fi);
```

- `public Unescape(System.String input) : System.String`  

```csharp
public System.String Unescape(System.String input);
```

- `public WriteCompleted(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid) : System.Void`  

```csharp
public System.Void WriteCompleted(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid);
```

- `private WriteGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void WriteGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid);
```


## Events

- `onModified` : `Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler`  

```csharp
public event Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
```


## Nested types

- `Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<>c__DisplayClass42_0`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<>c__DisplayClass54_0`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<>c__DisplayClass63_0`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<Enumerate>d__33`  


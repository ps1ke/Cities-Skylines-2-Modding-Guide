# Colossal.IO.AssetDatabase.FileSystemDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Code

```csharp
public class FileSystemDataSource : Colossal.IO.AssetDatabase.IDataSourceProvider, System.IDisposable
{
    private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
    protected readonly System.String m_Hostname;
    private readonly System.String m_RootPath;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo> m_GuidToPhysicalData;
    private readonly System.Boolean[] m_DataCached;
    private readonly Colossal.FileSystem.Watcher m_Watcher;
    private readonly System.Int64 m_MaxChunkSize;
    private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField;
    internal static readonly Colossal.IO.AssetDatabase.FileSystemDataSource+PathEscapePolicy kPathEscapePolicy;
    protected static Colossal.Logging.ILog log;

    public System.Boolean hasCache { get; }
    public System.Int32 maxSupportedFileLength { get; }
    public System.Int64 maxSupportedChunkSize { get; }
    public System.Boolean isRemoteStorageSource { get; }
    public System.String remoteStorageSourceName { get; }
    public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
    public System.String rootPath { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public System.Int32 count { get; }

    public FileSystemDataSource(System.String hostName, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory, System.Int64 maxChunkSize);

    protected Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, System.Int64 size, System.Int64 offset, System.Boolean priorityData, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Boolean fromCache, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
    public Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
    public Colossal.IO.AssetDatabase.Identifier AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
    public System.Boolean Contains(Colossal.Hash128 guid);
    private System.Void Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean removeFromDisk);
    public virtual System.Void DeleteCache();
    public System.Void DeleteData();
    protected System.Void DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, System.Boolean removeFromDisk);
    public virtual System.Void DeleteEntry(Colossal.Hash128 guid);
    private static System.Void DeleteGuid(System.String path);
    public virtual System.Void Dispose();
    public System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>> Enumerate();
    public System.Boolean Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid);
    public Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
    protected System.Collections.Generic.IReadOnlyDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo> GetEntries();
    public virtual Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
    public System.String GetName(Colossal.Hash128 guid);
    public Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter(Colossal.Hash128 guid);
    public System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public System.IO.Stream GetReadStream(Colossal.Hash128 guid);
    private System.IO.Stream GetReadStream(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi);
    public System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
    protected System.Boolean IsDataCached(System.Boolean priorityData);
    public System.Boolean IsPersistent(Colossal.Hash128 guid);
    private Colossal.Hash128 LoadOrCreateGuid(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean& isNew);
    public virtual System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider> LoadSavedCache();
    protected System.Void MarkDataCached(System.Boolean priorityData);
    private System.Void OnDirectoryCreated(System.String path);
    private System.Void OnDirectoryDeleted(System.String path);
    private System.Void OnFileChanged(System.String path);
    private System.Void OnFileCreated(System.String path);
    private System.Void OnFileDeleted(System.String path);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
    protected System.Threading.Tasks.Task PopulateFromDirectory(System.String root, System.Boolean priorityData, System.Threading.CancellationToken ct, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
    protected System.Void PopulateFromPackage(System.Boolean warnCollision, System.Boolean priorityData, Colossal.Hash128 packageGuid, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
    public virtual System.Void SaveCache();
    public System.Void SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime);
    public virtual System.String ToString();
    private System.Boolean TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo& fi);
    public System.String Unescape(System.String input);
    private System.Void WriteCompleted(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, Colossal.Hash128 guid);
    protected static System.Void WriteGuid(System.String path, Colossal.Hash128 guid);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified`  

```csharp
private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
```

- `protected readonly System.String m_Hostname`  

```csharp
protected readonly System.String m_Hostname;
```

- `private readonly System.String m_RootPath`  

```csharp
private readonly System.String m_RootPath;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo> m_GuidToPhysicalData`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo> m_GuidToPhysicalData;
```

- `private readonly System.Boolean[] m_DataCached`  

```csharp
private readonly System.Boolean[] m_DataCached;
```

- `private readonly Colossal.FileSystem.Watcher m_Watcher`  

```csharp
private readonly Colossal.FileSystem.Watcher m_Watcher;
```

- `private readonly System.Int64 m_MaxChunkSize`  

```csharp
private readonly System.Int64 m_MaxChunkSize;
```

- `private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField`  

```csharp
private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField;
```

- `internal static readonly Colossal.IO.AssetDatabase.FileSystemDataSource+PathEscapePolicy kPathEscapePolicy`  

```csharp
internal static readonly Colossal.IO.AssetDatabase.FileSystemDataSource+PathEscapePolicy kPathEscapePolicy;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```


## Properties

- `public System.Boolean hasCache { get }`  

```csharp
public System.Boolean hasCache { get; }
```

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


## Constructors

- `public FileSystemDataSource(System.String hostName, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory, System.Int64 maxChunkSize = 0)`  

```csharp
public FileSystemDataSource(System.String hostName, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory, System.Int64 maxChunkSize);
```


## Methods

- `protected AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, System.Int64 size, System.Int64 offset, System.Boolean priorityData, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Boolean fromCache, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
protected Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, System.Int64 size, System.Int64 offset, System.Boolean priorityData, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Boolean fromCache, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
```

- `public AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
public Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
```

- `public AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
public Colossal.IO.AssetDatabase.Identifier AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
```

- `public Contains(Colossal.Hash128 guid) : System.Boolean`  

```csharp
public System.Boolean Contains(Colossal.Hash128 guid);
```

- `private Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean removeFromDisk) : System.Void`  

```csharp
private System.Void Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean removeFromDisk);
```

- `public virtual DeleteCache() : System.Void`  

```csharp
public virtual System.Void DeleteCache();
```

- `public DeleteData() : System.Void`  

```csharp
public System.Void DeleteData();
```

- `protected DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, System.Boolean removeFromDisk) : System.Void`  

```csharp
protected System.Void DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, System.Boolean removeFromDisk);
```

- `public virtual DeleteEntry(Colossal.Hash128 guid) : System.Void`  

```csharp
public virtual System.Void DeleteEntry(Colossal.Hash128 guid);
```

- `private static DeleteGuid(System.String path) : System.Void`  

```csharp
private static System.Void DeleteGuid(System.String path);
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public Enumerate() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>> Enumerate();
```

- `public Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid) : System.Boolean`  

```csharp
public System.Boolean Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid);
```

- `public GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  

```csharp
public Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
```

- `protected GetEntries() : System.Collections.Generic.IReadOnlyDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo>`  

```csharp
protected System.Collections.Generic.IReadOnlyDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo> GetEntries();
```

- `public virtual GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  

```csharp
public virtual Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
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

- `private GetReadStream(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi) : System.IO.Stream`  

```csharp
private System.IO.Stream GetReadStream(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi);
```

- `public GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  

```csharp
public System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
```

- `protected IsDataCached(System.Boolean priorityData) : System.Boolean`  

```csharp
protected System.Boolean IsDataCached(System.Boolean priorityData);
```

- `public IsPersistent(Colossal.Hash128 guid) : System.Boolean`  

```csharp
public System.Boolean IsPersistent(Colossal.Hash128 guid);
```

- `private LoadOrCreateGuid(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean& isNew) : Colossal.Hash128`  

```csharp
private Colossal.Hash128 LoadOrCreateGuid(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean& isNew);
```

- `public virtual LoadSavedCache() : System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider>`  

```csharp
public virtual System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider> LoadSavedCache();
```

- `protected MarkDataCached(System.Boolean priorityData) : System.Void`  

```csharp
protected System.Void MarkDataCached(System.Boolean priorityData);
```

- `private OnDirectoryCreated(System.String path) : System.Void`  

```csharp
private System.Void OnDirectoryCreated(System.String path);
```

- `private OnDirectoryDeleted(System.String path) : System.Void`  

```csharp
private System.Void OnDirectoryDeleted(System.String path);
```

- `private OnFileChanged(System.String path) : System.Void`  

```csharp
private System.Void OnFileChanged(System.String path);
```

- `private OnFileCreated(System.String path) : System.Void`  

```csharp
private System.Void OnFileCreated(System.String path);
```

- `private OnFileDeleted(System.String path) : System.Void`  

```csharp
private System.Void OnFileDeleted(System.String path);
```

- `public virtual PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
```

- `protected PopulateFromDirectory(System.String root, System.Boolean priorityData, System.Threading.CancellationToken ct, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Threading.Tasks.Task`  

```csharp
protected System.Threading.Tasks.Task PopulateFromDirectory(System.String root, System.Boolean priorityData, System.Threading.CancellationToken ct, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
```

- `protected PopulateFromPackage(System.Boolean warnCollision, System.Boolean priorityData, Colossal.Hash128 packageGuid, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Void`  

```csharp
protected System.Void PopulateFromPackage(System.Boolean warnCollision, System.Boolean priorityData, Colossal.Hash128 packageGuid, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
```

- `public virtual SaveCache() : System.Void`  

```csharp
public virtual System.Void SaveCache();
```

- `public SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime) : System.Void`  

```csharp
public System.Void SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `private TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo& fi) : System.Boolean`  

```csharp
private System.Boolean TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo& fi);
```

- `public Unescape(System.String input) : System.String`  

```csharp
public System.String Unescape(System.String input);
```

- `private WriteCompleted(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void WriteCompleted(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, Colossal.Hash128 guid);
```

- `protected static WriteGuid(System.String path, Colossal.Hash128 guid) : System.Void`  

```csharp
protected static System.Void WriteGuid(System.String path, Colossal.Hash128 guid);
```


## Events

- `onModified` : `Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler`  

```csharp
public event Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
```


## Nested types

- `Colossal.IO.AssetDatabase.FileSystemDataSource+PathEscapePolicy`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<>c__DisplayClass49_0`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<>c__DisplayClass63_0`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<>c__DisplayClass65_0`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<>c__DisplayClass69_0`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<>c__DisplayClass73_0`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<Enumerate>d__38`  
- `Colossal.IO.AssetDatabase.FileSystemDataSource+<PopulateDataSource>d__73`  


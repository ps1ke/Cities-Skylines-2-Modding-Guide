# Colossal.IO.AssetDatabase.FileSystemDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Fields

- `private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified`  
- `protected readonly System.String m_Hostname`  
- `private readonly System.String m_RootPath`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo> m_GuidToPhysicalData`  
- `private readonly System.Boolean[] m_DataCached`  
- `private readonly Colossal.FileSystem.Watcher m_Watcher`  
- `private readonly System.Int64 m_MaxChunkSize`  
- `private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField`  
- `internal static readonly Colossal.IO.AssetDatabase.FileSystemDataSource+PathEscapePolicy kPathEscapePolicy`  
- `protected static Colossal.Logging.ILog log`  

## Properties

- `public System.Boolean hasCache { get }`  
- `public System.Int32 maxSupportedFileLength { get }`  
- `public System.Int64 maxSupportedChunkSize { get }`  
- `public System.Boolean isRemoteStorageSource { get }`  
- `public System.String remoteStorageSourceName { get }`  
- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  
- `public System.String rootPath { get }`  
- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  
- `public System.Int32 count { get }`  

## Constructors

- `public FileSystemDataSource(System.String hostName, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory, System.Int64 maxChunkSize = 0)`  

## Methods

- `protected AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, System.Int64 size, System.Int64 offset, System.Boolean priorityData, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Boolean fromCache, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : Colossal.IO.AssetDatabase.Identifier`  
- `public AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  
- `public AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  
- `public Contains(Colossal.Hash128 guid) : System.Boolean`  
- `private Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean removeFromDisk) : System.Void`  
- `public virtual DeleteCache() : System.Void`  
- `public DeleteData() : System.Void`  
- `protected DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, System.Boolean removeFromDisk) : System.Void`  
- `public virtual DeleteEntry(Colossal.Hash128 guid) : System.Void`  
- `private static DeleteGuid(System.String path) : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public Enumerate() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>>`  
- `public Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid) : System.Boolean`  
- `public GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  
- `protected GetEntries() : System.Collections.Generic.IReadOnlyDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo>`  
- `public virtual GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  
- `public GetName(Colossal.Hash128 guid) : System.String`  
- `public GetPackageWriter(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IPackageWriter`  
- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  
- `public GetReadStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `private GetReadStream(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi) : System.IO.Stream`  
- `public GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `protected IsDataCached(System.Boolean priorityData) : System.Boolean`  
- `public IsPersistent(Colossal.Hash128 guid) : System.Boolean`  
- `private LoadOrCreateGuid(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, System.Boolean& isNew) : Colossal.Hash128`  
- `public virtual LoadSavedCache() : System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider>`  
- `protected MarkDataCached(System.Boolean priorityData) : System.Void`  
- `private OnDirectoryCreated(System.String path) : System.Void`  
- `private OnDirectoryDeleted(System.String path) : System.Void`  
- `private OnFileChanged(System.String path) : System.Void`  
- `private OnFileCreated(System.String path) : System.Void`  
- `private OnFileDeleted(System.String path) : System.Void`  
- `public virtual PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  
- `protected PopulateFromDirectory(System.String root, System.Boolean priorityData, System.Threading.CancellationToken ct, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Threading.Tasks.Task`  
- `protected PopulateFromPackage(System.Boolean warnCollision, System.Boolean priorityData, Colossal.Hash128 packageGuid, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Void`  
- `public virtual SaveCache() : System.Void`  
- `public SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime) : System.Void`  
- `public virtual ToString() : System.String`  
- `private TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo& fi) : System.Boolean`  
- `public Unescape(System.String input) : System.String`  
- `private WriteCompleted(Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo fi, Colossal.Hash128 guid) : System.Void`  
- `protected static WriteGuid(System.String path, Colossal.Hash128 guid) : System.Void`  

## Events

- `onModified` : `Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler`  

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


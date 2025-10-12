# Colossal.IO.AssetDatabase.GdkCloudDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Fields

- `private Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified`  
- `private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager`  
- `private Colossal.IO.AssetDatabase.DataSourceCacheState m_CacheState`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo> m_GuidToCloudData`  
- `private readonly System.Boolean[] m_DataCached`  
- `private readonly Colossal.IO.AssetDatabase.IAssetFactory <assetFactory>k__BackingField`  
- `private static Colossal.Logging.ILog log`  
- `internal static readonly Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy kPathEscapePolicy`  
- `public static const System.Int64 kGsMaxBlobSize`  
- `public static const System.Int32 kGsMaxContainerNameSize`  
- `public static const System.Int32 kGsMaxBlobNameSize`  

## Properties

- `public System.Int32 maxSupportedFileLength { get }`  
- `public System.Int64 maxSupportedChunkSize { get }`  
- `public System.Boolean isRemoteStorageSource { get }`  
- `public System.String remoteStorageSourceName { get }`  
- `public System.String scheme { get }`  
- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  
- `public System.String rootPath { get }`  
- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  
- `public System.Int32 count { get }`  
- `public System.Boolean hasCache { get }`  

## Constructors

- `public GdkCloudDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory)`  

## Methods

- `public AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  
- `internal AddEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, System.Boolean warnCollision, System.String path, System.Type type, Colossal.Hash128 guid, Colossal.Hash128 package, System.String packageEntryName, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : Colossal.IO.AssetDatabase.Identifier`  
- `public AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  
- `public Contains(Colossal.Hash128 guid) : System.Boolean`  
- `private Delete(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi) : System.Void`  
- `public DeleteCache() : System.Void`  
- `public DeleteData() : System.Void`  
- `private DeleteEntry(Colossal.IO.AssetDatabase.DataSourceModification modification, Colossal.Hash128 guid) : System.Void`  
- `public DeleteEntry(Colossal.Hash128 guid) : System.Void`  
- `public Dispose() : System.Void`  
- `public Enumerate() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>>`  
- `public Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid) : System.Boolean`  
- `private Exists(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.DateTime& lastModified) : System.Boolean`  
- `public GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  
- `private GetContainerBlobGuidNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName) : System.Void`  
- `private GetContainerBlobNames(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo entry, System.String& containerName, System.String& blobName) : System.Void`  
- `public GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  
- `public GetName(Colossal.Hash128 guid) : System.String`  
- `public GetPackageWriter(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IPackageWriter`  
- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  
- `public GetReadStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `private GetReadStream(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo guid) : System.IO.Stream`  
- `public GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `private IsDataCached(System.Boolean priorityData) : System.Boolean`  
- `public IsPersistent(Colossal.Hash128 guid) : System.Boolean`  
- `private IsSystemData(System.String path, System.Type type) : System.Boolean`  
- `private LoadOrCreateGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, System.Boolean& isNew) : Colossal.Hash128`  
- `public static MakeBlobName(System.String displayName, System.Boolean escape, System.String extension) : System.String`  
- `private MarkDataCached(System.Boolean priorityData) : System.Void`  
- `public PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  
- `public ResaveCache() : System.Threading.Tasks.Task`  
- `public SaveCache() : System.Void`  
- `public SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime) : System.Void`  
- `public virtual ToString() : System.String`  
- `private TryGetEntry(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo& fi) : System.Boolean`  
- `public Unescape(System.String input) : System.String`  
- `public WriteCompleted(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid) : System.Void`  
- `private WriteGuid(Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.Hash128 guid) : System.Void`  

## Events

- `onModified` : `Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler`  

## Nested types

- `Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<>c__DisplayClass42_0`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<>c__DisplayClass54_0`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<>c__DisplayClass63_0`  
- `Colossal.IO.AssetDatabase.GdkCloudDataSource+<Enumerate>d__33`  


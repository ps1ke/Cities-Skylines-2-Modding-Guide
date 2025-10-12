# Colossal.IO.AssetDatabase.IDataSourceProvider

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Properties

- `public System.Int64 maxSupportedChunkSize { get }`  
- `public System.Int32 maxSupportedFileLength { get }`  
- `public System.Boolean isRemoteStorageSource { get }`  
- `public System.String remoteStorageSourceName { get }`  
- `public System.String rootPath { get }`  
- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  
- `public System.Int32 count { get }`  
- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  
- `public System.Boolean hasCache { get }`  

## Methods

- `public abstract AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  
- `public abstract AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  
- `public abstract Contains(Colossal.Hash128 guid) : System.Boolean`  
- `public abstract DeleteCache() : System.Void`  
- `public abstract DeleteData() : System.Void`  
- `public abstract DeleteEntry(Colossal.Hash128 guid) : System.Void`  
- `public abstract Enumerate() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>>`  
- `public abstract Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid) : System.Boolean`  
- `public abstract GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  
- `public abstract GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  
- `public abstract GetName(Colossal.Hash128 guid) : System.String`  
- `public abstract GetPackageWriter(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IPackageWriter`  
- `public abstract GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  
- `public abstract GetReadStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `public abstract GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `public abstract IsPersistent(Colossal.Hash128 guid) : System.Boolean`  
- `public abstract PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  
- `public abstract SaveCache() : System.Void`  
- `public abstract SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime) : System.Void`  
- `public abstract Unescape(System.String input) : System.String`  

## Events

- `onModified` : `Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler`  


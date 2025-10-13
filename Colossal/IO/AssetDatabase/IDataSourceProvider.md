# Colossal.IO.AssetDatabase.IDataSourceProvider

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IDataSourceProvider : System.IDisposable
{
    public System.Int64 maxSupportedChunkSize { get; }
    public System.Int32 maxSupportedFileLength { get; }
    public System.Boolean isRemoteStorageSource { get; }
    public System.String remoteStorageSourceName { get; }
    public System.String rootPath { get; }
    public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
    public System.Int32 count { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public System.Boolean hasCache { get; }

    public abstract Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.Identifier AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
    public abstract System.Boolean Contains(Colossal.Hash128 guid);
    public abstract System.Void DeleteCache();
    public abstract System.Void DeleteData();
    public abstract System.Void DeleteEntry(Colossal.Hash128 guid);
    public abstract System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>> Enumerate();
    public abstract System.Boolean Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid);
    public abstract Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
    public abstract System.String GetName(Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter(Colossal.Hash128 guid);
    public abstract System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public abstract System.IO.Stream GetReadStream(Colossal.Hash128 guid);
    public abstract System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
    public abstract System.Boolean IsPersistent(Colossal.Hash128 guid);
    public abstract System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
    public abstract System.Void SaveCache();
    public abstract System.Void SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime);
    public abstract System.String Unescape(System.String input);
}
```


## Properties

- `public System.Int64 maxSupportedChunkSize { get }`  

```csharp
public System.Int64 maxSupportedChunkSize { get; }
```

- `public System.Int32 maxSupportedFileLength { get }`  

```csharp
public System.Int32 maxSupportedFileLength { get; }
```

- `public System.Boolean isRemoteStorageSource { get }`  

```csharp
public System.Boolean isRemoteStorageSource { get; }
```

- `public System.String remoteStorageSourceName { get }`  

```csharp
public System.String remoteStorageSourceName { get; }
```

- `public System.String rootPath { get }`  

```csharp
public System.String rootPath { get; }
```

- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  

```csharp
public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
```

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```

- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  

```csharp
public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
```

- `public System.Boolean hasCache { get }`  

```csharp
public System.Boolean hasCache { get; }
```


## Methods

- `public abstract AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
public abstract Colossal.IO.AssetDatabase.Identifier AddEntry(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
```

- `public abstract AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid = null) : Colossal.IO.AssetDatabase.Identifier`  

```csharp
public abstract Colossal.IO.AssetDatabase.Identifier AddEntryFromDatabase(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128 guid);
```

- `public abstract Contains(Colossal.Hash128 guid) : System.Boolean`  

```csharp
public abstract System.Boolean Contains(Colossal.Hash128 guid);
```

- `public abstract DeleteCache() : System.Void`  

```csharp
public abstract System.Void DeleteCache();
```

- `public abstract DeleteData() : System.Void`  

```csharp
public abstract System.Void DeleteData();
```

- `public abstract DeleteEntry(Colossal.Hash128 guid) : System.Void`  

```csharp
public abstract System.Void DeleteEntry(Colossal.Hash128 guid);
```

- `public abstract Enumerate() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<System.ValueTuple<System.Type, Colossal.Hash128>> Enumerate();
```

- `public abstract Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid) : System.Boolean`  

```csharp
public abstract System.Boolean Exists(Colossal.IO.AssetDatabase.AssetDataPath path, System.Type type, Colossal.Hash128& guid);
```

- `public abstract GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  

```csharp
public abstract Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
```

- `public abstract GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  

```csharp
public abstract Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
```

- `public abstract GetName(Colossal.Hash128 guid) : System.String`  

```csharp
public abstract System.String GetName(Colossal.Hash128 guid);
```

- `public abstract GetPackageWriter(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IPackageWriter`  

```csharp
public abstract Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter(Colossal.Hash128 guid);
```

- `public abstract GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  

```csharp
public abstract System.ValueTuple<System.Int64, System.Int64> GetQuota();
```

- `public abstract GetReadStream(Colossal.Hash128 guid) : System.IO.Stream`  

```csharp
public abstract System.IO.Stream GetReadStream(Colossal.Hash128 guid);
```

- `public abstract GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  

```csharp
public abstract System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
```

- `public abstract IsPersistent(Colossal.Hash128 guid) : System.Boolean`  

```csharp
public abstract System.Boolean IsPersistent(Colossal.Hash128 guid);
```

- `public abstract PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
```

- `public abstract SaveCache() : System.Void`  

```csharp
public abstract System.Void SaveCache();
```

- `public abstract SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime) : System.Void`  

```csharp
public abstract System.Void SetTimestamp(Colossal.Hash128 guid, System.DateTime creationTime, System.DateTime lastAccessTime, System.DateTime lastWriteTime);
```

- `public abstract Unescape(System.String input) : System.String`  

```csharp
public abstract System.String Unescape(System.String input);
```


## Events

- `onModified` : `Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler`  

```csharp
public event Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler onModified;
```



# Colossal.IO.AssetDatabase.CachedFileSystemDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.FileSystemDataSource`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Code

```csharp
public class CachedFileSystemDataSource : Colossal.IO.AssetDatabase.FileSystemDataSource, Colossal.IO.AssetDatabase.IDataSourceProvider, System.IDisposable
{
    private readonly System.String m_CachePath;
    private static readonly System.UInt16 kFileFormatVersion;
    private static const System.String kCacheName;

    public System.Boolean hasCache { get; }

    public CachedFileSystemDataSource(System.String hostname, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory);

    public virtual System.Void DeleteCache();
    public virtual System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider> LoadSavedCache();
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
    private System.Threading.Tasks.Task ReadCache(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
    private System.Void ReadEntries(System.UInt16 version, System.Type[] assetTypes, System.Boolean priorityData, System.IO.BinaryReader sr, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
    public virtual System.Void SaveCache();
    private System.Void SaveEntries(System.IO.BinaryWriter sw, System.Type[] assetTypes, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.KeyValuePair<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo>> entries);
}
```


## Fields

- `private readonly System.String m_CachePath`  

```csharp
private readonly System.String m_CachePath;
```

- `private static readonly System.UInt16 kFileFormatVersion`  

```csharp
private static readonly System.UInt16 kFileFormatVersion;
```

- `private static const System.String kCacheName`  

```csharp
private static const System.String kCacheName;
```


## Properties

- `public System.Boolean hasCache { get }`  

```csharp
public System.Boolean hasCache { get; }
```


## Constructors

- `public CachedFileSystemDataSource(System.String hostname, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory)`  

```csharp
public CachedFileSystemDataSource(System.String hostname, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory);
```


## Methods

- `public virtual DeleteCache() : System.Void`  

```csharp
public virtual System.Void DeleteCache();
```

- `public virtual LoadSavedCache() : System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider>`  

```csharp
public virtual System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider> LoadSavedCache();
```

- `public virtual PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
```

- `private ReadCache(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task ReadCache(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
```

- `private ReadEntries(System.UInt16 version, System.Type[] assetTypes, System.Boolean priorityData, System.IO.BinaryReader sr, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Void`  

```csharp
private System.Void ReadEntries(System.UInt16 version, System.Type[] assetTypes, System.Boolean priorityData, System.IO.BinaryReader sr, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData);
```

- `public virtual SaveCache() : System.Void`  

```csharp
public virtual System.Void SaveCache();
```

- `private SaveEntries(System.IO.BinaryWriter sw, System.Type[] assetTypes, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.KeyValuePair<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo>> entries) : System.Void`  

```csharp
private System.Void SaveEntries(System.IO.BinaryWriter sw, System.Type[] assetTypes, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.KeyValuePair<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo>> entries);
```


## Nested types

- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<>c`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<>c__DisplayClass12_0`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<>c__DisplayClass5_0`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<LoadSavedCache>d__6`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<PopulateDataSource>d__12`  


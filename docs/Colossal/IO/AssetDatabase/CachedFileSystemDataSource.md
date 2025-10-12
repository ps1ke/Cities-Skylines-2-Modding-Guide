# Colossal.IO.AssetDatabase.CachedFileSystemDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.FileSystemDataSource`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Fields

- `private readonly System.String m_CachePath`  
- `private static readonly System.UInt16 kFileFormatVersion`  
- `private static const System.String kCacheName`  

## Properties

- `public System.Boolean hasCache { get }`  

## Constructors

- `public CachedFileSystemDataSource(System.String hostname, System.String rootPath, Colossal.IO.AssetDatabase.IAssetFactory assetFactory)`  

## Methods

- `public virtual DeleteCache() : System.Void`  
- `public virtual LoadSavedCache() : System.Threading.Tasks.Task<Colossal.IO.AssetDatabase.IDataSourceProvider>`  
- `public virtual PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  
- `private ReadCache(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Threading.Tasks.Task`  
- `private ReadEntries(System.UInt16 version, System.Type[] assetTypes, System.Boolean priorityData, System.IO.BinaryReader sr, System.Threading.CancellationToken ct, Colossal.TaskProgress progress, System.Collections.Generic.List<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>> newData) : System.Void`  
- `public virtual SaveCache() : System.Void`  
- `private SaveEntries(System.IO.BinaryWriter sw, System.Type[] assetTypes, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.KeyValuePair<Colossal.Hash128, Colossal.IO.AssetDatabase.FileSystemDataSource+EntryInfo>> entries) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<>c`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<>c__DisplayClass12_0`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<>c__DisplayClass5_0`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<LoadSavedCache>d__6`  
- `Colossal.IO.AssetDatabase.CachedFileSystemDataSource+<PopulateDataSource>d__12`  


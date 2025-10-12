# Colossal.IO.AssetDatabase.IDataSourceAccessor

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  


## Properties

- `public System.Int64 maxSupportedChunkSize { get }`  
- `public Colossal.IO.AssetDatabase.IDataSourceProvider dataSource { get }`  

## Methods

- `public abstract GetAsyncReadDescriptor(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.AsyncReadDescriptor`  
- `public abstract GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  
- `public abstract GetName(Colossal.Hash128 guid) : System.String`  
- `public abstract GetPackageWriter(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IPackageWriter`  
- `public abstract GetReadStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `public abstract GetWriteStream(Colossal.Hash128 guid) : System.IO.Stream`  
- `public abstract IsPersistent(Colossal.Hash128 guid) : System.Boolean`  
- `public abstract PopulateFromDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task`  


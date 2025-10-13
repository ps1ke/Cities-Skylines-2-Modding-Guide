# Colossal.IO.AssetDatabase.IDataSourceAccessor

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDataSourceAccessor
{
    public System.Int64 maxSupportedChunkSize { get; }
    public Colossal.IO.AssetDatabase.IDataSourceProvider dataSource { get; }

    public abstract Colossal.IO.AssetDatabase.AsyncReadDescriptor GetAsyncReadDescriptor(Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
    public abstract System.String GetName(Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.IPackageWriter GetPackageWriter(Colossal.Hash128 guid);
    public abstract System.IO.Stream GetReadStream(Colossal.Hash128 guid);
    public abstract System.IO.Stream GetWriteStream(Colossal.Hash128 guid);
    public abstract System.Boolean IsPersistent(Colossal.Hash128 guid);
    public abstract System.Threading.Tasks.Task PopulateFromDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
}
```


## Properties

- `public System.Int64 maxSupportedChunkSize { get }`  

```csharp
public System.Int64 maxSupportedChunkSize { get; }
```

- `public Colossal.IO.AssetDatabase.IDataSourceProvider dataSource { get }`  

```csharp
public Colossal.IO.AssetDatabase.IDataSourceProvider dataSource { get; }
```


## Methods

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

- `public abstract PopulateFromDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task PopulateFromDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
```



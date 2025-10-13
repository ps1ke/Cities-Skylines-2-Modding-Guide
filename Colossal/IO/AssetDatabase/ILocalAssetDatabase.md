# Colossal.IO.AssetDatabase.ILocalAssetDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabase`, `System.IDisposable`, `Colossal.IO.AssetDatabase.IDataSourceAccessor`  

## Code

```csharp
public abstract interface ILocalAssetDatabase : Colossal.IO.AssetDatabase.IAssetDatabase, System.IDisposable, Colossal.IO.AssetDatabase.IDataSourceAccessor
{
    public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
    public System.Boolean canWriteSettings { get; }

    public abstract TAssetData AddAsset<TAssetData, TData>(Colossal.IO.AssetDatabase.AssetDataPath name, TData data, Colossal.Hash128 forceGuid);
    public abstract TAssetData AddAsset<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid);
    public abstract Colossal.IO.AssetDatabase.IAssetData AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid);
    public abstract Colossal.IO.AssetDatabase.IAssetData AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, System.Type type, Colossal.Hash128 forceGuid);
    public abstract System.Boolean Exists<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath path, TAssetData& asset);
    public abstract System.Void MarkForDeletion();
    public abstract System.Void MoveAssetTo(Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath);
}
```


## Properties

- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  

```csharp
public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get; }
```

- `public System.Boolean canWriteSettings { get }`  

```csharp
public System.Boolean canWriteSettings { get; }
```


## Methods

- `public abstract AddAsset<TAssetData, TData>(Colossal.IO.AssetDatabase.AssetDataPath name, TData data, Colossal.Hash128 forceGuid = null) : TAssetData`  

```csharp
public abstract TAssetData AddAsset<TAssetData, TData>(Colossal.IO.AssetDatabase.AssetDataPath name, TData data, Colossal.Hash128 forceGuid);
```

- `public abstract AddAsset<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid = null) : TAssetData`  

```csharp
public abstract TAssetData AddAsset<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid);
```

- `public abstract AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid = null) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public abstract Colossal.IO.AssetDatabase.IAssetData AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid);
```

- `public abstract AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, System.Type type, Colossal.Hash128 forceGuid = null) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public abstract Colossal.IO.AssetDatabase.IAssetData AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, System.Type type, Colossal.Hash128 forceGuid);
```

- `public abstract Exists<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath path, TAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean Exists<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath path, TAssetData& asset);
```

- `public abstract MarkForDeletion() : System.Void`  

```csharp
public abstract System.Void MarkForDeletion();
```

- `public abstract MoveAssetTo(Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath = null) : System.Void`  

```csharp
public abstract System.Void MoveAssetTo(Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath);
```



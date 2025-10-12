# Colossal.IO.AssetDatabase.ILocalAssetDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabase`, `System.IDisposable`, `Colossal.IO.AssetDatabase.IDataSourceAccessor`  

## Properties

- `public Colossal.IO.AssetDatabase.DataSourceCacheState cacheState { get }`  
- `public System.Boolean canWriteSettings { get }`  

## Methods

- `public abstract AddAsset<TAssetData, TData>(Colossal.IO.AssetDatabase.AssetDataPath name, TData data, Colossal.Hash128 forceGuid = null) : TAssetData`  
- `public abstract AddAsset<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid = null) : TAssetData`  
- `public abstract AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, Colossal.Hash128 forceGuid = null) : Colossal.IO.AssetDatabase.IAssetData`  
- `public abstract AddAsset(Colossal.IO.AssetDatabase.AssetDataPath name, System.Type type, Colossal.Hash128 forceGuid = null) : Colossal.IO.AssetDatabase.IAssetData`  
- `public abstract Exists<TAssetData>(Colossal.IO.AssetDatabase.AssetDataPath path, TAssetData& asset) : System.Boolean`  
- `public abstract MarkForDeletion() : System.Void`  
- `public abstract MoveAssetTo(Colossal.IO.AssetDatabase.IAssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, Colossal.IO.AssetDatabase.AssetDataPath newPath = null) : System.Void`  


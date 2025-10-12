# Colossal.IO.AssetDatabase.IAssetDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Properties

- `public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get }`  
- `public System.Boolean areNotificationsEnabled { get }`  
- `public System.Boolean isCached { get }`  
- `public System.String name { get }`  
- `public System.String hostname { get }`  
- `public System.String rootPath { get }`  
- `public System.Int32 count { get }`  

## Methods

- `public abstract AllAssets() : System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData>`  
- `public abstract ClearCache() : System.Void`  
- `public abstract DeleteAsset<T>(T asset) : System.Void`  
- `public abstract DeleteAsset(Colossal.Hash128 guid) : System.Void`  
- `public abstract DisableNotificationsScoped() : Colossal.IO.AssetDatabase.DisableNotificationsScoped`  
- `public abstract EnableNotifications(System.Boolean enable) : System.Void`  
- `public abstract GetAsset<TAssetData>(System.Uri uri) : TAssetData`  
- `public abstract GetAsset<TAssetData>(System.String uri) : TAssetData`  
- `public abstract GetAsset<TAssetData>(Colossal.Hash128 guid) : TAssetData`  
- `public abstract GetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter = null) : TAssetData`  
- `public abstract GetAsset(System.Uri uri) : Colossal.IO.AssetDatabase.IAssetData`  
- `public abstract GetAsset(System.String uri) : Colossal.IO.AssetDatabase.IAssetData`  
- `public abstract GetAsset(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IAssetData`  
- `public abstract GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter = null) : Colossal.IO.AssetDatabase.IAssetData`  
- `public abstract GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter = null) : System.Collections.Generic.IEnumerable<T>`  
- `public abstract LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj) : System.Void`  
- `public abstract ResaveCache() : System.Threading.Tasks.Task<System.String>`  
- `public abstract SaveCache() : System.Void`  
- `public abstract TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset) : System.Boolean`  
- `public abstract TryGetAsset<TAssetData>(System.String uri, TAssetData& asset) : System.Boolean`  
- `public abstract TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& assetData) : System.Boolean`  
- `public abstract TryGetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter, TAssetData& asset) : System.Boolean`  
- `public abstract TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public abstract TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public abstract TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public abstract TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public abstract UnloadAllAssets() : System.Void`  


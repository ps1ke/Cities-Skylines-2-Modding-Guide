# Colossal.IO.AssetDatabase.IAssetDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IAssetDatabase : System.IDisposable
{
    public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get; }
    public System.Boolean areNotificationsEnabled { get; }
    public System.Boolean isCached { get; }
    public System.String name { get; }
    public System.String hostname { get; }
    public System.String rootPath { get; }
    public System.Int32 count { get; }

    public abstract System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> AllAssets();
    public abstract System.Void ClearCache();
    public abstract System.Void DeleteAsset<T>(T asset);
    public abstract System.Void DeleteAsset(Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.DisableNotificationsScoped DisableNotificationsScoped();
    public abstract System.Void EnableNotifications(System.Boolean enable);
    public abstract TAssetData GetAsset<TAssetData>(System.Uri uri);
    public abstract TAssetData GetAsset<TAssetData>(System.String uri);
    public abstract TAssetData GetAsset<TAssetData>(Colossal.Hash128 guid);
    public abstract TAssetData GetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter);
    public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(System.Uri uri);
    public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(System.String uri);
    public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.Hash128 guid);
    public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter);
    public abstract System.Collections.Generic.IEnumerable<T> GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter);
    public abstract System.Void LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj);
    public abstract System.Threading.Tasks.Task<System.String> ResaveCache();
    public abstract System.Void SaveCache();
    public abstract System.Boolean TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset);
    public abstract System.Boolean TryGetAsset<TAssetData>(System.String uri, TAssetData& asset);
    public abstract System.Boolean TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& assetData);
    public abstract System.Boolean TryGetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter, TAssetData& asset);
    public abstract System.Boolean TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset);
    public abstract System.Boolean TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset);
    public abstract System.Boolean TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset);
    public abstract System.Boolean TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset);
    public abstract System.Void UnloadAllAssets();
}
```


## Properties

- `public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get }`  

```csharp
public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get; }
```

- `public System.Boolean areNotificationsEnabled { get }`  

```csharp
public System.Boolean areNotificationsEnabled { get; }
```

- `public System.Boolean isCached { get }`  

```csharp
public System.Boolean isCached { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String hostname { get }`  

```csharp
public System.String hostname { get; }
```

- `public System.String rootPath { get }`  

```csharp
public System.String rootPath { get; }
```

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Methods

- `public abstract AllAssets() : System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> AllAssets();
```

- `public abstract ClearCache() : System.Void`  

```csharp
public abstract System.Void ClearCache();
```

- `public abstract DeleteAsset<T>(T asset) : System.Void`  

```csharp
public abstract System.Void DeleteAsset<T>(T asset);
```

- `public abstract DeleteAsset(Colossal.Hash128 guid) : System.Void`  

```csharp
public abstract System.Void DeleteAsset(Colossal.Hash128 guid);
```

- `public abstract DisableNotificationsScoped() : Colossal.IO.AssetDatabase.DisableNotificationsScoped`  

```csharp
public abstract Colossal.IO.AssetDatabase.DisableNotificationsScoped DisableNotificationsScoped();
```

- `public abstract EnableNotifications(System.Boolean enable) : System.Void`  

```csharp
public abstract System.Void EnableNotifications(System.Boolean enable);
```

- `public abstract GetAsset<TAssetData>(System.Uri uri) : TAssetData`  

```csharp
public abstract TAssetData GetAsset<TAssetData>(System.Uri uri);
```

- `public abstract GetAsset<TAssetData>(System.String uri) : TAssetData`  

```csharp
public abstract TAssetData GetAsset<TAssetData>(System.String uri);
```

- `public abstract GetAsset<TAssetData>(Colossal.Hash128 guid) : TAssetData`  

```csharp
public abstract TAssetData GetAsset<TAssetData>(Colossal.Hash128 guid);
```

- `public abstract GetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter = null) : TAssetData`  

```csharp
public abstract TAssetData GetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter);
```

- `public abstract GetAsset(System.Uri uri) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(System.Uri uri);
```

- `public abstract GetAsset(System.String uri) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(System.String uri);
```

- `public abstract GetAsset(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.Hash128 guid);
```

- `public abstract GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter = null) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public abstract Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter);
```

- `public abstract GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter = null) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<T> GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter);
```

- `public abstract LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj) : System.Void`  

```csharp
public abstract System.Void LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj);
```

- `public abstract ResaveCache() : System.Threading.Tasks.Task<System.String>`  

```csharp
public abstract System.Threading.Tasks.Task<System.String> ResaveCache();
```

- `public abstract SaveCache() : System.Void`  

```csharp
public abstract System.Void SaveCache();
```

- `public abstract TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset);
```

- `public abstract TryGetAsset<TAssetData>(System.String uri, TAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset<TAssetData>(System.String uri, TAssetData& asset);
```

- `public abstract TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& assetData) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& assetData);
```

- `public abstract TryGetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter, TAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset<TAssetData>(Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter, TAssetData& asset);
```

- `public abstract TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public abstract TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public abstract TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public abstract TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public abstract System.Boolean TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public abstract UnloadAllAssets() : System.Void`  

```csharp
public abstract System.Void UnloadAllAssets();
```



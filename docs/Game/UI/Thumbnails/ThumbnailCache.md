# Game.UI.Thumbnails.ThumbnailCache

**Assembly:** `Game`  
**Namespace:** `Game.UI.Thumbnails`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class ThumbnailCache : System.IDisposable
{
    private System.Collections.Generic.Dictionary<Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey, Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo> m_CacheData;

    public ThumbnailCache();

    public System.Void Dispose();
    public Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo GetCachedThumbnail(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey key);
    public Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo GetThumbnail(System.Object obj, System.Int32 width, System.Int32 height, UnityEngine.Camera camera);
    public System.Void Initialize();
    private System.Void LoadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset);
    private System.Void OnAtlasAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    public System.Void Refresh();
    private System.Void UnloadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset);
    public System.Void Update();
}
```


## Fields

- `private System.Collections.Generic.Dictionary<Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey, Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo> m_CacheData`  

```csharp
private System.Collections.Generic.Dictionary<Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey, Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo> m_CacheData;
```


## Constructors

- `public ThumbnailCache()`  

```csharp
public ThumbnailCache();
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetCachedThumbnail(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey key) : Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  

```csharp
public Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo GetCachedThumbnail(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey key);
```

- `public GetThumbnail(System.Object obj, System.Int32 width, System.Int32 height, UnityEngine.Camera camera = null) : Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  

```csharp
public Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo GetThumbnail(System.Object obj, System.Int32 width, System.Int32 height, UnityEngine.Camera camera);
```

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `private LoadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset) : System.Void`  

```csharp
private System.Void LoadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset);
```

- `private OnAtlasAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void OnAtlasAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `public Refresh() : System.Void`  

```csharp
public System.Void Refresh();
```

- `private UnloadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset) : System.Void`  

```csharp
private System.Void UnloadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Nested types

- `Game.UI.Thumbnails.ThumbnailCache+Status`  
- `Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  
- `Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey`  


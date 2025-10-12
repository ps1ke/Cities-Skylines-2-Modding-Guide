# Game.UI.Thumbnails.ThumbnailCache

**Assembly:** `Game`  
**Namespace:** `Game.UI.Thumbnails`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Collections.Generic.Dictionary<Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey, Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo> m_CacheData`  

## Constructors

- `public ThumbnailCache()`  

## Methods

- `public Dispose() : System.Void`  
- `public GetCachedThumbnail(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey key) : Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  
- `public GetThumbnail(System.Object obj, System.Int32 width, System.Int32 height, UnityEngine.Camera camera = null) : Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  
- `public Initialize() : System.Void`  
- `private LoadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset) : System.Void`  
- `private OnAtlasAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `public Refresh() : System.Void`  
- `private UnloadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset) : System.Void`  
- `public Update() : System.Void`  

## Nested types

- `Game.UI.Thumbnails.ThumbnailCache+Status`  
- `Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  
- `Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey`  


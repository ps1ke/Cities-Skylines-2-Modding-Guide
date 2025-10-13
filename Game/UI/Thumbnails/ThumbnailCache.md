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
public ThumbnailCache()
	{
		m_CacheData = new Dictionary<ThumbnailKey, ThumbnailInfo>();
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		foreach (KeyValuePair<ThumbnailKey, ThumbnailInfo> cacheDatum in m_CacheData)
		{
			cacheDatum.Value.baseObjectRef = null;
		}
	}
```

- `public GetCachedThumbnail(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey key) : Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  

```csharp
public ThumbnailInfo GetCachedThumbnail(ThumbnailKey key)
	{
		if (m_CacheData.TryGetValue(key, out var value))
		{
			return value;
		}
		return null;
	}
```

- `public GetThumbnail(System.Object obj, System.Int32 width, System.Int32 height, UnityEngine.Camera camera = null) : Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  

```csharp
public ThumbnailInfo GetThumbnail(object obj, int width, int height, Camera camera = null)
	{
		ThumbnailInfo value = null;
		UnityEngine.Object obj2 = obj as UnityEngine.Object;
		if (obj2 != null)
		{
			ThumbnailKey key = new ThumbnailKey(obj2.name, width, height);
			m_CacheData.TryGetValue(key, out value);
		}
		return value;
	}
```

- `public Initialize() : System.Void`  

```csharp
public void Initialize()
	{
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe<AtlasAsset>(OnAtlasAssetChanged, AssetChangedEventArgs.Default);
	}
```

- `private LoadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset) : System.Void`  

```csharp
private void LoadAtlas(AtlasAsset asset)
	{
		try
		{
			AtlasFrame atlasFrame = asset.Load();
			foreach (AtlasFrame.Entry item in asset)
			{
				m_CacheData.Add(new ThumbnailKey(item.name, (int)item.region.width, (int)item.region.height), new ThumbnailInfo
				{
					atlasFrame = atlasFrame,
					region = item.region,
					status = Status.Ready
				});
			}
		}
		catch (Exception exception)
		{
			UnityEngine.Debug.LogException(exception);
		}
	}
```

- `private OnAtlasAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private void OnAtlasAssetChanged(AssetChangedEventArgs args)
	{
		if (args.change == ChangeType.BulkAssetsChange)
		{
			m_CacheData.Clear();
			{
				foreach (AtlasAsset asset in AssetDatabase.global.GetAssets(default(SearchFilter<AtlasAsset>)))
				{
					LoadAtlas(asset);
				}
				return;
			}
		}
		if (args.change == ChangeType.AssetAdded || args.change == ChangeType.AssetUpdated)
		{
			LoadAtlas((AtlasAsset)args.asset);
		}
		else if (args.change == ChangeType.AssetDeleted)
		{
			UnloadAtlas((AtlasAsset)args.asset);
		}
	}
```

- `public Refresh() : System.Void`  

```csharp
public void Refresh()
	{
		foreach (KeyValuePair<ThumbnailKey, ThumbnailInfo> cacheDatum in m_CacheData)
		{
			cacheDatum.Value.status = Status.Pending;
		}
	}
```

- `private UnloadAtlas(Colossal.IO.AssetDatabase.AtlasAsset asset) : System.Void`  

```csharp
private void UnloadAtlas(AtlasAsset asset)
	{
		try
		{
			using (asset)
			{
				asset.Load();
				foreach (AtlasFrame.Entry item in asset)
				{
					m_CacheData.Remove(new ThumbnailKey(item.name, (int)item.region.width, (int)item.region.height));
				}
				asset.Unload();
			}
		}
		catch (Exception exception)
		{
			UnityEngine.Debug.LogException(exception);
		}
	}
```

- `public Update() : System.Void`  

```csharp
public void Update()
	{
	}
```


## Nested types

- `Game.UI.Thumbnails.ThumbnailCache+Status`  
- `Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo`  
- `Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey`  


# Game.UI.Menu.AssetUploadUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AssetUploadUtils
{
    private static Colossal.Logging.ILog sLog;

    public static Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData defaultExternalLink { get; }

    private static System.Void CollectExtraPrefabDependencies(Game.Prefabs.PrefabBase prefab, Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabDependencies);
    public static System.Void CollectPrefabAssetDependencies(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> dependencies, System.Boolean collectReverseDependencies);
    public static System.Void CollectPrefabDependencies(Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabs, System.Boolean collectReverseDependencies);
    public static System.Void CopyAsset(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID);
    public static T CopyAssetGeneric<T>(T asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid);
    public static Colossal.IO.AssetDatabase.AssetData CopyAssetGeneric(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid);
    public static System.Void CopyMap(Game.Assets.MapMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed);
    public static System.Void CopyPrefab(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID);
    public static Colossal.IO.AssetDatabase.AssetData CopyPreviewImage(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Colossal.IO.AssetDatabase.AssetDataPath path);
    public static System.Void CopySave(Game.Assets.SaveGameMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed);
    public static System.Void CreateThumbnailAtlas(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    private static System.Void GetAssets(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> assets);
    public static System.String GetImageURI(Colossal.IO.AssetDatabase.AssetData asset);
    public static System.Boolean LockLinkType(System.String url, System.String& type);
    public static System.Boolean TryGetPreview(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.AssetData& result);
    public static System.Boolean ValidateExternalLink(Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link);
    public static System.Boolean ValidateExternalLinks(System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links);
    public static System.Boolean ValidateForumLink(System.String link);
}
```


## Fields

- `private static Colossal.Logging.ILog sLog`  

```csharp
private static Colossal.Logging.ILog sLog;
```


## Properties

- `public static Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData defaultExternalLink { get }`  

```csharp
public static Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData defaultExternalLink { get; }
```


## Methods

- `private static CollectExtraPrefabDependencies(Game.Prefabs.PrefabBase prefab, Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabDependencies) : System.Void`  

```csharp
private static void CollectExtraPrefabDependencies(PrefabBase prefab, PrefabBase mainPrefab, List<PrefabBase> prefabDependencies)
	{
		if (prefab is ZonePrefab zonePrefab && (prefab == mainPrefab || (prefab.TryGet<AssetPackItem>(out var component) && component.m_Packs != null && component.m_Packs.Contains(mainPrefab))))
		{
			foreach (PrefabAsset asset in AssetDatabase.global.GetAssets(default(SearchFilter<PrefabAsset>)))
			{
				if (asset.Load() is PrefabBase prefabBase && prefabBase.TryGet<SpawnableBuilding>(out var component2) && component2.m_ZoneType == zonePrefab)
				{
					prefabDependencies.Add(prefabBase);
				}
			}
			return;
		}
		if (!(prefab is AssetPackPrefab value) || !(prefab == mainPrefab))
		{
			return;
		}
		foreach (PrefabAsset asset2 in AssetDatabase.global.GetAssets(default(SearchFilter<PrefabAsset>)))
		{
			if (asset2.Load() is PrefabBase prefabBase2 && prefabBase2.TryGet<AssetPackItem>(out var component3) && component3.m_Packs != null && component3.m_Packs.Contains(value))
			{
				prefabDependencies.Add(prefabBase2);
			}
		}
	}
```

- `public static CollectPrefabAssetDependencies(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> dependencies, System.Boolean collectReverseDependencies) : System.Void`  

```csharp
public static void CollectPrefabAssetDependencies(PrefabAsset prefabAsset, HashSet<AssetData> dependencies, bool collectReverseDependencies)
	{
		HashSet<PrefabBase> hashSet = new HashSet<PrefabBase>();
		CollectPrefabDependencies(prefabAsset.Load() as PrefabBase, hashSet, collectReverseDependencies);
		foreach (PrefabBase item in hashSet)
		{
			List<AssetData> list = new List<AssetData>();
			GetAssets(item, list);
			foreach (AssetData item2 in list)
			{
				if (item2.database != AssetDatabase.game)
				{
					dependencies.Add(item2);
				}
			}
		}
	}
```

- `public static CollectPrefabDependencies(Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabs, System.Boolean collectReverseDependencies) : System.Void`  

```csharp
public static void CollectPrefabDependencies(PrefabBase mainPrefab, HashSet<PrefabBase> prefabs, bool collectReverseDependencies)
	{
		if (prefabs.Contains(mainPrefab))
		{
			return;
		}
		Stack<PrefabBase> stack = new Stack<PrefabBase>();
		stack.Push(mainPrefab);
		prefabs.Add(mainPrefab);
		PrefabBase result;
		while (stack.TryPop(out result))
		{
			List<PrefabBase> list = new List<PrefabBase>();
			List<ComponentBase> list2 = new List<ComponentBase>();
			result.GetComponents(list2);
			foreach (ComponentBase item in list2)
			{
				item.GetDependencies(list);
			}
			if (collectReverseDependencies)
			{
				CollectExtraPrefabDependencies(result, mainPrefab, list);
			}
			foreach (PrefabBase item2 in list)
			{
				if (item2 != null && item2.asset != null && item2.asset.database != AssetDatabase.game && !prefabs.Contains(item2))
				{
					stack.Push(item2);
					prefabs.Add(item2);
				}
			}
		}
	}
```

- `public static CopyAsset(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID = 0) : System.Void`  

```csharp
public static void CopyAsset(AssetData asset, ILocalAssetDatabase database, Dictionary<AssetData, AssetData> processed, HashSet<IModsUploadSupport.ModInfo.ModDependency> externalReferences, bool copyReverseDependencies, bool binaryPackAssets, int platformID = 0)
	{
		if (asset is MapMetadata metadata)
		{
			CopyMap(metadata, database, processed);
		}
		else if (asset is SaveGameMetadata metadata2)
		{
			CopySave(metadata2, database, processed);
		}
		else if (asset is PrefabAsset prefabAsset)
		{
			CopyPrefab(prefabAsset, database, processed, externalReferences, copyReverseDependencies, binaryPackAssets, platformID);
		}
		else
		{
			CopyAssetGeneric(asset, database, processed, keepGuid: true);
		}
	}
```

- `public static CopyAssetGeneric<T>(T asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid = False) : T`  

```csharp
public static T CopyAssetGeneric<T>(T asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid);
```

- `public static CopyAssetGeneric(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid = False) : Colossal.IO.AssetDatabase.AssetData`  

```csharp
public static AssetData CopyAssetGeneric(AssetData asset, ILocalAssetDatabase database, Dictionary<AssetData, AssetData> processed, bool keepGuid = false)
	{
		if (processed.TryGetValue(asset, out var value))
		{
			return value;
		}
		using Stream stream = asset.GetReadStream();
		value = database.AddAsset(asset.name, asset.GetType(), keepGuid ? asset.id : default(Identifier)) as AssetData;
		using (Stream destination = value.GetWriteStream())
		{
			stream.CopyTo(destination);
		}
		processed.Add(asset, value);
		return value;
	}
```

- `public static CopyMap(Game.Assets.MapMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed) : System.Void`  

```csharp
public static void CopyMap(MapMetadata metadata, ILocalAssetDatabase database, Dictionary<AssetData, AssetData> processed)
	{
		MapInfo mapInfo = metadata.target.Copy();
		MapData mapData = CopyAssetGeneric(mapInfo.mapData, database, processed);
		mapInfo.mapData = mapData;
		if (metadata.target.preview != null)
		{
			TextureAsset preview = CopyAssetGeneric(mapInfo.preview, database, processed);
			mapInfo.preview = preview;
		}
		if (metadata.target.thumbnail != null)
		{
			TextureAsset thumbnail = CopyAssetGeneric(mapInfo.thumbnail, database, processed);
			mapInfo.thumbnail = thumbnail;
		}
		if (mapInfo.localeAssets != null)
		{
			LocaleAsset[] array = new LocaleAsset[mapInfo.localeAssets.Length];
			for (int i = 0; i < mapInfo.localeAssets.Length; i++)
			{
				array[i] = CopyAssetGeneric(mapInfo.localeAssets[i], database, processed);
			}
			mapInfo.localeAssets = array;
		}
		if (mapInfo.climate != null)
		{
			mapInfo.climate = CopyAssetGeneric(mapInfo.climate, database, processed);
		}
		MapMetadata mapMetadata = (mapInfo.metaData = CopyAssetGeneric(metadata, database, processed));
		mapMetadata.target = mapInfo;
		mapMetadata.Save();
	}
```

- `public static CopyPrefab(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID = 0) : System.Void`  

```csharp
public static void CopyPrefab(PrefabAsset prefabAsset, ILocalAssetDatabase database, Dictionary<AssetData, AssetData> processed, HashSet<IModsUploadSupport.ModInfo.ModDependency> externalReferences, bool copyReverseDependencies, bool binaryPackAssets, int platformID = 0)
	{
		HashSet<AssetData> hashSet = new HashSet<AssetData>();
		CollectPrefabAssetDependencies(prefabAsset, hashSet, copyReverseDependencies);
		foreach (AssetData item in hashSet)
		{
			if (processed.ContainsKey(item))
			{
				continue;
			}
			SourceMeta meta = item.GetMeta();
			if (meta.platformID > 0 && meta.platformID != platformID)
			{
				externalReferences.Add(new IModsUploadSupport.ModInfo.ModDependency
				{
					m_Id = meta.platformID,
					m_Version = meta.platformVersion
				});
				continue;
			}
			AssetData value;
			if (binaryPackAssets && item is PrefabAsset prefabAsset2)
			{
				PrefabBase obj = (PrefabBase)prefabAsset2.Load();
				PrefabBase data = obj.Clone(obj.name);
				PrefabAsset prefabAsset3 = database.AddAsset<PrefabAsset, ScriptableObject>(item.name, data, item.id);
				prefabAsset3.Save(ContentType.Binary, includeUnityDependencies: false, force: true);
				value = prefabAsset3;
			}
			else
			{
				value = CopyAssetGeneric(item, database, processed, !(item is LocaleAsset));
			}
			processed[item] = value;
		}
	}
```

- `public static CopyPreviewImage(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Colossal.IO.AssetDatabase.AssetDataPath path) : Colossal.IO.AssetDatabase.AssetData`  

```csharp
public static AssetData CopyPreviewImage(AssetData asset, ILocalAssetDatabase database, AssetDataPath path)
	{
		try
		{
			if (asset is ImageAsset imageAsset)
			{
				return imageAsset.Save(ImageAsset.FileFormat.JPG, path, database);
			}
			if (asset is TextureAsset textureAsset)
			{
				return textureAsset.SaveAsImageAsset(ImageAsset.FileFormat.JPG, path, database);
			}
		}
		catch (Exception exception)
		{
			sLog.Error(exception);
		}
		return null;
	}
```

- `public static CopySave(Game.Assets.SaveGameMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed) : System.Void`  

```csharp
public static void CopySave(SaveGameMetadata metadata, ILocalAssetDatabase database, Dictionary<AssetData, AssetData> processed)
	{
		SaveInfo saveInfo = metadata.target.Copy();
		SaveGameData saveGameData = CopyAssetGeneric(saveInfo.saveGameData, database, processed);
		saveInfo.saveGameData = saveGameData;
		if (metadata.target.preview != null)
		{
			TextureAsset preview = CopyAssetGeneric(saveInfo.preview, database, processed);
			saveInfo.preview = preview;
		}
		SaveGameMetadata saveGameMetadata = (saveInfo.metaData = CopyAssetGeneric(metadata, database, processed));
		saveGameMetadata.target = saveInfo;
		saveGameMetadata.Save();
	}
```

- `public static CreateThumbnailAtlas(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public static void CreateThumbnailAtlas(Dictionary<AssetData, AssetData> processed, ILocalAssetDatabase database)
	{
		AtlasFrame atlasFrame = new AtlasFrame(0, 0, rotations: false, 0);
		HashSet<AssetData> hashSet = new HashSet<AssetData>();
		foreach (AssetData key in processed.Keys)
		{
			if (!(key is PrefabAsset prefabAsset))
			{
				continue;
			}
			foreach (EditorPrefabUtils.IconInfo icon in EditorPrefabUtils.GetIcons((PrefabBase)prefabAsset.Load()))
			{
				if (processed.TryGetValue(icon.m_Asset, out var value))
				{
					PrefabAsset prefabAsset2 = (PrefabAsset)processed[prefabAsset];
					ComponentBase componentExactly = ((PrefabBase)prefabAsset2.Load()).GetComponentExactly(icon.m_Component.GetType());
					UnityEngine.Debug.Log($"{prefabAsset2.name}: {value.name}\n{icon.m_Field.DeclaringType?.Name}.{icon.m_Field.Name}: {icon.m_Field.GetValue(componentExactly)}");
					if (atlasFrame.TryAdd(value.name, ((ImageAsset)value).Load()))
					{
						icon.m_Field.SetValue(componentExactly, "thumbnail://insert thumbnail URI here");
						hashSet.Add(value);
						prefabAsset2.Save(force: true);
					}
				}
			}
		}
		if (hashSet.Count <= 0)
		{
			return;
		}
		database.AddAsset("ThumbnailAtlas", atlasFrame);
		foreach (AssetData item in hashSet)
		{
			database.DeleteAsset(item);
		}
	}
```

- `private static GetAssets(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> assets) : System.Void`  

```csharp
private static void GetAssets(PrefabBase prefab, List<AssetData> assets)
	{
		assets.Add(prefab.asset);
		if (prefab is RenderPrefab renderPrefab)
		{
			assets.Add(renderPrefab.geometryAsset);
			foreach (SurfaceAsset surfaceAsset in renderPrefab.surfaceAssets)
			{
				assets.Add(surfaceAsset);
				surfaceAsset.LoadProperties(useVT: false);
				foreach (TextureAsset value in surfaceAsset.textures.Values)
				{
					assets.Add(value);
				}
			}
		}
		foreach (LocaleAsset localeAsset in EditorPrefabUtils.GetLocaleAssets(prefab))
		{
			assets.Add(localeAsset);
		}
		foreach (EditorPrefabUtils.IconInfo icon in EditorPrefabUtils.GetIcons(prefab))
		{
			assets.Add(icon.m_Asset);
		}
	}
```

- `public static GetImageURI(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
public static string GetImageURI(AssetData asset)
	{
		if (asset is ImageAsset asset2)
		{
			return asset2.ToUri();
		}
		if (asset is TextureAsset asset3)
		{
			return asset3.ToUri();
		}
		return MenuHelpers.defaultPreview.ToUri();
	}
```

- `public static LockLinkType(System.String url, System.String& type) : System.Boolean`  

```csharp
public static bool LockLinkType(string url, out string type)
	{
		string text = url.ToLower().Trim();
		IModsUploadSupport.ExternalLinkInfo[] kAcceptedTypes = IModsUploadSupport.ExternalLinkInfo.kAcceptedTypes;
		for (int i = 0; i < kAcceptedTypes.Length; i++)
		{
			IModsUploadSupport.ExternalLinkInfo externalLinkInfo = kAcceptedTypes[i];
			string[] uRLs = externalLinkInfo.m_URLs;
			foreach (string text2 in uRLs)
			{
				if (text.StartsWith(text2 + "/") && text.Length >= text2.Length + 2)
				{
					type = externalLinkInfo.m_Type;
					return true;
				}
				if (text.StartsWith("https://" + text2 + "/") && text.Length >= text2.Length + 10)
				{
					type = externalLinkInfo.m_Type;
					return true;
				}
			}
		}
		type = null;
		return false;
	}
```

- `public static TryGetPreview(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.AssetData& result) : System.Boolean`  

```csharp
public static bool TryGetPreview(AssetData asset, out AssetData result)
	{
		if (asset is SaveGameMetadata saveGameMetadata)
		{
			result = saveGameMetadata.target.preview;
			return result != null;
		}
		if (asset is MapMetadata mapMetadata)
		{
			result = mapMetadata.target.preview;
			return result != null;
		}
		if (asset is PrefabAsset prefabAsset && prefabAsset.Load() is PrefabBase prefabBase && prefabBase.TryGet<UIObject>(out var component) && UIExtensions.TryGetImageAsset(component.m_Icon, out var imageAsset))
		{
			result = imageAsset;
			return true;
		}
		result = null;
		return false;
	}
```

- `public static ValidateExternalLink(Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link) : System.Boolean`  

```csharp
public static bool ValidateExternalLink(IModsUploadSupport.ExternalLinkData link)
	{
		if (string.IsNullOrWhiteSpace(link.m_URL))
		{
			return true;
		}
		if (LockLinkType(link.m_URL, out var type) && type == link.m_Type)
		{
			return true;
		}
		return false;
	}
```

- `public static ValidateExternalLinks(System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links) : System.Boolean`  

```csharp
public static bool ValidateExternalLinks(IEnumerable<IModsUploadSupport.ExternalLinkData> links)
	{
		foreach (IModsUploadSupport.ExternalLinkData link in links)
		{
			if (!ValidateExternalLink(link))
			{
				return false;
			}
		}
		return true;
	}
```

- `public static ValidateForumLink(System.String link) : System.Boolean`  

```csharp
public static bool ValidateForumLink(string link)
	{
		if (string.IsNullOrWhiteSpace(link))
		{
			return true;
		}
		return link.ToLower().Contains("paradoxplaza.com");
	}
```



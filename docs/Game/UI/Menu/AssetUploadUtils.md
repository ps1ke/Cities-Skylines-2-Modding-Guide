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
private static System.Void CollectExtraPrefabDependencies(Game.Prefabs.PrefabBase prefab, Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabDependencies);
```

- `public static CollectPrefabAssetDependencies(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> dependencies, System.Boolean collectReverseDependencies) : System.Void`  

```csharp
public static System.Void CollectPrefabAssetDependencies(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> dependencies, System.Boolean collectReverseDependencies);
```

- `public static CollectPrefabDependencies(Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabs, System.Boolean collectReverseDependencies) : System.Void`  

```csharp
public static System.Void CollectPrefabDependencies(Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabs, System.Boolean collectReverseDependencies);
```

- `public static CopyAsset(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID = 0) : System.Void`  

```csharp
public static System.Void CopyAsset(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID);
```

- `public static CopyAssetGeneric<T>(T asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid = False) : T`  

```csharp
public static T CopyAssetGeneric<T>(T asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid);
```

- `public static CopyAssetGeneric(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid = False) : Colossal.IO.AssetDatabase.AssetData`  

```csharp
public static Colossal.IO.AssetDatabase.AssetData CopyAssetGeneric(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid);
```

- `public static CopyMap(Game.Assets.MapMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed) : System.Void`  

```csharp
public static System.Void CopyMap(Game.Assets.MapMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed);
```

- `public static CopyPrefab(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID = 0) : System.Void`  

```csharp
public static System.Void CopyPrefab(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID);
```

- `public static CopyPreviewImage(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Colossal.IO.AssetDatabase.AssetDataPath path) : Colossal.IO.AssetDatabase.AssetData`  

```csharp
public static Colossal.IO.AssetDatabase.AssetData CopyPreviewImage(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Colossal.IO.AssetDatabase.AssetDataPath path);
```

- `public static CopySave(Game.Assets.SaveGameMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed) : System.Void`  

```csharp
public static System.Void CopySave(Game.Assets.SaveGameMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed);
```

- `public static CreateThumbnailAtlas(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public static System.Void CreateThumbnailAtlas(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
```

- `private static GetAssets(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> assets) : System.Void`  

```csharp
private static System.Void GetAssets(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> assets);
```

- `public static GetImageURI(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
public static System.String GetImageURI(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public static LockLinkType(System.String url, System.String& type) : System.Boolean`  

```csharp
public static System.Boolean LockLinkType(System.String url, System.String& type);
```

- `public static TryGetPreview(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.AssetData& result) : System.Boolean`  

```csharp
public static System.Boolean TryGetPreview(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.AssetData& result);
```

- `public static ValidateExternalLink(Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link) : System.Boolean`  

```csharp
public static System.Boolean ValidateExternalLink(Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link);
```

- `public static ValidateExternalLinks(System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links) : System.Boolean`  

```csharp
public static System.Boolean ValidateExternalLinks(System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links);
```

- `public static ValidateForumLink(System.String link) : System.Boolean`  

```csharp
public static System.Boolean ValidateForumLink(System.String link);
```



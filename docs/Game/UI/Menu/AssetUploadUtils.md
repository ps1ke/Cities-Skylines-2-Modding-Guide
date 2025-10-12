# Game.UI.Menu.AssetUploadUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static Colossal.Logging.ILog sLog`  

## Properties

- `public static Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData defaultExternalLink { get }`  

## Methods

- `private static CollectExtraPrefabDependencies(Game.Prefabs.PrefabBase prefab, Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabDependencies) : System.Void`  
- `public static CollectPrefabAssetDependencies(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> dependencies, System.Boolean collectReverseDependencies) : System.Void`  
- `public static CollectPrefabDependencies(Game.Prefabs.PrefabBase mainPrefab, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabs, System.Boolean collectReverseDependencies) : System.Void`  
- `public static CopyAsset(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID = 0) : System.Void`  
- `public static CopyAssetGeneric<T>(T asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid = False) : T`  
- `public static CopyAssetGeneric(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Boolean keepGuid = False) : Colossal.IO.AssetDatabase.AssetData`  
- `public static CopyMap(Game.Assets.MapMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed) : System.Void`  
- `public static CopyPrefab(Colossal.IO.AssetDatabase.PrefabAsset prefabAsset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences, System.Boolean copyReverseDependencies, System.Boolean binaryPackAssets, System.Int32 platformID = 0) : System.Void`  
- `public static CopyPreviewImage(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Colossal.IO.AssetDatabase.AssetDataPath path) : Colossal.IO.AssetDatabase.AssetData`  
- `public static CopySave(Game.Assets.SaveGameMetadata metadata, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed) : System.Void`  
- `public static CreateThumbnailAtlas(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> processed, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  
- `private static GetAssets(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> assets) : System.Void`  
- `public static GetImageURI(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  
- `public static LockLinkType(System.String url, System.String& type) : System.Boolean`  
- `public static TryGetPreview(Colossal.IO.AssetDatabase.AssetData asset, Colossal.IO.AssetDatabase.AssetData& result) : System.Boolean`  
- `public static ValidateExternalLink(Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link) : System.Boolean`  
- `public static ValidateExternalLinks(System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links) : System.Boolean`  
- `public static ValidateForumLink(System.String link) : System.Boolean`  


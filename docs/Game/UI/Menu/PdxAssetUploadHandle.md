# Game.UI.Menu.PdxAssetUploadHandle

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class PdxAssetUploadHandle
{
    private Colossal.Logging.ILog log;
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Screenshots;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Assets;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_OriginalPreviews;
    private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> m_WIPAssets;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AdditionalAssets;
    private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_CachedAssetDependencies;
    private Colossal.IO.AssetDatabase.AssetData <mainAsset>k__BackingField;
    private System.Boolean <hasPrefabAssets>k__BackingField;
    private Colossal.IO.AssetDatabase.AssetData <preview>k__BackingField;
    private Colossal.PSI.Common.IModsUploadSupport+ModInfo <modInfo>k__BackingField;
    private System.Boolean <updateExisting>k__BackingField;
    private System.Int32 <processVT>k__BackingField;
    private System.Boolean <packThumbnailsAtlas>k__BackingField;
    private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> <authorMods>k__BackingField;
    private Colossal.PSI.Common.IModsUploadSupport+ModTag[] <availableTags>k__BackingField;
    private Colossal.PSI.Common.IModsUploadSupport+DLCTag[] <availableDLCs>k__BackingField;
    private System.Collections.Generic.HashSet<System.String> <typeTags>k__BackingField;
    private System.Collections.Generic.HashSet<System.String> <tags>k__BackingField;
    private System.Collections.Generic.List<System.String> <additionalTags>k__BackingField;
    private System.Boolean <binaryPackAssets>k__BackingField;
    private Colossal.PSI.Common.IModsUploadSupport+SocialProfile <socialProfile>k__BackingField;
    public System.Action onSocialProfileSynced;

    public Colossal.IO.AssetDatabase.AssetData mainAsset { get; private set; }
    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> assets { get; }
    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> additionalAssets { get; }
    public System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> cachedDependencies { get; }
    public System.Boolean hasPrefabAssets { get; private set; }
    public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AssetData> allAssets { get; }
    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> screenshots { get; }
    public Colossal.IO.AssetDatabase.AssetData preview { get; private set; }
    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> originalPreviews { get; }
    public Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo { get; set; }
    public System.Boolean updateExisting { get; set; }
    public System.Int32 processVT { get; set; }
    public System.Boolean packThumbnailsAtlas { get; set; }
    public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> authorMods { get; private set; }
    public Colossal.PSI.Common.IModsUploadSupport+ModTag[] availableTags { get; private set; }
    public Colossal.PSI.Common.IModsUploadSupport+DLCTag[] availableDLCs { get; private set; }
    public System.Collections.Generic.HashSet<System.String> typeTags { get; private set; }
    public System.Collections.Generic.HashSet<System.String> tags { get; private set; }
    public System.Collections.Generic.List<System.String> additionalTags { get; private set; }
    public System.Int32 tagCount { get; }
    public System.Boolean binaryPackAssets { get; set; }
    public Colossal.PSI.Common.IModsUploadSupport+SocialProfile socialProfile { get; private set; }

    public PdxAssetUploadHandle();
    public PdxAssetUploadHandle(Colossal.IO.AssetDatabase.AssetData mainAsset, Colossal.IO.AssetDatabase.AssetData[] assets);

    internal static System.Void <ExcludeSourceTextures>g__AddReferenceTo|92_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface);
    private System.Void <Initialize>b__86_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    public System.Void AddAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Void AddAdditionalTag(System.String tag);
    public System.Void AddScreenshot(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> BeginSubmit();
    public System.Threading.Tasks.Task Cleanup();
    public System.Void ClearScreenshots();
    private System.String[] CollectTags();
    private System.ValueTuple<System.Boolean, System.String> CopyFiles(System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences);
    private System.String CopyMetadata(Colossal.IO.AssetDatabase.AssetData asset, System.String name, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed);
    private System.Void CopyPreview(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed);
    private System.Void CopyScreenshot(Colossal.IO.AssetDatabase.AssetData asset, System.Int32 index, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed);
    public System.Void ExcludeSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> FinalizeSubmit();
    private System.Boolean FindByPath(Colossal.IO.AssetDatabase.ImageAsset candidate, System.String imagePath);
    public System.String GetAbsoluteContentPath();
    private System.String GetAbsoluteMetadataPath();
    private System.String GetContentPath();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo> GetExistingInfo();
    private System.String GetFilename(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>> GetLocalData(System.Int32 id);
    private System.String GetMetadataPath();
    private static System.ValueTuple<System.Collections.Generic.HashSet<System.String>, System.Collections.Generic.HashSet<System.String>> GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> validTags);
    private System.Void Initialize();
    private System.Void InitializeContentPrerequisite();
    private System.Void InitializePreviews();
    public System.Boolean LoggedIn();
    private System.Void OnModsUIClosed();
    private System.Void RebuildDependencyCache();
    private System.Void RefreshSocialProfile();
    public System.Void RemoveAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Void RemoveAdditionalTag(System.String tag);
    public System.Void RemoveScreenshot(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Void SetPreview(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Void SetPreviewsFromExisting(Colossal.PSI.Common.IModsUploadSupport+ModLocalData localData);
    public System.Void ShowModsUIProfilePage();
    public System.Threading.Tasks.Task SyncPlatformData();
}
```


## Fields

- `private Colossal.Logging.ILog log`  

```csharp
private Colossal.Logging.ILog log;
```

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Screenshots`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Screenshots;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Assets`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Assets;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_OriginalPreviews`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_OriginalPreviews;
```

- `private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> m_WIPAssets`  

```csharp
private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> m_WIPAssets;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AdditionalAssets`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AdditionalAssets;
```

- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_CachedAssetDependencies`  

```csharp
private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_CachedAssetDependencies;
```

- `private Colossal.IO.AssetDatabase.AssetData <mainAsset>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.AssetData <mainAsset>k__BackingField;
```

- `private System.Boolean <hasPrefabAssets>k__BackingField`  

```csharp
private System.Boolean <hasPrefabAssets>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.AssetData <preview>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.AssetData <preview>k__BackingField;
```

- `private Colossal.PSI.Common.IModsUploadSupport+ModInfo <modInfo>k__BackingField`  

```csharp
private Colossal.PSI.Common.IModsUploadSupport+ModInfo <modInfo>k__BackingField;
```

- `private System.Boolean <updateExisting>k__BackingField`  

```csharp
private System.Boolean <updateExisting>k__BackingField;
```

- `private System.Int32 <processVT>k__BackingField`  

```csharp
private System.Int32 <processVT>k__BackingField;
```

- `private System.Boolean <packThumbnailsAtlas>k__BackingField`  

```csharp
private System.Boolean <packThumbnailsAtlas>k__BackingField;
```

- `private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> <authorMods>k__BackingField`  

```csharp
private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> <authorMods>k__BackingField;
```

- `private Colossal.PSI.Common.IModsUploadSupport+ModTag[] <availableTags>k__BackingField`  

```csharp
private Colossal.PSI.Common.IModsUploadSupport+ModTag[] <availableTags>k__BackingField;
```

- `private Colossal.PSI.Common.IModsUploadSupport+DLCTag[] <availableDLCs>k__BackingField`  

```csharp
private Colossal.PSI.Common.IModsUploadSupport+DLCTag[] <availableDLCs>k__BackingField;
```

- `private System.Collections.Generic.HashSet<System.String> <typeTags>k__BackingField`  

```csharp
private System.Collections.Generic.HashSet<System.String> <typeTags>k__BackingField;
```

- `private System.Collections.Generic.HashSet<System.String> <tags>k__BackingField`  

```csharp
private System.Collections.Generic.HashSet<System.String> <tags>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <additionalTags>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <additionalTags>k__BackingField;
```

- `private System.Boolean <binaryPackAssets>k__BackingField`  

```csharp
private System.Boolean <binaryPackAssets>k__BackingField;
```

- `private Colossal.PSI.Common.IModsUploadSupport+SocialProfile <socialProfile>k__BackingField`  

```csharp
private Colossal.PSI.Common.IModsUploadSupport+SocialProfile <socialProfile>k__BackingField;
```

- `public System.Action onSocialProfileSynced`  

```csharp
public System.Action onSocialProfileSynced;
```


## Properties

- `public Colossal.IO.AssetDatabase.AssetData mainAsset { get; private set }`  

```csharp
public Colossal.IO.AssetDatabase.AssetData mainAsset { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> assets { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> assets { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> additionalAssets { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> additionalAssets { get; }
```

- `public System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> cachedDependencies { get }`  

```csharp
public System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> cachedDependencies { get; }
```

- `public System.Boolean hasPrefabAssets { get; private set }`  

```csharp
public System.Boolean hasPrefabAssets { get; private set; }
```

- `public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AssetData> allAssets { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AssetData> allAssets { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> screenshots { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> screenshots { get; }
```

- `public Colossal.IO.AssetDatabase.AssetData preview { get; private set }`  

```csharp
public Colossal.IO.AssetDatabase.AssetData preview { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> originalPreviews { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> originalPreviews { get; }
```

- `public Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo { get; set }`  

```csharp
public Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo { get; set; }
```

- `public System.Boolean updateExisting { get; set }`  

```csharp
public System.Boolean updateExisting { get; set; }
```

- `public System.Int32 processVT { get; set }`  

```csharp
public System.Int32 processVT { get; set; }
```

- `public System.Boolean packThumbnailsAtlas { get; set }`  

```csharp
public System.Boolean packThumbnailsAtlas { get; set; }
```

- `public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> authorMods { get; private set }`  

```csharp
public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> authorMods { get; private set; }
```

- `public Colossal.PSI.Common.IModsUploadSupport+ModTag[] availableTags { get; private set }`  

```csharp
public Colossal.PSI.Common.IModsUploadSupport+ModTag[] availableTags { get; private set; }
```

- `public Colossal.PSI.Common.IModsUploadSupport+DLCTag[] availableDLCs { get; private set }`  

```csharp
public Colossal.PSI.Common.IModsUploadSupport+DLCTag[] availableDLCs { get; private set; }
```

- `public System.Collections.Generic.HashSet<System.String> typeTags { get; private set }`  

```csharp
public System.Collections.Generic.HashSet<System.String> typeTags { get; private set; }
```

- `public System.Collections.Generic.HashSet<System.String> tags { get; private set }`  

```csharp
public System.Collections.Generic.HashSet<System.String> tags { get; private set; }
```

- `public System.Collections.Generic.List<System.String> additionalTags { get; private set }`  

```csharp
public System.Collections.Generic.List<System.String> additionalTags { get; private set; }
```

- `public System.Int32 tagCount { get }`  

```csharp
public System.Int32 tagCount { get; }
```

- `public System.Boolean binaryPackAssets { get; set }`  

```csharp
public System.Boolean binaryPackAssets { get; set; }
```

- `public Colossal.PSI.Common.IModsUploadSupport+SocialProfile socialProfile { get; private set }`  

```csharp
public Colossal.PSI.Common.IModsUploadSupport+SocialProfile socialProfile { get; private set; }
```


## Constructors

- `public PdxAssetUploadHandle()`  

```csharp
public PdxAssetUploadHandle();
```

- `public PdxAssetUploadHandle(Colossal.IO.AssetDatabase.AssetData mainAsset, Colossal.IO.AssetDatabase.AssetData[] assets)`  

```csharp
public PdxAssetUploadHandle(Colossal.IO.AssetDatabase.AssetData mainAsset, Colossal.IO.AssetDatabase.AssetData[] assets);
```


## Methods

- `internal static <ExcludeSourceTextures>g__AddReferenceTo|92_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Void`  

```csharp
internal static System.Void <ExcludeSourceTextures>g__AddReferenceTo|92_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface);
```

- `private <Initialize>b__86_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <Initialize>b__86_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public AddAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public System.Void AddAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public AddAdditionalTag(System.String tag) : System.Void`  

```csharp
public System.Void AddAdditionalTag(System.String tag);
```

- `public AddScreenshot(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public System.Void AddScreenshot(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public BeginSubmit() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> BeginSubmit();
```

- `public Cleanup() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Cleanup();
```

- `public ClearScreenshots() : System.Void`  

```csharp
public System.Void ClearScreenshots();
```

- `private CollectTags() : System.String[]`  

```csharp
private System.String[] CollectTags();
```

- `private CopyFiles(System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences) : System.ValueTuple<System.Boolean, System.String>`  

```csharp
private System.ValueTuple<System.Boolean, System.String> CopyFiles(System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences);
```

- `private CopyMetadata(Colossal.IO.AssetDatabase.AssetData asset, System.String name, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.String`  

```csharp
private System.String CopyMetadata(Colossal.IO.AssetDatabase.AssetData asset, System.String name, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed);
```

- `private CopyPreview(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.Void`  

```csharp
private System.Void CopyPreview(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed);
```

- `private CopyScreenshot(Colossal.IO.AssetDatabase.AssetData asset, System.Int32 index, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.Void`  

```csharp
private System.Void CopyScreenshot(Colossal.IO.AssetDatabase.AssetData asset, System.Int32 index, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed);
```

- `public ExcludeSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public System.Void ExcludeSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
```

- `public FinalizeSubmit() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> FinalizeSubmit();
```

- `private FindByPath(Colossal.IO.AssetDatabase.ImageAsset candidate, System.String imagePath) : System.Boolean`  

```csharp
private System.Boolean FindByPath(Colossal.IO.AssetDatabase.ImageAsset candidate, System.String imagePath);
```

- `public GetAbsoluteContentPath() : System.String`  

```csharp
public System.String GetAbsoluteContentPath();
```

- `private GetAbsoluteMetadataPath() : System.String`  

```csharp
private System.String GetAbsoluteMetadataPath();
```

- `private GetContentPath() : System.String`  

```csharp
private System.String GetContentPath();
```

- `public GetExistingInfo() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo> GetExistingInfo();
```

- `private GetFilename(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
private System.String GetFilename(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public GetLocalData(System.Int32 id) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>> GetLocalData(System.Int32 id);
```

- `private GetMetadataPath() : System.String`  

```csharp
private System.String GetMetadataPath();
```

- `private static GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> validTags) : System.ValueTuple<System.Collections.Generic.HashSet<System.String>, System.Collections.Generic.HashSet<System.String>>`  

```csharp
private static System.ValueTuple<System.Collections.Generic.HashSet<System.String>, System.Collections.Generic.HashSet<System.String>> GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> validTags);
```

- `private Initialize() : System.Void`  

```csharp
private System.Void Initialize();
```

- `private InitializeContentPrerequisite() : System.Void`  

```csharp
private System.Void InitializeContentPrerequisite();
```

- `private InitializePreviews() : System.Void`  

```csharp
private System.Void InitializePreviews();
```

- `public LoggedIn() : System.Boolean`  

```csharp
public System.Boolean LoggedIn();
```

- `private OnModsUIClosed() : System.Void`  

```csharp
private System.Void OnModsUIClosed();
```

- `private RebuildDependencyCache() : System.Void`  

```csharp
private System.Void RebuildDependencyCache();
```

- `private RefreshSocialProfile() : System.Void`  

```csharp
private System.Void RefreshSocialProfile();
```

- `public RemoveAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public System.Void RemoveAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public RemoveAdditionalTag(System.String tag) : System.Void`  

```csharp
public System.Void RemoveAdditionalTag(System.String tag);
```

- `public RemoveScreenshot(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public System.Void RemoveScreenshot(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public SetPreview(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public System.Void SetPreview(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public SetPreviewsFromExisting(Colossal.PSI.Common.IModsUploadSupport+ModLocalData localData) : System.Void`  

```csharp
public System.Void SetPreviewsFromExisting(Colossal.PSI.Common.IModsUploadSupport+ModLocalData localData);
```

- `public ShowModsUIProfilePage() : System.Void`  

```csharp
public System.Void ShowModsUIProfilePage();
```

- `public SyncPlatformData() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SyncPlatformData();
```


## Nested types

- `Game.UI.Menu.PdxAssetUploadHandle+<>c`  
- `Game.UI.Menu.PdxAssetUploadHandle+<>c__DisplayClass105_0`  
- `Game.UI.Menu.PdxAssetUploadHandle+<>c__DisplayClass105_1`  
- `Game.UI.Menu.PdxAssetUploadHandle+<>c__DisplayClass91_0`  
- `Game.UI.Menu.PdxAssetUploadHandle+<>c__DisplayClass95_0`  
- `Game.UI.Menu.PdxAssetUploadHandle+<BeginSubmit>d__87`  
- `Game.UI.Menu.PdxAssetUploadHandle+<Cleanup>d__94`  
- `Game.UI.Menu.PdxAssetUploadHandle+<FinalizeSubmit>d__88`  
- `Game.UI.Menu.PdxAssetUploadHandle+<GetExistingInfo>d__96`  
- `Game.UI.Menu.PdxAssetUploadHandle+<GetLocalData>d__97`  
- `Game.UI.Menu.PdxAssetUploadHandle+<RefreshSocialProfile>d__91`  
- `Game.UI.Menu.PdxAssetUploadHandle+<SyncPlatformData>d__95`  
- `Game.UI.Menu.PdxAssetUploadHandle+<get_allAssets>d__23`  


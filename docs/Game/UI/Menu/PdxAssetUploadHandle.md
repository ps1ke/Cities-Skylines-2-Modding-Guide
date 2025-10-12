# Game.UI.Menu.PdxAssetUploadHandle

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.Logging.ILog log`  
- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Screenshots`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_Assets`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_OriginalPreviews`  
- `private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.AssetData> m_WIPAssets`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AdditionalAssets`  
- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_CachedAssetDependencies`  
- `private Colossal.IO.AssetDatabase.AssetData <mainAsset>k__BackingField`  
- `private System.Boolean <hasPrefabAssets>k__BackingField`  
- `private Colossal.IO.AssetDatabase.AssetData <preview>k__BackingField`  
- `private Colossal.PSI.Common.IModsUploadSupport+ModInfo <modInfo>k__BackingField`  
- `private System.Boolean <updateExisting>k__BackingField`  
- `private System.Int32 <processVT>k__BackingField`  
- `private System.Boolean <packThumbnailsAtlas>k__BackingField`  
- `private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> <authorMods>k__BackingField`  
- `private Colossal.PSI.Common.IModsUploadSupport+ModTag[] <availableTags>k__BackingField`  
- `private Colossal.PSI.Common.IModsUploadSupport+DLCTag[] <availableDLCs>k__BackingField`  
- `private System.Collections.Generic.HashSet<System.String> <typeTags>k__BackingField`  
- `private System.Collections.Generic.HashSet<System.String> <tags>k__BackingField`  
- `private System.Collections.Generic.List<System.String> <additionalTags>k__BackingField`  
- `private System.Boolean <binaryPackAssets>k__BackingField`  
- `private Colossal.PSI.Common.IModsUploadSupport+SocialProfile <socialProfile>k__BackingField`  
- `public System.Action onSocialProfileSynced`  

## Properties

- `public Colossal.IO.AssetDatabase.AssetData mainAsset { get; private set }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> assets { get }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> additionalAssets { get }`  
- `public System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> cachedDependencies { get }`  
- `public System.Boolean hasPrefabAssets { get; private set }`  
- `public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AssetData> allAssets { get }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> screenshots { get }`  
- `public Colossal.IO.AssetDatabase.AssetData preview { get; private set }`  
- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AssetData> originalPreviews { get }`  
- `public Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo { get; set }`  
- `public System.Boolean updateExisting { get; set }`  
- `public System.Int32 processVT { get; set }`  
- `public System.Boolean packThumbnailsAtlas { get; set }`  
- `public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo> authorMods { get; private set }`  
- `public Colossal.PSI.Common.IModsUploadSupport+ModTag[] availableTags { get; private set }`  
- `public Colossal.PSI.Common.IModsUploadSupport+DLCTag[] availableDLCs { get; private set }`  
- `public System.Collections.Generic.HashSet<System.String> typeTags { get; private set }`  
- `public System.Collections.Generic.HashSet<System.String> tags { get; private set }`  
- `public System.Collections.Generic.List<System.String> additionalTags { get; private set }`  
- `public System.Int32 tagCount { get }`  
- `public System.Boolean binaryPackAssets { get; set }`  
- `public Colossal.PSI.Common.IModsUploadSupport+SocialProfile socialProfile { get; private set }`  

## Constructors

- `public PdxAssetUploadHandle()`  
- `public PdxAssetUploadHandle(Colossal.IO.AssetDatabase.AssetData mainAsset, Colossal.IO.AssetDatabase.AssetData[] assets)`  

## Methods

- `internal static <ExcludeSourceTextures>g__AddReferenceTo|92_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Void`  
- `private <Initialize>b__86_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `public AddAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  
- `public AddAdditionalTag(System.String tag) : System.Void`  
- `public AddScreenshot(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  
- `public BeginSubmit() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  
- `public Cleanup() : System.Threading.Tasks.Task`  
- `public ClearScreenshots() : System.Void`  
- `private CollectTags() : System.String[]`  
- `private CopyFiles(System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences) : System.ValueTuple<System.Boolean, System.String>`  
- `private CopyMetadata(Colossal.IO.AssetDatabase.AssetData asset, System.String name, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.String`  
- `private CopyPreview(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.Void`  
- `private CopyScreenshot(Colossal.IO.AssetDatabase.AssetData asset, System.Int32 index, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.Void`  
- `public ExcludeSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  
- `public FinalizeSubmit() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  
- `private FindByPath(Colossal.IO.AssetDatabase.ImageAsset candidate, System.String imagePath) : System.Boolean`  
- `public GetAbsoluteContentPath() : System.String`  
- `private GetAbsoluteMetadataPath() : System.String`  
- `private GetContentPath() : System.String`  
- `public GetExistingInfo() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo>`  
- `private GetFilename(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  
- `public GetLocalData(System.Int32 id) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>>`  
- `private GetMetadataPath() : System.String`  
- `private static GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> validTags) : System.ValueTuple<System.Collections.Generic.HashSet<System.String>, System.Collections.Generic.HashSet<System.String>>`  
- `private Initialize() : System.Void`  
- `private InitializeContentPrerequisite() : System.Void`  
- `private InitializePreviews() : System.Void`  
- `public LoggedIn() : System.Boolean`  
- `private OnModsUIClosed() : System.Void`  
- `private RebuildDependencyCache() : System.Void`  
- `private RefreshSocialProfile() : System.Void`  
- `public RemoveAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  
- `public RemoveAdditionalTag(System.String tag) : System.Void`  
- `public RemoveScreenshot(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  
- `public SetPreview(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  
- `public SetPreviewsFromExisting(Colossal.PSI.Common.IModsUploadSupport+ModLocalData localData) : System.Void`  
- `public ShowModsUIProfilePage() : System.Void`  
- `public SyncPlatformData() : System.Threading.Tasks.Task`  

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


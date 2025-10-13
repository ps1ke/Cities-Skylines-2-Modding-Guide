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
public PdxAssetUploadHandle(AssetData mainAsset, params AssetData[] assets)
	{
		this.mainAsset = mainAsset;
		if (mainAsset != null)
		{
			m_Assets.Add(mainAsset);
		}
		m_Assets.AddRange(assets);
		Initialize();
	}
```

- `public PdxAssetUploadHandle(Colossal.IO.AssetDatabase.AssetData mainAsset, Colossal.IO.AssetDatabase.AssetData[] assets)`  

```csharp
public PdxAssetUploadHandle(AssetData mainAsset, params AssetData[] assets)
	{
		this.mainAsset = mainAsset;
		if (mainAsset != null)
		{
			m_Assets.Add(mainAsset);
		}
		m_Assets.AddRange(assets);
		Initialize();
	}
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
public void AddAdditionalAsset(AssetData asset)
	{
		m_AdditionalAssets.Add(asset);
		RebuildDependencyCache();
	}
```

- `public AddAdditionalTag(System.String tag) : System.Void`  

```csharp
public void AddAdditionalTag(string tag)
	{
		additionalTags.Add(tag);
	}
```

- `public AddScreenshot(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public void AddScreenshot(AssetData asset)
	{
		m_Screenshots.Add(asset);
	}
```

- `public BeginSubmit() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public async Task<IModsUploadSupport.ModOperationResult> BeginSubmit()
	{
		IModsUploadSupport.ModOperationResult modOperationResult = ((!updateExisting) ? (await m_Manager.RegisterWIP(this.modInfo)) : (await m_Manager.RegisterExistingWIP(this.modInfo)));
		IModsUploadSupport.ModOperationResult result = modOperationResult;
		this.modInfo = result.m_ModInfo;
		if (!result.m_Success)
		{
			return result;
		}
		HashSet<IModsUploadSupport.ModInfo.ModDependency> hashSet = new HashSet<IModsUploadSupport.ModInfo.ModDependency>();
		var (flag, error) = CopyFiles(hashSet);
		if (!flag)
		{
			log.Error(error);
			await Cleanup();
			return new IModsUploadSupport.ModOperationResult
			{
				m_ModInfo = this.modInfo,
				m_Success = false,
				m_Error = new IModsUploadSupport.ModError
				{
					m_Details = error
				}
			};
		}
		IModsUploadSupport.ModInfo modInfo = this.modInfo;
		modInfo.m_ModDependencies = hashSet.ToArray();
		modInfo.m_Tags = CollectTags();
		this.modInfo = modInfo;
		IModsUploadSupport.ModOperationResult updateResult = await m_Manager.UpdateWIP(this.modInfo);
		this.modInfo = updateResult.m_ModInfo;
		if (!updateResult.m_Success)
		{
			await Cleanup();
		}
		return updateResult;
	}
```

- `public Cleanup() : System.Threading.Tasks.Task`  

```csharp
public async Task Cleanup()
	{
		foreach (KeyValuePair<AssetData, AssetData> wIPAsset in m_WIPAssets)
		{
			AssetDatabase<ParadoxMods>.instance.DeleteAsset(wIPAsset.Value);
		}
		m_WIPAssets.Clear();
		modInfo = (await m_Manager.UnregisterWIP(modInfo)).m_ModInfo;
	}
```

- `public ClearScreenshots() : System.Void`  

```csharp
public void ClearScreenshots()
	{
		m_Screenshots.Clear();
	}
```

- `private CollectTags() : System.String[]`  

```csharp
private string[] CollectTags()
	{
		HashSet<string> hashSet = new HashSet<string>(tags);
		foreach (string additionalTag in additionalTags)
		{
			hashSet.Add(additionalTag);
		}
		return hashSet.ToArray();
	}
```

- `private CopyFiles(System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences) : System.ValueTuple<System.Boolean, System.String>`  

```csharp
private System.ValueTuple<System.Boolean, System.String> CopyFiles(System.Collections.Generic.HashSet<Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency> externalReferences);
```

- `private CopyMetadata(Colossal.IO.AssetDatabase.AssetData asset, System.String name, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.String`  

```csharp
private string CopyMetadata(AssetData asset, string name, Dictionary<AssetData, string> processed)
	{
		if (processed.TryGetValue(asset, out var value))
		{
			return value;
		}
		using (ILocalAssetDatabase database = AssetDatabase.GetTransient(0L))
		{
			try
			{
				AssetData assetData = AssetUploadUtils.CopyPreviewImage(asset, database, name);
				value = GetFilename(assetData);
				using FileStream destination = LongFile.Create(GetAbsoluteMetadataPath() + "/" + value);
				using Stream stream = assetData.GetReadStream();
				stream.CopyTo(destination);
			}
			catch (Exception exception)
			{
				log.Error(exception);
				return null;
			}
		}
		processed[asset] = value;
		return value;
	}
```

- `private CopyPreview(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.Void`  

```csharp
private void CopyPreview(Dictionary<AssetData, string> processed)
	{
		if (!(preview == null))
		{
			string text = CopyMetadata(preview, "preview", processed);
			if (text != null)
			{
				IModsUploadSupport.ModInfo modInfo = this.modInfo;
				modInfo.m_ThumbnailFilename = text;
				this.modInfo = modInfo;
			}
		}
	}
```

- `private CopyScreenshot(Colossal.IO.AssetDatabase.AssetData asset, System.Int32 index, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AssetData, System.String> processed) : System.Void`  

```csharp
private void CopyScreenshot(AssetData asset, int index, Dictionary<AssetData, string> processed)
	{
		string text = CopyMetadata(asset, $"screenshot{index}", processed);
		if (text != null)
		{
			IModsUploadSupport.ModInfo modInfo = this.modInfo;
			if (!modInfo.m_ScreenshotFileNames.Contains(text))
			{
				modInfo.m_ScreenshotFileNames.Add(text);
			}
			this.modInfo = modInfo;
		}
	}
```

- `public ExcludeSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public void ExcludeSourceTextures(IEnumerable<SurfaceAsset> surfaces, ILocalAssetDatabase database)
	{
		Dictionary<TextureAsset, List<SurfaceAsset>> dictionary = new Dictionary<TextureAsset, List<SurfaceAsset>>();
		Dictionary<TextureAsset, List<SurfaceAsset>> dictionary2 = new Dictionary<TextureAsset, List<SurfaceAsset>>();
		foreach (SurfaceAsset surface in surfaces)
		{
			surface.LoadProperties(useVT: true);
			if (surface.isVTMaterial)
			{
				foreach (KeyValuePair<string, TextureAsset> texture in surface.textures)
				{
					if (surface.IsHandledByVirtualTexturing(texture))
					{
						AddReferenceTo(dictionary, texture.Value, surface);
					}
					else
					{
						AddReferenceTo(dictionary2, texture.Value, surface);
					}
				}
			}
			else
			{
				foreach (KeyValuePair<string, TextureAsset> texture2 in surface.textures)
				{
					AddReferenceTo(dictionary2, texture2.Value, surface);
				}
			}
			surface.Unload();
		}
		List<TextureAsset> list = database.GetAssets(default(SearchFilter<TextureAsset>)).ToList();
		for (int i = 0; i < list.Count; i++)
		{
			TextureAsset textureAsset = list[i];
			if (dictionary.ContainsKey(textureAsset))
			{
				if (dictionary2.ContainsKey(textureAsset))
				{
					log.WarnFormat("Texture {0} is referenced {1} times by VT materials and {2} times by non VT materials. It will be duplicated on disk.", textureAsset, dictionary[textureAsset].Count, dictionary2[textureAsset].Count);
					log.InfoFormat("Detail for {0}:\nvt: {1}\nnon vt: {2}", textureAsset, string.Join(", ", dictionary[textureAsset]), string.Join(", ", dictionary2[textureAsset]));
				}
				else
				{
					log.InfoFormat($"Deleting {textureAsset}");
					textureAsset.Delete();
				}
			}
		}
		static void AddReferenceTo(Dictionary<TextureAsset, List<SurfaceAsset>> references, TextureAsset texture, SurfaceAsset surface)
		{
			if (!references.TryGetValue(texture, out var value))
			{
				value = new List<SurfaceAsset>();
				references.Add(texture, value);
			}
			value.Add(surface);
		}
	}
```

- `public FinalizeSubmit() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public async Task<IModsUploadSupport.ModOperationResult> FinalizeSubmit()
	{
		IModsUploadSupport.ModOperationResult modOperationResult = ((!updateExisting) ? (await m_Manager.PublishWIP(modInfo)) : (await m_Manager.UpdateExisting(modInfo)));
		IModsUploadSupport.ModOperationResult publishResult = modOperationResult;
		modInfo = publishResult.m_ModInfo;
		await Cleanup();
		return publishResult;
	}
```

- `private FindByPath(Colossal.IO.AssetDatabase.ImageAsset candidate, System.String imagePath) : System.Boolean`  

```csharp
private bool FindByPath(ImageAsset candidate, string imagePath)
	{
		string fullPath = Path.GetFullPath(candidate.GetMeta().path);
		return imagePath.Equals(fullPath, StringComparison.OrdinalIgnoreCase);
	}
```

- `public GetAbsoluteContentPath() : System.String`  

```csharp
public string GetAbsoluteContentPath()
	{
		return Path.Combine(m_Manager.modsRootPath, GetContentPath());
	}
```

- `private GetAbsoluteMetadataPath() : System.String`  

```csharp
private string GetAbsoluteMetadataPath()
	{
		return Path.Combine(m_Manager.modsRootPath, GetMetadataPath());
	}
```

- `private GetContentPath() : System.String`  

```csharp
private string GetContentPath()
	{
		return modInfo.m_RootPath + "/" + IModsUploadSupport.ModInfo.kContentDirectory;
	}
```

- `public GetExistingInfo() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo>`  

```csharp
public async Task<IModsUploadSupport.ModInfo> GetExistingInfo()
	{
		return await m_Manager.GetDetails(modInfo);
	}
```

- `private GetFilename(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
private string GetFilename(AssetData asset)
	{
		SourceMeta meta = asset.GetMeta();
		return meta.fileName + meta.extension;
	}
```

- `public GetLocalData(System.Int32 id) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>> GetLocalData(System.Int32 id);
```

- `private GetMetadataPath() : System.String`  

```csharp
private string GetMetadataPath()
	{
		return modInfo.m_RootPath + "/" + IModsUploadSupport.ModInfo.kMetadataDirectory;
	}
```

- `private static GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> validTags) : System.ValueTuple<System.Collections.Generic.HashSet<System.String>, System.Collections.Generic.HashSet<System.String>>`  

```csharp
private static System.ValueTuple<System.Collections.Generic.HashSet<System.String>, System.Collections.Generic.HashSet<System.String>> GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> validTags);
```

- `private Initialize() : System.Void`  

```csharp
private void Initialize()
	{
		m_Manager = PlatformManager.instance.GetPSI<PdxSdkPlatform>("PdxSdk");
		PlatformManager.instance.onPlatformRegistered += delegate(IPlatformServiceIntegration psi)
		{
			if (psi is PdxSdkPlatform manager)
			{
				m_Manager = manager;
			}
		};
		InitializePreviews();
		IModsUploadSupport.ModInfo modInfo = this.modInfo;
		modInfo.Clear();
		modInfo.m_RecommendedGameVersion = $"{Version.current.majorVersion}.{Version.current.minorVersion}.*";
		modInfo.m_DisplayName = mainAsset?.name;
		modInfo.m_ExternalLinks.Add(new IModsUploadSupport.ExternalLinkData
		{
			m_Type = IModsUploadSupport.ExternalLinkInfo.kAcceptedTypes[0].m_Type,
			m_URL = string.Empty
		});
		this.modInfo = modInfo;
		RebuildDependencyCache();
	}
```

- `private InitializeContentPrerequisite() : System.Void`  

```csharp
private void InitializeContentPrerequisite()
	{
		HashSet<string> hashSet = new HashSet<string>();
		foreach (AssetData asset in assets)
		{
			if (asset is MapMetadata mapMetadata && mapMetadata.target.contentPrerequisites != null)
			{
				string[] contentPrerequisites = mapMetadata.target.contentPrerequisites;
				foreach (string item in contentPrerequisites)
				{
					hashSet.Add(item);
				}
			}
			if (asset is SaveGameMetadata saveGameMetadata && saveGameMetadata.target.contentPrerequisites != null)
			{
				string[] contentPrerequisites = saveGameMetadata.target.contentPrerequisites;
				foreach (string item2 in contentPrerequisites)
				{
					hashSet.Add(item2);
				}
			}
		}
		IModsUploadSupport.ModInfo modInfo = this.modInfo;
		modInfo.m_DLCDependencies = hashSet.ToArray();
		this.modInfo = modInfo;
	}
```

- `private InitializePreviews() : System.Void`  

```csharp
private void InitializePreviews()
	{
		if (AssetUploadUtils.TryGetPreview(mainAsset, out var result))
		{
			preview = result;
		}
		else
		{
			preview = MenuHelpers.defaultPreview;
		}
		HashSet<AssetData> hashSet = new HashSet<AssetData>();
		foreach (AssetData asset in assets)
		{
			if (AssetUploadUtils.TryGetPreview(asset, out var result2))
			{
				hashSet.Add(result2);
			}
		}
		m_OriginalPreviews.AddRange(hashSet);
		m_Screenshots.AddRange(hashSet);
	}
```

- `public LoggedIn() : System.Boolean`  

```csharp
public bool LoggedIn()
	{
		return m_Manager?.cachedLoggedIn ?? false;
	}
```

- `private OnModsUIClosed() : System.Void`  

```csharp
private void OnModsUIClosed()
	{
		m_Manager.onModsUIClosed -= OnModsUIClosed;
		RefreshSocialProfile();
	}
```

- `private RebuildDependencyCache() : System.Void`  

```csharp
private void RebuildDependencyCache()
	{
		m_CachedAssetDependencies.Clear();
		hasPrefabAssets = false;
		foreach (AssetData allAsset in allAssets)
		{
			if (allAsset is PrefabAsset prefabAsset)
			{
				AssetUploadUtils.CollectPrefabAssetDependencies(prefabAsset, m_CachedAssetDependencies, allAsset == mainAsset);
				hasPrefabAssets = true;
			}
			m_CachedAssetDependencies.Add(allAsset);
		}
		InitializeContentPrerequisite();
	}
```

- `private RefreshSocialProfile() : System.Void`  

```csharp
private async void RefreshSocialProfile()
	{
		IModsUploadSupport.SocialProfile socialProfileResult = await m_Manager.GetSocialProfile();
		GameManager.instance.RunOnMainThread(delegate
		{
			socialProfile = socialProfileResult;
			onSocialProfileSynced?.Invoke();
		});
	}
```

- `public RemoveAdditionalAsset(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public void RemoveAdditionalAsset(AssetData asset)
	{
		m_AdditionalAssets.Remove(asset);
		RebuildDependencyCache();
	}
```

- `public RemoveAdditionalTag(System.String tag) : System.Void`  

```csharp
public void RemoveAdditionalTag(string tag)
	{
		additionalTags.Remove(tag);
	}
```

- `public RemoveScreenshot(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public void RemoveScreenshot(AssetData asset)
	{
		m_Screenshots.Remove(asset);
	}
```

- `public SetPreview(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
public void SetPreview(AssetData asset)
	{
		preview = asset;
	}
```

- `public SetPreviewsFromExisting(Colossal.PSI.Common.IModsUploadSupport+ModLocalData localData) : System.Void`  

```csharp
public void SetPreviewsFromExisting(IModsUploadSupport.ModLocalData localData)
	{
		if (localData.m_ThumbnailFilename != null)
		{
			string thumbnailPath = Path.GetFullPath(Path.Combine(localData.m_AbsolutePath, localData.m_ThumbnailFilename));
			if (AssetDatabase<ParadoxMods>.instance.TryGetAsset(SearchFilter<ImageAsset>.ByCondition((ImageAsset candidate) => FindByPath(candidate, thumbnailPath)), out var asset))
			{
				SetPreview(asset);
			}
		}
		if (localData.m_ScreenshotFilenames == null)
		{
			return;
		}
		ClearScreenshots();
		string[] screenshotFilenames = localData.m_ScreenshotFilenames;
		foreach (string path in screenshotFilenames)
		{
			string screenshotPath = Path.GetFullPath(Path.Combine(localData.m_AbsolutePath, path));
			if (AssetDatabase<ParadoxMods>.instance.TryGetAsset(SearchFilter<ImageAsset>.ByCondition((ImageAsset candidate) => FindByPath(candidate, screenshotPath)), out var asset2))
			{
				AddScreenshot(asset2);
			}
		}
	}
```

- `public ShowModsUIProfilePage() : System.Void`  

```csharp
public void ShowModsUIProfilePage()
	{
		m_Manager.onModsUIClosed += OnModsUIClosed;
		m_Manager.ShowModsUIProfilePage();
	}
```

- `public SyncPlatformData() : System.Threading.Tasks.Task`  

```csharp
public async Task SyncPlatformData()
	{
		Task<List<IModsUploadSupport.ModInfo>> modsTask = m_Manager.ListAllModsByMe(typeTags.ToArray());
		Task<(IModsUploadSupport.ModTag[], IModsUploadSupport.DLCTag[])> tagsTask = m_Manager.GetTags();
		Task<IModsUploadSupport.SocialProfile> socialProfileTask = m_Manager.GetSocialProfile();
		await Task.WhenAll(modsTask, tagsTask, socialProfileTask);
		GameManager.instance.RunOnMainThread(delegate
		{
			authorMods = modsTask.Result;
			authorMods?.Sort((IModsUploadSupport.ModInfo a, IModsUploadSupport.ModInfo b) => string.Compare(a.m_DisplayName, b.m_DisplayName, StringComparison.OrdinalIgnoreCase));
			availableTags = tagsTask.Result.Item1;
			availableDLCs = tagsTask.Result.Item2;
			socialProfile = socialProfileTask.Result;
			HashSet<string> validTags = new HashSet<string>(availableTags.Select((IModsUploadSupport.ModTag tag) => tag.m_Id));
			(HashSet<string>, HashSet<string>) tuple = GetTags(mainAsset, validTags);
			(tags, _) = tuple;
			HashSet<string> hashSet = (typeTags = tuple.Item2);
		});
	}
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


# Game.AssetPipeline.AssetImportPipeline

**Assembly:** `Game`  
**Namespace:** `Game.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AssetImportPipeline
{
    private static readonly Colossal.Logging.ILog log;
    public static System.Boolean useParallelImport;
    public static Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase;
    private static readonly Unity.Profiling.ProfilerMarker s_ImportPath;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfPostImport;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImportModels;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImportTextures;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateGeomsSurfaces;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImportAssetGroup;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfImportDidimo;
    private static readonly Game.AssetPipeline.AssetImportPipeline+Progress s_Progress;
    private static Colossal.AssetPipeline.MainThreadDispatcher s_MainThreadDispatcher;
    public static System.Action<System.String, UnityEngine.Texture> OnDebugTexture;
    private static UnityEngine.Material s_BackgroundMaterial;
    private static const System.String kMainSettings;
    private static const System.Single kBoundSize;
    private static const System.Single kHalfBoundSize;

    public static UnityEngine.Material backgroundMaterial { get; }

    internal static System.String <GetSettings>g__GetIfThen|54_0(Colossal.AssetPipeline.Importers.ISettings settings);
    internal static System.Void <HideVTSourceTextures>g__AddReferenceTo|82_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface);
    internal static System.String <InstantiateRenderPrefabs>g__GetParent|74_0<T>(System.String path);
    private static System.Void AddSimplifiedProperties(Colossal.Json.Variant schema);
    private static System.Void AddSupportedThemes(System.String projectRootPath);
    private static System.String AdjustNamingConvention(System.String input);
    private static System.Void AdjustXBounds(UnityEngine.Transform parent, System.Single x);
    private static System.Void AdjustZBounds(UnityEngine.Transform parent, System.Single z);
    public static System.Threading.Tasks.Task ApplyVTMipBias(Colossal.IO.AssetDatabase.IAssetDatabase database, System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipCount, System.String folder);
    public static System.Void BuildMidMipsCache(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    private static TTo CastStruct<TFrom, TTo>(TFrom s);
    public static System.Collections.Generic.IDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>, Colossal.AssetPipeline.Settings> CollectDataToImport(System.String projectRootPath, System.String[] assetPaths, Colossal.AssetPipeline.Diagnostic.Report report);
    public static System.Void ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    public static System.Void ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean writeVTSettings, System.Int32 tileSize, System.Int32 midMipsCount, System.Int32 mipBias, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    private static Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> CreateAssetGroupFromSettings(System.String projectRootPath, Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport);
    private static System.Void CreateBackground(UnityEngine.Transform parent, System.String name, UnityEngine.Vector3 position, UnityEngine.Vector3 size);
    private static System.Void CreateBounds(UnityEngine.Transform parent);
    private static System.Void CreateDidimoAssets(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    private static System.Void CreateGeometriesAndSurfaces(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    private static T CreatePrefab<T>(System.String suffix, System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory);
    private static System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> CreateRenderPrefab(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> asset, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory);
    private static Game.Prefabs.RenderPrefab CreateRenderPrefab(System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory);
    private static System.Void CreateRenderPrefabs(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory);
    private static Game.Prefabs.CharacterStyle CreateStylePrefab(System.ValueTuple<System.String, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Colossal.Animations.Animation, Colossal.Animations.BoneHierarchy, System.String, System.Int32, Colossal.Hash128>>, System.Int32, System.Int32> style, System.String sourcePath, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.AnimationAsset> overrideSafeGuard, System.Collections.Generic.List<Game.Prefabs.RenderPrefab> prefabs, Game.AssetPipeline.IPrefabFactory prefabFactory);
    private static System.Void CreateTitle(UnityEngine.Transform parent, System.String text, UnityEngine.Vector3 textPosOffset, UnityEngine.Color bgColor, UnityEngine.Color txtColor, System.Int32 txtSize, System.Single txtPadding);
    private static System.Void DisposeLODs(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD>> assets);
    private static System.Void DisposeLODs(System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> assets);
    private static System.Threading.Tasks.Task ExecuteMainThreadQueue(System.Threading.Tasks.Task importTask, Colossal.AssetPipeline.Diagnostic.Report report);
    private static Unity.Collections.NativeArray<System.Byte> FromManagedArray<T>(T[] array);
    private static Unity.Collections.NativeArray<System.Byte> FromManagedArray<T>(T[] array, System.Int32 offset, System.Int32 elementSize, System.Int32 countPerElement);
    public static System.Void GenerateJSONSchema();
    private static Colossal.Json.Variant GetDefinitions();
    public static System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ISettingable> GetImportChainFor(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private static System.String GetNameWithoutGUID(System.String str);
    private static System.String GetSettings();
    private static System.Boolean GetSkinningInfo(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]& bones, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
    public static System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> GetTextureReferenceCount(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32& surfaceCount);
    private static System.String GetUniqueString(System.String input, System.Int32 currentIndex, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] array);
    public static System.Void HideVTSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces);
    private static System.Boolean ImportAssetGroup(System.String projectRootPath, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.Collections.Generic.List`1[[System.Collections.Generic.List`1[[Colossal.AssetPipeline.LOD, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& lods, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, Colossal.AssetPipeline.Diagnostic.Report report, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport);
    private static System.Void ImportDidimo(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    private static System.Void ImportModels(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    public static System.Threading.Tasks.Task ImportPath(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths, Colossal.AssetPipeline.ImportMode importMode, System.Boolean convertToVT, System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback, Game.AssetPipeline.IPrefabFactory prefabFactory);
    private static Colossal.AssetPipeline.Settings ImportSettings(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    private static System.Void ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    private static System.Void ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<Colossal.AssetPipeline.TextureAsset, System.Boolean> predicate, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
    public static System.Void InstantiateRenderPrefabs<T>(System.Collections.Generic.IEnumerable<System.ValueTuple<T, System.String>> prefabs, System.Boolean smartInstantiate, System.Boolean ignoreLODs);
    private static System.Boolean IsArtRootPath(System.String rootPathName, System.String path, System.String& artProjectPath, System.String& artProjectRelativePath);
    public static System.Boolean IsArtRootPath(System.String rootPathName, System.String[] paths, System.String& artProjectPath, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& artProjectRelativePaths);
    private static System.Boolean IsLODsValid(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets);
    private static System.String MakeRelativePath(System.String path, System.String rootPath);
    public static System.Void ProcessSurfacesForVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    private static System.Void ReportTextureReferenceStats(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    private static System.Void ResaveCache(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
    private static System.String ResolveRelativePath(System.String projectRootPath, System.String target, System.String to);
    public static System.Void SetReportCallback(System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback);
    private static System.Void SetupComponents(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
    private static System.Void SetupEmissiveComponent(Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod);
    private static System.Void SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
    private static System.Void SetupLODs(Colossal.AssetPipeline.Settings settings, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> meshPrefabs);
    private static System.Void SetupProceduralAnimationComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
    private static System.Int32 TestTextureSizesUniformity(Colossal.IO.AssetDatabase.SurfaceAsset asset, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription description);
    private static Colossal.Json.Variant ToJsonSchema(System.Object obj);
    private static Colossal.Json.Variant ToJsonSchema(System.Type type, Colossal.Json.Variant previous);
    private static System.String ToJsonSchema(System.Reflection.FieldInfo fieldInfo);
    private static System.String ToJsonType(System.Type type, System.Boolean nullable);
}
```


## Fields

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```

- `public static System.Boolean useParallelImport`  

```csharp
public static System.Boolean useParallelImport;
```

- `public static Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase`  

```csharp
public static Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ImportPath`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ImportPath;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfPostImport`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfPostImport;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportModels`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImportModels;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportTextures`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImportTextures;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateGeomsSurfaces`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateGeomsSurfaces;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportAssetGroup`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImportAssetGroup;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportDidimo`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfImportDidimo;
```

- `private static readonly Game.AssetPipeline.AssetImportPipeline+Progress s_Progress`  

```csharp
private static readonly Game.AssetPipeline.AssetImportPipeline+Progress s_Progress;
```

- `private static Colossal.AssetPipeline.MainThreadDispatcher s_MainThreadDispatcher`  

```csharp
private static Colossal.AssetPipeline.MainThreadDispatcher s_MainThreadDispatcher;
```

- `public static System.Action<System.String, UnityEngine.Texture> OnDebugTexture`  

```csharp
public static System.Action<System.String, UnityEngine.Texture> OnDebugTexture;
```

- `private static UnityEngine.Material s_BackgroundMaterial`  

```csharp
private static UnityEngine.Material s_BackgroundMaterial;
```

- `private static const System.String kMainSettings`  

```csharp
private static const System.String kMainSettings;
```

- `private static const System.Single kBoundSize`  

```csharp
private static const System.Single kBoundSize;
```

- `private static const System.Single kHalfBoundSize`  

```csharp
private static const System.Single kHalfBoundSize;
```


## Properties

- `public static UnityEngine.Material backgroundMaterial { get }`  

```csharp
public static UnityEngine.Material backgroundMaterial { get; }
```


## Methods

- `internal static <GetSettings>g__GetIfThen|54_0(Colossal.AssetPipeline.Importers.ISettings settings) : System.String`  

```csharp
internal static System.String <GetSettings>g__GetIfThen|54_0(Colossal.AssetPipeline.Importers.ISettings settings);
```

- `internal static <HideVTSourceTextures>g__AddReferenceTo|82_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Void`  

```csharp
internal static System.Void <HideVTSourceTextures>g__AddReferenceTo|82_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface);
```

- `internal static <InstantiateRenderPrefabs>g__GetParent|74_0<T>(System.String path) : System.String`  

```csharp
internal static System.String <InstantiateRenderPrefabs>g__GetParent|74_0<T>(System.String path);
```

- `private static AddSimplifiedProperties(Colossal.Json.Variant schema) : System.Void`  

```csharp
private static void AddSimplifiedProperties(Variant schema)
	{
		schema["^LOD(\\d+|\\*)?(_[A-Za-z0-9*]+)?$"] = ToJsonSchema(typeof(LODPostProcessor.PostProcessSettings.LODLevelSettings));
		schema["^Surface(_[A-Za-z0-9*]+)?$"] = ToJsonSchema(typeof(SurfacePostProcessor.PostProcessSettings));
	}
```

- `private static AddSupportedThemes(System.String projectRootPath) : System.Void`  

```csharp
private static void AddSupportedThemes(string projectRootPath)
	{
		string path = projectRootPath + "/themes.json";
		if (!LongFile.Exists(path))
		{
			return;
		}
		Variant variant = JSON.Load(LongFile.ReadAllText(path).Trim());
		if (variant != null)
		{
			ThemesConfig themesConfig = JSON.MakeInto<ThemesConfig>(variant);
			if (themesConfig.themePrefixes != null)
			{
				AssetUtils.AddSupportedThemes(themesConfig.themePrefixes);
				log.InfoFormat("Theme prefixes added: {0}", string.Join(',', themesConfig.themePrefixes));
			}
		}
	}
```

- `private static AdjustNamingConvention(System.String input) : System.String`  

```csharp
private static string AdjustNamingConvention(string input)
	{
		StringBuilder stringBuilder = new StringBuilder();
		bool flag = true;
		foreach (char c in input)
		{
			if (flag)
			{
				stringBuilder.Append(char.ToUpper(c));
				flag = false;
			}
			else
			{
				stringBuilder.Append(c);
			}
			if (c == '_')
			{
				flag = true;
			}
		}
		return stringBuilder.ToString();
	}
```

- `private static AdjustXBounds(UnityEngine.Transform parent, System.Single x) : System.Void`  

```csharp
private static void AdjustXBounds(Transform parent, float x)
	{
		Transform transform = parent.Find("Title");
		Transform transform2 = transform.Find("BoundsTop");
		Transform transform3 = transform.Find("BoundsBottom");
		Transform transform4 = transform.Find("BoundsRight");
		Vector3 localPosition = transform.Find("BoundsLeft").transform.localPosition;
		Vector3 localPosition2 = localPosition;
		localPosition2.x += x;
		transform4.transform.localPosition = localPosition2;
		float x2 = (localPosition.x + localPosition2.x) * 0.5f;
		Vector3 localPosition3 = transform2.localPosition;
		localPosition3.x = x2;
		transform2.localPosition = localPosition3;
		Vector3 localPosition4 = transform3.localPosition;
		localPosition4.x = x2;
		transform3.localPosition = localPosition4;
		float x3 = (localPosition2.x - localPosition.x) / 10f + 0.1f;
		Vector3 localScale = transform2.localScale;
		localScale.x = x3;
		transform2.localScale = localScale;
		Vector3 localScale2 = transform3.localScale;
		localScale2.x = x3;
		transform3.localScale = localScale2;
	}
```

- `private static AdjustZBounds(UnityEngine.Transform parent, System.Single z) : System.Void`  

```csharp
private static void AdjustZBounds(Transform parent, float z)
	{
		Transform transform = parent.Find("Title");
		Transform transform2 = transform.Find("BoundsTop");
		Transform transform3 = transform.Find("BoundsBottom");
		Transform transform4 = transform.Find("BoundsRight");
		Transform transform5 = transform.Find("BoundsLeft");
		Vector3 localPosition = transform2.localPosition;
		localPosition.y = z;
		transform2.localPosition = localPosition;
		Vector3 localPosition2 = transform3.localPosition;
		localPosition2.y = 0f - z;
		transform3.localPosition = localPosition2;
		Vector3 localScale = transform5.localScale;
		localScale.z = z * 2f / 10f;
		transform5.localScale = localScale;
		Vector3 localScale2 = transform4.localScale;
		localScale2.z = z * 2f / 10f;
		transform4.localScale = localScale2;
	}
```

- `public static ApplyVTMipBias(Colossal.IO.AssetDatabase.IAssetDatabase database, System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipCount, System.String folder) : System.Threading.Tasks.Task`  

```csharp
public static async Task ApplyVTMipBias(IAssetDatabase database, int mipBias, int tileSize, int midMipCount, string folder)
	{
		if (s_MainThreadDispatcher == null)
		{
			s_MainThreadDispatcher = new MainThreadDispatcher();
		}
		if (mipBias < 0)
		{
			throw new Exception("Mip bias cannot be smaller than zero in that context!");
		}
		bool flag = true;
		string text = null;
		if (database is ILocalAssetDatabase { dataSource: FileSystemDataSource dataSource })
		{
			text = dataSource.rootPath + "/StreamingData~";
			if (database != AssetDatabase.game)
			{
				flag = false;
			}
		}
		if (text == null)
		{
			throw new ArgumentException("Master VT file path is null.");
		}
		ILocalAssetDatabase vtMipXDatabase = AssetDatabase.GetTransient(0L, text + "/." + folder);
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		ParallelOptions opts = new ParallelOptions
		{
			MaxDegreeOfParallelism = ((!useParallelImport) ? 1 : Environment.ProcessorCount)
		};
		int total = 0;
		Task importTask = Task.Run(delegate
		{
			List<VTTextureAsset> texture2DPreProcessedAssets = database.GetAssets(default(SearchFilter<VTTextureAsset>)).ToList();
			List<SurfaceAsset> list = database.GetAssets(default(SearchFilter<SurfaceAsset>)).ToList();
			int assetsToProcess = texture2DPreProcessedAssets.Count + list.Count;
			for (int i = 0; i < list.Count; i++)
			{
				try
				{
					using (SurfaceAsset surfaceAsset = list[i])
					{
						s_Progress.Set("VT post process - Apply Surface MipBias", "Applying Mip Bias to " + surfaceAsset.name, (float)total / (float)assetsToProcess);
						log.InfoFormat("Processing {0} ({1}/{2})", surfaceAsset, total + 1, assetsToProcess);
						if (!s_Progress.shouldCancel)
						{
							surfaceAsset.LoadProperties(useVT: false);
							if (surfaceAsset.isVTMaterial && surfaceAsset.hasVTSurfaceAsset)
							{
								surfaceAsset.UpdateMipBias(vtMipXDatabase, mipBias, virtualTexturingConfig, tileSize, midMipCount);
							}
							goto IL_0127;
						}
					}
					goto end_IL_0067;
					IL_0127:
					Interlocked.Increment(ref total);
					continue;
					end_IL_0067:;
				}
				catch (Exception exception)
				{
					log.ErrorFormat(exception, "Error with {0}", list[i]);
					continue;
				}
				break;
			}
			Parallel.ForEach(texture2DPreProcessedAssets, opts, delegate(VTTextureAsset texture2DPreProcessedAsset, ParallelLoopState state, long index)
			{
				try
				{
					s_Progress.Set("VT post process - Apply Texture MipBias", "Applying Mip Bias to " + texture2DPreProcessedAsset.name, (float)total / (float)assetsToProcess);
					log.InfoFormat("Processing {0} ({1}/{2})", texture2DPreProcessedAsset, total + 1, assetsToProcess);
					if (s_Progress.shouldCancel)
					{
						state.Stop();
					}
					texture2DPreProcessedAsset.LoadHeader();
					using (Colossal.IO.AssetDatabase.TextureAsset textureAsset = texture2DPreProcessedAsset.textureAsset)
					{
						textureAsset.LoadData(0);
						if (textureAsset.width < tileSize || textureAsset.height < tileSize)
						{
							log.ErrorFormat("That texture [{0}] dimension is too small to be supported by the VT system textureSize: {1}x{2} VT tileSize: {3}", textureAsset.name, textureAsset.width, textureAsset.height, tileSize);
						}
						using VTTextureAsset vTTextureAsset = vtMipXDatabase.AddAsset<VTTextureAsset>(texture2DPreProcessedAsset.name, texture2DPreProcessedAsset.id);
						vTTextureAsset.Save(mipBias, textureAsset, tileSize, midMipCount, virtualTexturingConfig);
					}
					Interlocked.Increment(ref total);
				}
				catch (Exception exception2)
				{
					log.ErrorFormat(exception2, "Error with {0}", texture2DPreProcessedAssets);
				}
			});
		});
		if (flag)
		{
			using VTSettingsAsset vTSettingsAsset = vtMipXDatabase.AddAsset<VTSettingsAsset>("VT");
			vTSettingsAsset.Save(mipBias, tileSize, midMipCount);
		}
		Report report = new Report();
		await ExecuteMainThreadQueue(importTask, report);
	}
```

- `public static BuildMidMipsCache(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public static void BuildMidMipsCache(IEnumerable<SurfaceAsset> surfaces, int tileSize, int midMipsCount, ILocalAssetDatabase database)
	{
		s_Progress.Set("VT post process - Rebuilding mip cache", "", 0f);
		if (midMipsCount < 0)
		{
			throw new Exception("Nb mid mip levels can't be negative");
		}
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		int nbConfigStacks = virtualTexturingConfig.stackDatas.Length;
		MaterialLibrary materialLibrary = AssetDatabase.global.resources.materialLibrary;
		AtlasMaterialsGrouper atlasMaterialsGrouper = new AtlasMaterialsGrouper(nbConfigStacks, tileSize, midMipsCount);
		List<SurfaceAsset> list = surfaces.ToList();
		Dictionary<Colossal.Hash128, NativeArray<byte>> dictionary = new Dictionary<Colossal.Hash128, NativeArray<byte>>();
		Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] array = new Dictionary<Colossal.Hash128, Colossal.Hash128[]>[2];
		for (int i = 0; i < array.Length; i++)
		{
			array[i] = new Dictionary<Colossal.Hash128, Colossal.Hash128[]>();
		}
		for (int j = 0; j < list.Count; j++)
		{
			using SurfaceAsset surfaceAsset = list[j];
			s_Progress.Set("VT post process - Rebuilding mip cache", "Processing " + surfaceAsset.name, (float)j / (float)list.Count);
			surfaceAsset.LoadProperties(useVT: true);
			if (!surfaceAsset.isVTMaterial)
			{
				continue;
			}
			MaterialLibrary.MaterialDescription materialDescription = materialLibrary.GetMaterialDescription(surfaceAsset.materialTemplateHash);
			long[] textureHash = new long[materialDescription.m_Stacks.Length];
			for (int k = 0; k < materialDescription.m_Stacks.Length; k++)
			{
				Colossal.Hash128[] value = new Colossal.Hash128[4];
				array[k][surfaceAsset.id] = value;
				surfaceAsset.AddMidMipTexturesDataToDictionnary(k, midMipsCount, tileSize, materialDescription, dictionary);
			}
			int multiStackLayersMask = surfaceAsset.ComputeVTLayersMask(materialDescription, array, textureHash);
			for (int l = 0; l < surfaceAsset.stackCount; l++)
			{
				AtlassedSize unbiasedStackTextureSize = surfaceAsset.GetUnbiasedStackTextureSize(l);
				if (unbiasedStackTextureSize.x >= 0)
				{
					atlasMaterialsGrouper.Add(l, unbiasedStackTextureSize, multiStackLayersMask, surfaceAsset, textureHash, materialDescription.m_MipBiasOverride);
				}
			}
		}
		atlasMaterialsGrouper.ResolveDuplicates(array, 2);
		atlasMaterialsGrouper.GroupEntries(virtualTexturingConfig, dictionary, array);
		string assetName = AtlasMaterialsGrouper.GetAssetName(tileSize, midMipsCount);
		using (BinaryWriter bw = new BinaryWriter(database.AddAsset<MidMipCacheAsset>(AssetDataPath.Create("StreamingData~", assetName)).GetWriteStream()))
		{
			atlasMaterialsGrouper.Write(bw);
		}
		foreach (NativeArray<byte> value2 in dictionary.Values)
		{
			value2.Dispose();
		}
		atlasMaterialsGrouper.Dispose();
	}
```

- `private static CastStruct<TFrom, TTo>(TFrom s) : TTo`  

```csharp
private static TTo CastStruct<TFrom, TTo>(TFrom s);
```

- `public static CollectDataToImport(System.String projectRootPath, System.String[] assetPaths, Colossal.AssetPipeline.Diagnostic.Report report) : System.Collections.Generic.IDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>, Colossal.AssetPipeline.Settings>`  

```csharp
public static IDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings> CollectDataToImport(string projectRootPath, string[] assetPaths, Report report)
	{
		OrderedDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings> orderedDictionary = new OrderedDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings>();
		if (IsArtRootPath(projectRootPath, assetPaths, out var artProjectPath, out var artProjectRelativePaths))
		{
			using (Report.ImportStep item = report.AddImportStep("Collect asset group"))
			{
				foreach (SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset> item2 in new SourceAssetCollector(artProjectPath, artProjectRelativePaths))
				{
					Report.Asset asset = report.AddAsset(item2.name);
					Colossal.AssetPipeline.Settings value = ImportSettings(item2, (step: item, asset: asset));
					foreach (SourceAssetCollector.Asset item3 in item2)
					{
						if (value.ignoreSuffixes != null && Path.GetFileNameWithoutExtension(item3.name).EndsWithAny(value.ignoreSuffixes))
						{
							item2.RemoveFile(item3);
						}
					}
					foreach (KeyValuePair<string, string> item4 in value.UsedShaderAssets(item2, asset))
					{
						string path = ResolveRelativePath(projectRootPath, item4.Value, item2.rootPath);
						if (LongFile.Exists(path))
						{
							SourceAssetCollector.Asset file = new SourceAssetCollector.Asset(path, projectRootPath);
							item2.AddFile(file);
						}
					}
					orderedDictionary.Add(item2, value);
				}
				return orderedDictionary;
			}
		}
		throw new Exception("Invalid " + artProjectPath);
	}
```

- `public static ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
public static void ConvertSurfacesToVT(IEnumerable<SurfaceAsset> surfacesToConvert, IEnumerable<SurfaceAsset> allSurfaces, bool writeVTSettings, int tileSize, int midMipsCount, int mipBias, bool force, Report.ImportStep report)
	{
		s_Progress.Set("VT post process - Converting surfaces", "Collecting references...", 0f);
		int surfaceCount;
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> textureReferenceCount = GetTextureReferenceCount(allSurfaces, out surfaceCount);
		ReportTextureReferenceStats(textureReferenceCount, report);
		MaterialLibrary materialLibrary = AssetDatabase.global.resources.materialLibrary;
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		int num = 0;
		foreach (SurfaceAsset item in surfacesToConvert)
		{
			s_Progress.Set("VT post process - Converting surfaces", "Processing " + item.name, (float)num++ / (float)surfaceCount);
			try
			{
				bool flag = item.IsVTMaterialFromHeader();
				if (!force && flag)
				{
					continue;
				}
				item.LoadProperties(useVT: false);
				MaterialLibrary.MaterialDescription materialDescription = materialLibrary.GetMaterialDescription(item.materialTemplateHash);
				if (materialDescription != null)
				{
					if (materialDescription.m_SupportsVT)
					{
						switch (TestTextureSizesUniformity(item, tileSize, materialDescription))
						{
						case 0:
						{
							if (!materialDescription.m_SupportsVT)
							{
								break;
							}
							int mipBias2 = (materialDescription.hasMipBiasOverride ? materialDescription.m_MipBiasOverride : mipBias);
							if (item.Save(mipBias2, force: true, saveTextures: true, vt: true, virtualTexturingConfig, textureReferenceCount, tileSize, midMipsCount))
							{
								log.InfoFormat("File {0} has been converted to VT", item);
							}
							goto end_IL_0089;
						}
						case -1:
							log.WarnFormat("File {0} cannot use VT because at least one of its textures width is smaller than the tileSize {1}", item, tileSize);
							break;
						case -2:
							log.WarnFormat("File {0} cannot use VT because at least one of its textures height is smaller than the tileSize {1}", item, tileSize);
							break;
						case -3:
							log.WarnFormat("File {0} cannot use VT because at least one texture uses a wrap mode that is not Clamp", item);
							break;
						case -4:
							log.WarnFormat("File {0} cannot use VT because its texture sizes is not uniform", item);
							break;
						case -5:
							log.WarnFormat("File {0} cannot use VT because some of its textures are null", item);
							break;
						}
					}
					else
					{
						log.WarnFormat("File {0} cannot use VT because its template {2} (Shader:{3}) from material hash {1} is not set to support VT", item, item.materialTemplateHash, materialDescription.m_Material.name, materialDescription.m_Material.shader.name);
					}
				}
				else
				{
					log.WarnFormat("File {0} cannot use VT because its material hash {1} is not mapped or not found", item, item.materialTemplateHash);
				}
				if (flag)
				{
					item.Save(0, force: true, saveTextures: false);
					log.InfoFormat("File {0} has been unconverted from VT", item);
				}
				end_IL_0089:;
			}
			catch (Exception exception)
			{
				log.ErrorFormat(exception, "Error occured with {0}", item);
				throw;
			}
			finally
			{
				item.Unload();
			}
		}
		if (writeVTSettings)
		{
			using (VTSettingsAsset vTSettingsAsset = AssetDatabase.game.AddAsset<VTSettingsAsset>(AssetDataPath.Create(EnvPath.kVTSubPath, "VT")))
			{
				vTSettingsAsset.Save(mipBias, tileSize, midMipsCount);
			}
		}
	}
```

- `public static ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean writeVTSettings, System.Int32 tileSize, System.Int32 midMipsCount, System.Int32 mipBias, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
public static void ConvertSurfacesToVT(IEnumerable<SurfaceAsset> surfacesToConvert, IEnumerable<SurfaceAsset> allSurfaces, bool writeVTSettings, int tileSize, int midMipsCount, int mipBias, bool force, Report.ImportStep report)
	{
		s_Progress.Set("VT post process - Converting surfaces", "Collecting references...", 0f);
		int surfaceCount;
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> textureReferenceCount = GetTextureReferenceCount(allSurfaces, out surfaceCount);
		ReportTextureReferenceStats(textureReferenceCount, report);
		MaterialLibrary materialLibrary = AssetDatabase.global.resources.materialLibrary;
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		int num = 0;
		foreach (SurfaceAsset item in surfacesToConvert)
		{
			s_Progress.Set("VT post process - Converting surfaces", "Processing " + item.name, (float)num++ / (float)surfaceCount);
			try
			{
				bool flag = item.IsVTMaterialFromHeader();
				if (!force && flag)
				{
					continue;
				}
				item.LoadProperties(useVT: false);
				MaterialLibrary.MaterialDescription materialDescription = materialLibrary.GetMaterialDescription(item.materialTemplateHash);
				if (materialDescription != null)
				{
					if (materialDescription.m_SupportsVT)
					{
						switch (TestTextureSizesUniformity(item, tileSize, materialDescription))
						{
						case 0:
						{
							if (!materialDescription.m_SupportsVT)
							{
								break;
							}
							int mipBias2 = (materialDescription.hasMipBiasOverride ? materialDescription.m_MipBiasOverride : mipBias);
							if (item.Save(mipBias2, force: true, saveTextures: true, vt: true, virtualTexturingConfig, textureReferenceCount, tileSize, midMipsCount))
							{
								log.InfoFormat("File {0} has been converted to VT", item);
							}
							goto end_IL_0089;
						}
						case -1:
							log.WarnFormat("File {0} cannot use VT because at least one of its textures width is smaller than the tileSize {1}", item, tileSize);
							break;
						case -2:
							log.WarnFormat("File {0} cannot use VT because at least one of its textures height is smaller than the tileSize {1}", item, tileSize);
							break;
						case -3:
							log.WarnFormat("File {0} cannot use VT because at least one texture uses a wrap mode that is not Clamp", item);
							break;
						case -4:
							log.WarnFormat("File {0} cannot use VT because its texture sizes is not uniform", item);
							break;
						case -5:
							log.WarnFormat("File {0} cannot use VT because some of its textures are null", item);
							break;
						}
					}
					else
					{
						log.WarnFormat("File {0} cannot use VT because its template {2} (Shader:{3}) from material hash {1} is not set to support VT", item, item.materialTemplateHash, materialDescription.m_Material.name, materialDescription.m_Material.shader.name);
					}
				}
				else
				{
					log.WarnFormat("File {0} cannot use VT because its material hash {1} is not mapped or not found", item, item.materialTemplateHash);
				}
				if (flag)
				{
					item.Save(0, force: true, saveTextures: false);
					log.InfoFormat("File {0} has been unconverted from VT", item);
				}
				end_IL_0089:;
			}
			catch (Exception exception)
			{
				log.ErrorFormat(exception, "Error occured with {0}", item);
				throw;
			}
			finally
			{
				item.Unload();
			}
		}
		if (writeVTSettings)
		{
			using (VTSettingsAsset vTSettingsAsset = AssetDatabase.game.AddAsset<VTSettingsAsset>(AssetDataPath.Create(EnvPath.kVTSubPath, "VT")))
			{
				vTSettingsAsset.Save(mipBias, tileSize, midMipsCount);
			}
		}
	}
```

- `private static CreateAssetGroupFromSettings(System.String projectRootPath, Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport) : Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset>`  

```csharp
private static SourceAssetCollector.AssetGroup<IAsset> CreateAssetGroupFromSettings(string projectRootPath, Colossal.AssetPipeline.Settings settings, SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset> assetGroup, Report.Asset assetReport)
	{
		HashSet<IAsset> hashSet = new HashSet<IAsset>(assetGroup.count);
		foreach (SourceAssetCollector.Asset item in assetGroup)
		{
			if (settings.ignoreSuffixes == null || !Path.GetFileNameWithoutExtension(item.name).EndsWithAny(settings.ignoreSuffixes))
			{
				IAsset asset = IAsset.Create(settings, Path.GetFileNameWithoutExtension(item.name), item);
				if (asset != null)
				{
					hashSet.Add(asset);
				}
			}
		}
		foreach (KeyValuePair<string, string> item2 in settings.UsedShaderAssets(assetGroup, assetReport))
		{
			string path = ResolveRelativePath(projectRootPath, item2.Value, assetGroup.rootPath);
			if (!LongFile.Exists(path))
			{
				string fileName = Path.GetFileName(path);
				path = EnvPath.kContentPath + "/Game/.ModdingToolchain/shared_assets_fallback/" + fileName;
				log.InfoFormat("Using fallback {0}", fileName);
			}
			if (LongFile.Exists(path))
			{
				IAsset asset2 = IAsset.Create(sourceAsset: new SourceAssetCollector.Asset(path, projectRootPath), settings: settings, name: Path.GetFileNameWithoutExtension(item2.Key));
				if (asset2 != null)
				{
					hashSet.Add(asset2);
				}
			}
		}
		return new SourceAssetCollector.AssetGroup<IAsset>(assetGroup.rootPath, hashSet);
	}
```

- `private static CreateBackground(UnityEngine.Transform parent, System.String name, UnityEngine.Vector3 position, UnityEngine.Vector3 size) : System.Void`  

```csharp
private static void CreateBackground(Transform parent, string name, Vector3 position, Vector3 size)
	{
		GameObject gameObject = GameObject.CreatePrimitive(PrimitiveType.Plane);
		gameObject.name = name;
		gameObject.transform.SetParent(parent, worldPositionStays: false);
		gameObject.transform.localRotation = Quaternion.Euler(-90f, 0f, 0f);
		gameObject.transform.localScale = size;
		gameObject.transform.localPosition = new Vector3(position.x, position.y, position.z + 0.05f);
		gameObject.GetComponent<Renderer>().sharedMaterial = backgroundMaterial;
	}
```

- `private static CreateBounds(UnityEngine.Transform parent) : System.Void`  

```csharp
private static void CreateBounds(Transform parent)
	{
		Transform transform = parent.Find("Title");
		Transform transform2 = transform.Find("TextBg");
		CreateBackground(transform, "BoundsTop", Vector3.zero, new Vector3(1f, 1f, 0.1f));
		CreateBackground(transform, "BoundsBottom", Vector3.zero, new Vector3(1f, 1f, 0.1f));
		CreateBackground(transform, "BoundsRight", Vector3.zero, new Vector3(0.1f, 1f, 1f));
		CreateBackground(transform, "BoundsLeft", new Vector3((transform2.localScale.x * 0.5f + 0.05f) * 10f, 0f, 0f), new Vector3(0.1f, 1f, 1f));
	}
```

- `private static CreateDidimoAssets(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  

```csharp
private static System.Void CreateDidimoAssets(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `private static CreateGeometriesAndSurfaces(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  

```csharp
private static System.Void CreateGeometriesAndSurfaces(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `private static CreatePrefab<T>(System.String suffix, System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : T`  

```csharp
private static T CreatePrefab<T>(System.String suffix, System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory);
```

- `private static CreateRenderPrefab(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> asset, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>>`  

```csharp
private static RenderPrefab CreateRenderPrefab(string sourcePath, string name, int lodLevel, IPrefabFactory prefabFactory = null)
	{
		return CreatePrefab<RenderPrefab>("Mesh", sourcePath, name, lodLevel, prefabFactory);
	}
```

- `private static CreateRenderPrefab(System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : Game.Prefabs.RenderPrefab`  

```csharp
private static RenderPrefab CreateRenderPrefab(string sourcePath, string name, int lodLevel, IPrefabFactory prefabFactory = null)
	{
		return CreatePrefab<RenderPrefab>("Mesh", sourcePath, name, lodLevel, prefabFactory);
	}
```

- `private static CreateRenderPrefabs(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Void`  

```csharp
private static void CreateRenderPrefabs(Colossal.AssetPipeline.Settings settings, string sourcePath, IReadOnlyList<List<Colossal.AssetPipeline.LOD>> assets, ImportMode importMode, Report report, HashSet<SurfaceAsset> VTMaterials, IPrefabFactory prefabFactory = null)
	{
		using (s_ProfPostImport.Auto())
		{
			if (!IsLODsValid(assets))
			{
				log.DebugFormat("Result for {0} is not valid and will not be serialized", sourcePath);
				return;
			}
			string name = assets[0][0].name;
			try
			{
				using (report.AddImportStep("Perform main thread tasks (Assetdatabase serialization + Prefabs upgrade)"))
				{
					foreach (List<Colossal.AssetPipeline.LOD> asset in assets)
					{
						CreateRenderPrefab(settings, sourcePath, asset, importMode, report, VTMaterials, prefabFactory);
					}
				}
			}
			catch (Exception ex)
			{
				log.Error(ex, "Error post-importing " + name + ".");
				report.AddError("Error post-importing " + name + ": " + ex.Message + ".");
			}
		}
	}
```

- `private static CreateStylePrefab(System.ValueTuple<System.String, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Colossal.Animations.Animation, Colossal.Animations.BoneHierarchy, System.String, System.Int32, Colossal.Hash128>>, System.Int32, System.Int32> style, System.String sourcePath, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.AnimationAsset> overrideSafeGuard, System.Collections.Generic.List<Game.Prefabs.RenderPrefab> prefabs, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : Game.Prefabs.CharacterStyle`  

```csharp
private static Game.Prefabs.CharacterStyle CreateStylePrefab(System.ValueTuple<System.String, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Colossal.Animations.Animation, Colossal.Animations.BoneHierarchy, System.String, System.Int32, Colossal.Hash128>>, System.Int32, System.Int32> style, System.String sourcePath, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.AnimationAsset> overrideSafeGuard, System.Collections.Generic.List<Game.Prefabs.RenderPrefab> prefabs, Game.AssetPipeline.IPrefabFactory prefabFactory);
```

- `private static CreateTitle(UnityEngine.Transform parent, System.String text, UnityEngine.Vector3 textPosOffset, UnityEngine.Color bgColor, UnityEngine.Color txtColor, System.Int32 txtSize, System.Single txtPadding) : System.Void`  

```csharp
private static void CreateTitle(Transform parent, string text, Vector3 textPosOffset, Color bgColor, Color txtColor, int txtSize, float txtPadding)
	{
		GameObject gameObject = new GameObject("Title");
		gameObject.transform.SetParent(parent, worldPositionStays: false);
		gameObject.transform.rotation = Quaternion.Euler(90f, 0f, 0f);
		TextMeshPro textMeshPro = gameObject.AddComponent<TextMeshPro>();
		textMeshPro.font = Resources.Load<TMP_FontAsset>("Fonts & Materials/LiberationSans SDF");
		textMeshPro.text = text;
		textMeshPro.fontSize = txtSize;
		textMeshPro.color = txtColor;
		textMeshPro.alignment = TextAlignmentOptions.Center;
		textMeshPro.enableWordWrapping = false;
		Vector2 preferredValues = textMeshPro.GetPreferredValues();
		Vector3 vector = new Vector3(preferredValues.x + txtPadding, preferredValues.y + txtPadding, 0.1f);
		gameObject.transform.localPosition = textPosOffset + new Vector3((0f - preferredValues.x) / 2f, 0f, 0f);
		CreateBackground(gameObject.transform, "TextBg", Vector3.zero, new Vector3(vector.x / 10f, 1f, vector.y / 10f));
		backgroundMaterial.color = bgColor;
	}
```

- `private static DisposeLODs(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD>> assets) : System.Void`  

```csharp
private static void DisposeLODs(IReadOnlyList<Colossal.AssetPipeline.LOD> assets)
	{
		foreach (Colossal.AssetPipeline.LOD asset in assets)
		{
			asset.Dispose();
		}
	}
```

- `private static DisposeLODs(System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> assets) : System.Void`  

```csharp
private static void DisposeLODs(IReadOnlyList<Colossal.AssetPipeline.LOD> assets)
	{
		foreach (Colossal.AssetPipeline.LOD asset in assets)
		{
			asset.Dispose();
		}
	}
```

- `private static ExecuteMainThreadQueue(System.Threading.Tasks.Task importTask, Colossal.AssetPipeline.Diagnostic.Report report) : System.Threading.Tasks.Task`  

```csharp
private static async Task ExecuteMainThreadQueue(Task importTask, Report report)
	{
		using (report.AddImportStep("Process main thread task queue"))
		{
			while ((!importTask.IsCompleted || s_MainThreadDispatcher.hasPendingTasks) && !s_Progress.shouldCancel)
			{
				s_Progress.Update();
				if (s_MainThreadDispatcher.hasPendingTasks)
				{
					s_Progress.SetThreadDescription($"Executing {s_MainThreadDispatcher.pendingTasksCount} tasks");
					s_MainThreadDispatcher.ProcessTasks();
				}
				await Task.Yield();
			}
		}
		await importTask;
	}
```

- `private static FromManagedArray<T>(T[] array) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private static Unity.Collections.NativeArray<System.Byte> FromManagedArray<T>(T[] array);
```

- `private static FromManagedArray<T>(T[] array, System.Int32 offset, System.Int32 elementSize, System.Int32 countPerElement) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private static Unity.Collections.NativeArray<System.Byte> FromManagedArray<T>(T[] array, System.Int32 offset, System.Int32 elementSize, System.Int32 countPerElement);
```

- `public static GenerateJSONSchema() : System.Void`  

```csharp
public static void GenerateJSONSchema()
	{
		PostProcessorCache.CachePostProcessors();
		ImporterCache.CacheSupportedExtensions();
		Variant variant = new ProxyObject();
		variant["$schema"] = new ProxyString("http://json-schema.org/draft-07/schema#");
		variant["definitions"] = GetDefinitions();
		ToJsonSchema(typeof(Colossal.AssetPipeline.Settings), variant);
		Variant schema = (variant["patternProperties"] = new ProxyObject());
		AddSimplifiedProperties(schema);
		variant["additionalProperties"] = new ProxyBoolean(value: false);
		string message = (GUIUtility.systemCopyBuffer = variant.ToJSON());
		log.Info(message);
	}
```

- `private static GetDefinitions() : Colossal.Json.Variant`  

```csharp
private static Variant GetDefinitions()
	{
		ProxyObject proxyObject = new ProxyObject();
		IEnumerable<string> source = (from ext in ImporterCache.GetSupportedExtensions()
			select ImporterCache.GetImporter(ext.Key).GetType()).Distinct().SelectMany((Type t) => new string[2]
		{
			t.FullName,
			t.TypeName()
		});
		proxyObject["importers"] = JSON.Load("{ \"type\": \"string\", \"enum\": " + source.ToArray().ToJSONString() + " }");
		IEnumerable<string> source2 = (from x in (from x in (from x in (from x in (from ext in ImporterCache.GetSupportedExtensions()
							select ImporterCache.GetImporter(ext.Key).GetDefaultSettings()?.GetType()).Distinct().Concat(from x in PostProcessorCache.GetTexturePostProcessors()
							select x.GetDefaultSettings()?.GetType())
						where x != null
						select x).Concat(from x in PostProcessorCache.GetModelPostProcessors()
						select x.GetDefaultSettings()?.GetType())
					where x != null
					select x).Concat(from x in PostProcessorCache.GetModelSurfacePostProcessors()
					select x.GetDefaultSettings()?.GetType())
				where x != null
				select x).Concat(from x in PostProcessorCache.GetGeometryPostProcessors()
				select x.GetDefaultSettings()?.GetType())
			where x != null
			select x).SelectMany((Type t) => new string[2]
		{
			t.FullName,
			t.TypeName()
		});
		proxyObject["settingsType"] = JSON.Load("{ \"type\": \"string\", \"enum\": " + source2.ToArray().ToJSONString() + " }");
		return proxyObject;
	}
```

- `public static GetImportChainFor(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ISettingable>`  

```csharp
public static IEnumerable<ISettingable> GetImportChainFor(Colossal.AssetPipeline.Settings settings, SourceAssetCollector.Asset asset, ReportBase report)
	{
		List<ISettingable> list = new List<ISettingable>();
		if (ImporterCache.GetImporter<IAssetImporter>(asset.path, out var importer, settings.importerTypeHints))
		{
			list.Add(importer);
		}
		string assetName;
		try
		{
			AssetUtils.ParseName(Path.GetFileNameWithoutExtension(asset.name), out var _, out assetName, out var _, out var _, out var _, out var _, out var _, out var _);
		}
		catch (FormatException)
		{
			log.WarnFormat("Invalid filename: {0}", Path.GetFileNameWithoutExtension(asset.name));
			assetName = Path.GetFileName(asset.name);
		}
		if (importer is TextureImporter)
		{
			foreach (ITexturePostProcessor texturePostProcessor in PostProcessorCache.GetTexturePostProcessors())
			{
				if (settings.GetPostProcessSettings(asset.name, texturePostProcessor, report, out var _))
				{
					list.Add(texturePostProcessor);
				}
			}
		}
		if (importer is ModelImporter)
		{
			foreach (IModelPostProcessor modelPostProcessor in PostProcessorCache.GetModelPostProcessors())
			{
				if (settings.GetPostProcessSettings(asset.name, modelPostProcessor, report, out var _))
				{
					list.Add(modelPostProcessor);
				}
			}
			foreach (IModelSurfacePostProcessor modelSurfacePostProcessor in PostProcessorCache.GetModelSurfacePostProcessors())
			{
				if (settings.GetPostProcessSettings(assetName, modelSurfacePostProcessor, report, out var _))
				{
					list.Add(modelSurfacePostProcessor);
				}
			}
			foreach (IGeometryPostProcessor geometryPostProcessor in PostProcessorCache.GetGeometryPostProcessors())
			{
				if (settings.GetPostProcessSettings(assetName, geometryPostProcessor, report, out var _))
				{
					list.Add(geometryPostProcessor);
				}
			}
		}
		return list;
	}
```

- `private static GetNameWithoutGUID(System.String str) : System.String`  

```csharp
private static string GetNameWithoutGUID(string str)
	{
		return str.Substring(0, str.LastIndexOf("_"));
	}
```

- `private static GetSettings() : System.String`  

```csharp
private static string GetSettings()
	{
		string[] array = (from x in (from settings in (from ext in ImporterCache.GetSupportedExtensions()
					select ImporterCache.GetImporter(ext.Key).GetDefaultSettings()).Concat(from x in PostProcessorCache.GetTexturePostProcessors()
					select x.GetDefaultSettings()).Concat(from x in PostProcessorCache.GetModelPostProcessors()
					select x.GetDefaultSettings()).Concat(from x in PostProcessorCache.GetModelSurfacePostProcessors()
					select x.GetDefaultSettings())
					.Concat(from x in PostProcessorCache.GetGeometryPostProcessors()
						select x.GetDefaultSettings())
				where settings != null
				group settings by settings.GetType() into @group
				select @group.First()).Select(GetIfThen)
			where x != null
			select x).ToArray();
		string text = string.Empty;
		for (int num = 0; num < array.Length; num++)
		{
			if (num > 0)
			{
				text += ", \"else\": {";
			}
			text += array[num];
		}
		text += ", \"else\": { \"additionalProperties\": false";
		for (int num2 = 0; num2 < array.Length; num2++)
		{
			text += "}";
		}
		return text;
		static string GetIfThen(ISettings settings)
		{
			Variant variant = ToJsonSchema(settings);
			if (variant == null)
			{
				return null;
			}
			string text2 = "[ { \"const\": \"" + settings.GetType().FullName + "\" }, { \"const\": \"" + settings.GetType().TypeName() + "\" } ]";
			return "\"if\": { \"properties\": { \"@type\": { \"oneOf\": " + text2 + " } } }, \"then\": " + variant.ToJSONString();
		}
	}

	private static Variant GetDefinitions()
	{
		ProxyObject proxyObject = new ProxyObject();
		IEnumerable<string> source = (from ext in ImporterCache.GetSupportedExtensions()
			select ImporterCache.GetImporter(ext.Key).GetType()).Distinct().SelectMany((Type t) => new string[2]
		{
			t.FullName,
			t.TypeName()
		});
		proxyObject["importers"] = JSON.Load("{ \"type\": \"string\", \"enum\": " + source.ToArray().ToJSONString() + " }");
		IEnumerable<string> source2 = (from x in (from x in (from x in (from x in (from ext in ImporterCache.GetSupportedExtensions()
							select ImporterCache.GetImporter(ext.Key).GetDefaultSettings()?.GetType()).Distinct().Concat(from x in PostProcessorCache.GetTexturePostProcessors()
							select x.GetDefaultSettings()?.GetType())
						where x != null
						select x).Concat(from x in PostProcessorCache.GetModelPostProcessors()
						select x.GetDefaultSettings()?.GetType())
					where x != null
					select x).Concat(from x in PostProcessorCache.GetModelSurfacePostProcessors()
					select x.GetDefaultSettings()?.GetType())
				where x != null
				select x).Concat(from x in PostProcessorCache.GetGeometryPostProcessors()
				select x.GetDefaultSettings()?.GetType())
			where x != null
			select x).SelectMany((Type t) => new string[2]
		{
			t.FullName,
			t.TypeName()
		});
		proxyObject["settingsType"] = JSON.Load("{ \"type\": \"string\", \"enum\": " + source2.ToArray().ToJSONString() + " }");
		return proxyObject;
	}

	private static string ToJsonSchema(FieldInfo fieldInfo)
	{
		string name = fieldInfo.Name;
		Type fieldType = fieldInfo.FieldType;
		bool nullable = name == "materialTemplate";
		string text = "\"type\": " + ToJsonType(fieldType, nullable);
		if (fieldType.IsEnum)
		{
			return text + ", \"enum\": " + Enum.GetNames(fieldType).ToJSONString();
		}
		if (fieldType.IsArray)
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetElementType()).ToJSONString();
		}
		if (typeof(IList).IsAssignableFrom(fieldType))
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetGenericArguments()[0]).ToJSONString();
		}
		return name switch
		{
			"importerTypeHints" => text + ", \"patternProperties\": { \"^\\\\.[A-Za-z0-9]+$\": { \"$ref\": \"#/definitions/importers\" } }, \"additionalProperties\": false", 
			"sharedAssets" => text + ", \"patternProperties\": { \"^[A-Za-z0-9_*{}]+(\\\\.[A-Za-z0-9]+)?(/_[A-Za-z0-9]+)?$\": { \"type\": \"string\", \"format\": \"uri-reference\" } }, \"additionalProperties\": false", 
			"importSettings" => text + ", \"additionalProperties\": { " + GetSettings() + " }", 
			_ => text, 
		};
	}

	private static void AddSimplifiedProperties(Variant schema)
	{
		schema["^LOD(\\d+|\\*)?(_[A-Za-z0-9*]+)?$"] = ToJsonSchema(typeof(LODPostProcessor.PostProcessSettings.LODLevelSettings));
		schema["^Surface(_[A-Za-z0-9*]+)?$"] = ToJsonSchema(typeof(SurfacePostProcessor.PostProcessSettings));
	}

	public static void GenerateJSONSchema()
	{
		PostProcessorCache.CachePostProcessors();
		ImporterCache.CacheSupportedExtensions();
		Variant variant = new ProxyObject();
		variant["$schema"] = new ProxyString("http://json-schema.org/draft-07/schema#");
		variant["definitions"] = GetDefinitions();
		ToJsonSchema(typeof(Colossal.AssetPipeline.Settings), variant);
		Variant schema = (variant["patternProperties"] = new ProxyObject());
		AddSimplifiedProperties(schema);
		variant["additionalProperties"] = new ProxyBoolean(value: false);
		string message = (GUIUtility.systemCopyBuffer = variant.ToJSON());
		log.Info(message);
	}

	private static string AdjustNamingConvention(string input)
	{
		StringBuilder stringBuilder = new StringBuilder();
		bool flag = true;
		foreach (char c in input)
		{
			if (flag)
			{
				stringBuilder.Append(char.ToUpper(c));
				flag = false;
			}
			else
			{
				stringBuilder.Append(c);
			}
			if (c == '_')
			{
				flag = true;
			}
		}
		return stringBuilder.ToString();
	}

	private static bool IsArtRootPath(string rootPathName, string path, out string artProjectPath, out string artProjectRelativePath)
	{
		if (rootPathName == null)
		{
			throw new IOException("rootPath can not be null");
		}
		if (path == null)
		{
			throw new IOException("import path can not be null");
		}
		if (path == rootPathName)
		{
			throw new IOException("rootPath can not be the same as import path");
		}
		int num = path.IndexOf(rootPathName, StringComparison.Ordinal);
		bool flag = num != -1;
		artProjectRelativePath = (flag ? path.Substring(num + rootPathName.Length).Replace('\\', '/').TrimStart('/') : null);
		artProjectPath = (flag ? path.Substring(0, num + rootPathName.Length).Replace('\\', '/').TrimEnd('/') : null);
		return flag;
	}

	public static bool IsArtRootPath(string rootPathName, string[] paths, out string artProjectPath, out List<string> artProjectRelativePaths)
	{
		artProjectPath = null;
		artProjectRelativePaths = new List<string>(paths.Length);
		foreach (string text in paths)
		{
			if (!string.IsNullOrEmpty(text))
			{
				if (!IsArtRootPath(rootPathName, text, out var artProjectPath2, out var artProjectRelativePath))
				{
					return false;
				}
				if (artProjectPath != null && artProjectPath2 != artProjectPath)
				{
					throw new Exception("Root project path does not match. Previous: " + artProjectPath + " Current: " + artProjectPath2);
				}
				artProjectPath = artProjectPath2;
				artProjectRelativePaths.Add(artProjectRelativePath);
			}
		}
		return true;
	}

	public static IEnumerable<ISettingable> GetImportChainFor(Colossal.AssetPipeline.Settings settings, SourceAssetCollector.Asset asset, ReportBase report)
	{
		List<ISettingable> list = new List<ISettingable>();
		if (ImporterCache.GetImporter<IAssetImporter>(asset.path, out var importer, settings.importerTypeHints))
		{
			list.Add(importer);
		}
		string assetName;
		try
		{
			AssetUtils.ParseName(Path.GetFileNameWithoutExtension(asset.name), out var _, out assetName, out var _, out var _, out var _, out var _, out var _, out var _);
		}
		catch (FormatException)
		{
			log.WarnFormat("Invalid filename: {0}", Path.GetFileNameWithoutExtension(asset.name));
			assetName = Path.GetFileName(asset.name);
		}
		if (importer is TextureImporter)
		{
			foreach (ITexturePostProcessor texturePostProcessor in PostProcessorCache.GetTexturePostProcessors())
			{
				if (settings.GetPostProcessSettings(asset.name, texturePostProcessor, report, out var _))
				{
					list.Add(texturePostProcessor);
				}
			}
		}
		if (importer is ModelImporter)
		{
			foreach (IModelPostProcessor modelPostProcessor in PostProcessorCache.GetModelPostProcessors())
			{
				if (settings.GetPostProcessSettings(asset.name, modelPostProcessor, report, out var _))
				{
					list.Add(modelPostProcessor);
				}
			}
			foreach (IModelSurfacePostProcessor modelSurfacePostProcessor in PostProcessorCache.GetModelSurfacePostProcessors())
			{
				if (settings.GetPostProcessSettings(assetName, modelSurfacePostProcessor, report, out var _))
				{
					list.Add(modelSurfacePostProcessor);
				}
			}
			foreach (IGeometryPostProcessor geometryPostProcessor in PostProcessorCache.GetGeometryPostProcessors())
			{
				if (settings.GetPostProcessSettings(assetName, geometryPostProcessor, report, out var _))
				{
					list.Add(geometryPostProcessor);
				}
			}
		}
		return list;
	}

	public static IDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings> CollectDataToImport(string projectRootPath, string[] assetPaths, Report report)
	{
		OrderedDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings> orderedDictionary = new OrderedDictionary<SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset>, Colossal.AssetPipeline.Settings>();
		if (IsArtRootPath(projectRootPath, assetPaths, out var artProjectPath, out var artProjectRelativePaths))
		{
			using (Report.ImportStep item = report.AddImportStep("Collect asset group"))
			{
				foreach (SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset> item2 in new SourceAssetCollector(artProjectPath, artProjectRelativePaths))
				{
					Report.Asset asset = report.AddAsset(item2.name);
					Colossal.AssetPipeline.Settings value = ImportSettings(item2, (step: item, asset: asset));
					foreach (SourceAssetCollector.Asset item3 in item2)
					{
						if (value.ignoreSuffixes != null && Path.GetFileNameWithoutExtension(item3.name).EndsWithAny(value.ignoreSuffixes))
						{
							item2.RemoveFile(item3);
						}
					}
					foreach (KeyValuePair<string, string> item4 in value.UsedShaderAssets(item2, asset))
					{
						string path = ResolveRelativePath(projectRootPath, item4.Value, item2.rootPath);
						if (LongFile.Exists(path))
						{
							SourceAssetCollector.Asset file = new SourceAssetCollector.Asset(path, projectRootPath);
							item2.AddFile(file);
						}
					}
					orderedDictionary.Add(item2, value);
				}
				return orderedDictionary;
			}
		}
		throw new Exception("Invalid " + artProjectPath);
	}

	private static void CreateTitle(Transform parent, string text, Vector3 textPosOffset, Color bgColor, Color txtColor, int txtSize, float txtPadding)
	{
		GameObject gameObject = new GameObject("Title");
		gameObject.transform.SetParent(parent, worldPositionStays: false);
		gameObject.transform.rotation = Quaternion.Euler(90f, 0f, 0f);
		TextMeshPro textMeshPro = gameObject.AddComponent<TextMeshPro>();
		textMeshPro.font = Resources.Load<TMP_FontAsset>("Fonts & Materials/LiberationSans SDF");
		textMeshPro.text = text;
		textMeshPro.fontSize = txtSize;
		textMeshPro.color = txtColor;
		textMeshPro.alignment = TextAlignmentOptions.Center;
		textMeshPro.enableWordWrapping = false;
		Vector2 preferredValues = textMeshPro.GetPreferredValues();
		Vector3 vector = new Vector3(preferredValues.x + txtPadding, preferredValues.y + txtPadding, 0.1f);
		gameObject.transform.localPosition = textPosOffset + new Vector3((0f - preferredValues.x) / 2f, 0f, 0f);
		CreateBackground(gameObject.transform, "TextBg", Vector3.zero, new Vector3(vector.x / 10f, 1f, vector.y / 10f));
		backgroundMaterial.color = bgColor;
	}

	private static void CreateBounds(Transform parent)
	{
		Transform transform = parent.Find("Title");
		Transform transform2 = transform.Find("TextBg");
		CreateBackground(transform, "BoundsTop", Vector3.zero, new Vector3(1f, 1f, 0.1f));
		CreateBackground(transform, "BoundsBottom", Vector3.zero, new Vector3(1f, 1f, 0.1f));
		CreateBackground(transform, "BoundsRight", Vector3.zero, new Vector3(0.1f, 1f, 1f));
		CreateBackground(transform, "BoundsLeft", new Vector3((transform2.localScale.x * 0.5f + 0.05f) * 10f, 0f, 0f), new Vector3(0.1f, 1f, 1f));
	}

	private static void AdjustZBounds(Transform parent, float z)
	{
		Transform transform = parent.Find("Title");
		Transform transform2 = transform.Find("BoundsTop");
		Transform transform3 = transform.Find("BoundsBottom");
		Transform transform4 = transform.Find("BoundsRight");
		Transform transform5 = transform.Find("BoundsLeft");
		Vector3 localPosition = transform2.localPosition;
		localPosition.y = z;
		transform2.localPosition = localPosition;
		Vector3 localPosition2 = transform3.localPosition;
		localPosition2.y = 0f - z;
		transform3.localPosition = localPosition2;
		Vector3 localScale = transform5.localScale;
		localScale.z = z * 2f / 10f;
		transform5.localScale = localScale;
		Vector3 localScale2 = transform4.localScale;
		localScale2.z = z * 2f / 10f;
		transform4.localScale = localScale2;
	}

	private static void AdjustXBounds(Transform parent, float x)
	{
		Transform transform = parent.Find("Title");
		Transform transform2 = transform.Find("BoundsTop");
		Transform transform3 = transform.Find("BoundsBottom");
		Transform transform4 = transform.Find("BoundsRight");
		Vector3 localPosition = transform.Find("BoundsLeft").transform.localPosition;
		Vector3 localPosition2 = localPosition;
		localPosition2.x += x;
		transform4.transform.localPosition = localPosition2;
		float x2 = (localPosition.x + localPosition2.x) * 0.5f;
		Vector3 localPosition3 = transform2.localPosition;
		localPosition3.x = x2;
		transform2.localPosition = localPosition3;
		Vector3 localPosition4 = transform3.localPosition;
		localPosition4.x = x2;
		transform3.localPosition = localPosition4;
		float x3 = (localPosition2.x - localPosition.x) / 10f + 0.1f;
		Vector3 localScale = transform2.localScale;
		localScale.x = x3;
		transform2.localScale = localScale;
		Vector3 localScale2 = transform3.localScale;
		localScale2.x = x3;
		transform3.localScale = localScale2;
	}

	private static void CreateBackground(Transform parent, string name, Vector3 position, Vector3 size)
	{
		GameObject gameObject = GameObject.CreatePrimitive(PrimitiveType.Plane);
		gameObject.name = name;
		gameObject.transform.SetParent(parent, worldPositionStays: false);
		gameObject.transform.localRotation = Quaternion.Euler(-90f, 0f, 0f);
		gameObject.transform.localScale = size;
		gameObject.transform.localPosition = new Vector3(position.x, position.y, position.z + 0.05f);
		gameObject.GetComponent<Renderer>().sharedMaterial = backgroundMaterial;
	}

	public static void InstantiateRenderPrefabs<T>(IEnumerable<(T prefab, string sourcePath)> prefabs, bool smartInstantiate, bool ignoreLODs) where T : PrefabBase
	{
		if (smartInstantiate)
		{
			List<(RenderPrefab, string)> list = (from tuple in prefabs
				where tuple.prefab is RenderPrefab && (!ignoreLODs || !tuple.prefab.name.Contains("_LOD"))
				select (tuple.prefab as RenderPrefab, GetParent(tuple.sourcePath)) into x
				orderby x.Item1.name, x.Item2
				select x).ToList();
			Dictionary<string, int> dictionary = new Dictionary<string, int>();
			List<float> list2 = new List<float>();
			int num = 0;
			foreach (var item in list)
			{
				Bounds bounds = RenderingUtils.ToBounds(item.Item1.bounds);
				if (!dictionary.TryGetValue(item.Item2, out var value))
				{
					list2.Add(bounds.extents.z * 1.5f);
					dictionary.Add(item.Item2, num);
					num++;
				}
				else
				{
					list2[value] = Mathf.Max(list2[value], bounds.extents.z * 1.5f);
				}
			}
			float num2 = 5f;
			float num3 = 0f;
			Dictionary<string, GameObject> dictionary2 = new Dictionary<string, GameObject>(dictionary.Count);
			List<float> list3 = Enumerable.Repeat(num2, dictionary.Count).ToList();
			{
				foreach (var item2 in list)
				{
					int index = dictionary[item2.Item2];
					if (!dictionary2.TryGetValue(item2.Item2, out var value2))
					{
						string fileName = Path.GetFileName(item2.Item2);
						value2 = GameObject.Find(fileName);
						if (value2 == null)
						{
							value2 = new GameObject(fileName);
							CreateTitle(value2.transform, fileName, new Vector3(0f, 0.1f, 0f), new Color32(1, 174, 240, byte.MaxValue), Color.white, 48, 0.1f);
							CreateBounds(value2.transform);
						}
						num3 += list2[index];
						value2.transform.position = new Vector3(0f, 0f, num3);
						num3 += list2[index] + 10f;
						AdjustZBounds(value2.transform, list2[index] + 5f);
						dictionary2.Add(item2.Item2, value2);
					}
					if (GameObject.Find(value2.name + "/" + item2.Item1.name) == null)
					{
						GameObject gameObject = new GameObject(item2.Item1.name);
						gameObject.transform.parent = value2.transform;
						gameObject.AddComponent<RenderPrefabRenderer>().m_Prefab = item2.Item1;
						Bounds bounds2 = RenderingUtils.ToBounds(item2.Item1.bounds);
						list3[index] += bounds2.extents.x * 1.5f;
						gameObject.transform.localPosition = new Vector3(list3[index], 0f, 0f);
						list3[index] += bounds2.extents.x * 1.5f + num2;
						AdjustXBounds(value2.transform, list3[index]);
					}
				}
				return;
			}
		}
		int num4 = 0;
		float num5 = 0f;
		float num6 = 0f;
		float num7 = 0f;
		foreach (var prefab in prefabs)
		{
			if ((ignoreLODs && prefab.prefab.name.Contains("_LOD")) || !(prefab.prefab is RenderPrefab renderPrefab))
			{
				continue;
			}
			GameObject gameObject2 = GameObject.Find(renderPrefab.name);
			if (gameObject2 == null)
			{
				gameObject2 = new GameObject(renderPrefab.name);
				gameObject2.AddComponent<RenderPrefabRenderer>().m_Prefab = renderPrefab;
				Bounds bounds3 = RenderingUtils.ToBounds(renderPrefab.bounds);
				num6 += bounds3.extents.x * 1.5f;
				gameObject2.transform.position = new Vector3(num6, 0f, num7);
				num6 += bounds3.extents.x * 1.5f;
				num5 = Mathf.Max(num5, bounds3.extents.z * 3f);
				num4++;
				if (num4 % 10 == 0)
				{
					num7 += num5;
					num5 = 0f;
					num6 = 0f;
				}
			}
			else
			{
				RenderPrefabRenderer component = gameObject2.GetComponent<RenderPrefabRenderer>();
				if (component != null)
				{
					component.m_Prefab = renderPrefab;
				}
			}
		}
		static string GetParent(string path)
		{
			int num8 = path.LastIndexOf('/');
			if (num8 < 0)
			{
				return path;
			}
			return path.Substring(0, num8);
		}
	}

	public static Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> GetTextureReferenceCount(IEnumerable<SurfaceAsset> surfaces, out int surfaceCount)
	{
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> dictionary = new Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>>();
		surfaceCount = 0;
		foreach (SurfaceAsset surface in surfaces)
		{
			using (surface)
			{
				surface.LoadProperties(useVT: false);
				foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture in surface.textures)
				{
					if (!dictionary.TryGetValue(texture.Value, out var value))
					{
						value = new List<SurfaceAsset>();
						dictionary.Add(texture.Value, value);
					}
					value.Add(surface);
				}
				surfaceCount++;
			}
		}
		return dictionary;
	}

	private static void ReportTextureReferenceStats(Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> textureReferencesMap, Report.ImportStep report)
	{
		int num = 0;
		int num2 = 0;
		int num3 = 0;
		foreach (Colossal.IO.AssetDatabase.TextureAsset key in textureReferencesMap.Keys)
		{
			if (textureReferencesMap[key].Count == 1)
			{
				num++;
			}
			else if (textureReferencesMap[key].Count == 2)
			{
				num2++;
			}
			else
			{
				num3++;
			}
		}
		report.AddMessage($"Singles: {num}");
		report.AddMessage($"Doubles: {num2}");
		report.AddMessage($"Multiple: {num3}");
	}

	private static int TestTextureSizesUniformity(SurfaceAsset asset, int tileSize, MaterialLibrary.MaterialDescription description)
	{
		int num = description.m_Stacks.Length;
		int[] array = new int[num];
		int[] array2 = new int[num];
		for (int i = 0; i < num; i++)
		{
			array[i] = -1;
		}
		foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture in asset.textures)
		{
			int stackConfigIndex = description.GetStackConfigIndex(texture.Key);
			if (stackConfigIndex != -1)
			{
				Colossal.IO.AssetDatabase.TextureAsset value = texture.Value;
				value.LoadData(0);
				if (value.width < tileSize)
				{
					return -1;
				}
				if (value.height < tileSize)
				{
					return -2;
				}
				if (array[stackConfigIndex] == -1)
				{
					array[stackConfigIndex] = value.width;
					array2[stackConfigIndex] = value.height;
				}
				else if (array[stackConfigIndex] != value.width || array2[stackConfigIndex] != value.height)
				{
					return -4;
				}
			}
		}
		return 0;
	}

	public static void ProcessSurfacesForVT(IEnumerable<SurfaceAsset> surfacesToConvert, IEnumerable<SurfaceAsset> surfaces, bool force, Report.ImportStep report)
	{
		int midMipsCount = 3;
		int tileSize = 512;
		int mipBias = 20;
		ConvertSurfacesToVT(surfacesToConvert, surfaces, writeVTSettings: false, tileSize, midMipsCount, mipBias, force, report);
		BuildMidMipsCache(surfaces, tileSize, midMipsCount, AssetDatabase.game);
		HideVTSourceTextures(surfacesToConvert);
		ResaveCache(report);
	}

	public static void ConvertSurfacesToVT(IEnumerable<SurfaceAsset> surfacesToConvert, IEnumerable<SurfaceAsset> allSurfaces, bool force, Report.ImportStep report)
	{
		int midMipsCount = 3;
		int tileSize = 512;
		int mipBias = 20;
		ConvertSurfacesToVT(surfacesToConvert, allSurfaces, writeVTSettings: false, tileSize, midMipsCount, mipBias, force, report);
	}

	public static void ConvertSurfacesToVT(IEnumerable<SurfaceAsset> surfacesToConvert, IEnumerable<SurfaceAsset> allSurfaces, bool writeVTSettings, int tileSize, int midMipsCount, int mipBias, bool force, Report.ImportStep report)
	{
		s_Progress.Set("VT post process - Converting surfaces", "Collecting references...", 0f);
		int surfaceCount;
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> textureReferenceCount = GetTextureReferenceCount(allSurfaces, out surfaceCount);
		ReportTextureReferenceStats(textureReferenceCount, report);
		MaterialLibrary materialLibrary = AssetDatabase.global.resources.materialLibrary;
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		int num = 0;
		foreach (SurfaceAsset item in surfacesToConvert)
		{
			s_Progress.Set("VT post process - Converting surfaces", "Processing " + item.name, (float)num++ / (float)surfaceCount);
			try
			{
				bool flag = item.IsVTMaterialFromHeader();
				if (!force && flag)
				{
					continue;
				}
				item.LoadProperties(useVT: false);
				MaterialLibrary.MaterialDescription materialDescription = materialLibrary.GetMaterialDescription(item.materialTemplateHash);
				if (materialDescription != null)
				{
					if (materialDescription.m_SupportsVT)
					{
						switch (TestTextureSizesUniformity(item, tileSize, materialDescription))
						{
						case 0:
						{
							if (!materialDescription.m_SupportsVT)
							{
								break;
							}
							int mipBias2 = (materialDescription.hasMipBiasOverride ? materialDescription.m_MipBiasOverride : mipBias);
							if (item.Save(mipBias2, force: true, saveTextures: true, vt: true, virtualTexturingConfig, textureReferenceCount, tileSize, midMipsCount))
							{
								log.InfoFormat("File {0} has been converted to VT", item);
							}
							goto end_IL_0089;
						}
						case -1:
							log.WarnFormat("File {0} cannot use VT because at least one of its textures width is smaller than the tileSize {1}", item, tileSize);
							break;
						case -2:
							log.WarnFormat("File {0} cannot use VT because at least one of its textures height is smaller than the tileSize {1}", item, tileSize);
							break;
						case -3:
							log.WarnFormat("File {0} cannot use VT because at least one texture uses a wrap mode that is not Clamp", item);
							break;
						case -4:
							log.WarnFormat("File {0} cannot use VT because its texture sizes is not uniform", item);
							break;
						case -5:
							log.WarnFormat("File {0} cannot use VT because some of its textures are null", item);
							break;
						}
					}
					else
					{
						log.WarnFormat("File {0} cannot use VT because its template {2} (Shader:{3}) from material hash {1} is not set to support VT", item, item.materialTemplateHash, materialDescription.m_Material.name, materialDescription.m_Material.shader.name);
					}
				}
				else
				{
					log.WarnFormat("File {0} cannot use VT because its material hash {1} is not mapped or not found", item, item.materialTemplateHash);
				}
				if (flag)
				{
					item.Save(0, force: true, saveTextures: false);
					log.InfoFormat("File {0} has been unconverted from VT", item);
				}
				end_IL_0089:;
			}
			catch (Exception exception)
			{
				log.ErrorFormat(exception, "Error occured with {0}", item);
				throw;
			}
			finally
			{
				item.Unload();
			}
		}
		if (writeVTSettings)
		{
			using (VTSettingsAsset vTSettingsAsset = AssetDatabase.game.AddAsset<VTSettingsAsset>(AssetDataPath.Create(EnvPath.kVTSubPath, "VT")))
			{
				vTSettingsAsset.Save(mipBias, tileSize, midMipsCount);
			}
		}
	}

	private static void ResaveCache(Report.ImportStep report)
	{
		s_Progress.Set("VT post process", "Resaving asset cache", 100f);
		report.AddMessage(AssetDatabase.global.ResaveCache().Result);
	}

	public static void HideVTSourceTextures(IEnumerable<SurfaceAsset> surfaces)
	{
		s_Progress.Set("VT post process - Hiding converted textures", "", 0f);
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> dictionary = new Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>>();
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> dictionary2 = new Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>>();
		foreach (SurfaceAsset surface in surfaces)
		{
			surface.LoadProperties(useVT: true);
			if (surface.isVTMaterial)
			{
				foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture in surface.textures)
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
				foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture2 in surface.textures)
				{
					AddReferenceTo(dictionary2, texture2.Value, surface);
				}
			}
			surface.Unload();
		}
		List<Colossal.IO.AssetDatabase.TextureAsset> list = AssetDatabase.global.GetAssets(default(SearchFilter<Colossal.IO.AssetDatabase.TextureAsset>)).ToList();
		for (int i = 0; i < list.Count; i++)
		{
			Colossal.IO.AssetDatabase.TextureAsset textureAsset = list[i];
			s_Progress.Set("VT post process - Hiding", "Processing " + textureAsset.name, (float)i / (float)dictionary.Count);
			if (dictionary.ContainsKey(textureAsset))
			{
				if (dictionary2.ContainsKey(textureAsset))
				{
					log.WarnFormat("Texture {0} is referenced {1} times by VT materials and {2} times by non VT materials. It will be duplicated on disk.", textureAsset, dictionary[textureAsset].Count, dictionary2[textureAsset].Count);
					log.InfoFormat("Detail for {0}:\nvt: {1}\nnon vt: {2}", textureAsset, string.Join(", ", dictionary[textureAsset]), string.Join(", ", dictionary2[textureAsset]));
				}
				else
				{
					log.InfoFormat($"Hiding {textureAsset}");
				}
			}
		}
		static void AddReferenceTo(Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, SurfaceAsset surface)
		{
			if (!references.TryGetValue(texture, out var value))
			{
				value = new List<SurfaceAsset>();
				references.Add(texture, value);
			}
			value.Add(surface);
		}
	}

	public static void BuildMidMipsCache(IEnumerable<SurfaceAsset> surfaces, int tileSize, int midMipsCount, ILocalAssetDatabase database)
	{
		s_Progress.Set("VT post process - Rebuilding mip cache", "", 0f);
		if (midMipsCount < 0)
		{
			throw new Exception("Nb mid mip levels can't be negative");
		}
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		int nbConfigStacks = virtualTexturingConfig.stackDatas.Length;
		MaterialLibrary materialLibrary = AssetDatabase.global.resources.materialLibrary;
		AtlasMaterialsGrouper atlasMaterialsGrouper = new AtlasMaterialsGrouper(nbConfigStacks, tileSize, midMipsCount);
		List<SurfaceAsset> list = surfaces.ToList();
		Dictionary<Colossal.Hash128, NativeArray<byte>> dictionary = new Dictionary<Colossal.Hash128, NativeArray<byte>>();
		Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] array = new Dictionary<Colossal.Hash128, Colossal.Hash128[]>[2];
		for (int i = 0; i < array.Length; i++)
		{
			array[i] = new Dictionary<Colossal.Hash128, Colossal.Hash128[]>();
		}
		for (int j = 0; j < list.Count; j++)
		{
			using SurfaceAsset surfaceAsset = list[j];
			s_Progress.Set("VT post process - Rebuilding mip cache", "Processing " + surfaceAsset.name, (float)j / (float)list.Count);
			surfaceAsset.LoadProperties(useVT: true);
			if (!surfaceAsset.isVTMaterial)
			{
				continue;
			}
			MaterialLibrary.MaterialDescription materialDescription = materialLibrary.GetMaterialDescription(surfaceAsset.materialTemplateHash);
			long[] textureHash = new long[materialDescription.m_Stacks.Length];
			for (int k = 0; k < materialDescription.m_Stacks.Length; k++)
			{
				Colossal.Hash128[] value = new Colossal.Hash128[4];
				array[k][surfaceAsset.id] = value;
				surfaceAsset.AddMidMipTexturesDataToDictionnary(k, midMipsCount, tileSize, materialDescription, dictionary);
			}
			int multiStackLayersMask = surfaceAsset.ComputeVTLayersMask(materialDescription, array, textureHash);
			for (int l = 0; l < surfaceAsset.stackCount; l++)
			{
				AtlassedSize unbiasedStackTextureSize = surfaceAsset.GetUnbiasedStackTextureSize(l);
				if (unbiasedStackTextureSize.x >= 0)
				{
					atlasMaterialsGrouper.Add(l, unbiasedStackTextureSize, multiStackLayersMask, surfaceAsset, textureHash, materialDescription.m_MipBiasOverride);
				}
			}
		}
		atlasMaterialsGrouper.ResolveDuplicates(array, 2);
		atlasMaterialsGrouper.GroupEntries(virtualTexturingConfig, dictionary, array);
		string assetName = AtlasMaterialsGrouper.GetAssetName(tileSize, midMipsCount);
		using (BinaryWriter bw = new BinaryWriter(database.AddAsset<MidMipCacheAsset>(AssetDataPath.Create("StreamingData~", assetName)).GetWriteStream()))
		{
			atlasMaterialsGrouper.Write(bw);
		}
		foreach (NativeArray<byte> value2 in dictionary.Values)
		{
			value2.Dispose();
		}
		atlasMaterialsGrouper.Dispose();
	}

	public static async Task ApplyVTMipBias(IAssetDatabase database, int mipBias, int tileSize, int midMipCount, string folder)
	{
		if (s_MainThreadDispatcher == null)
		{
			s_MainThreadDispatcher = new MainThreadDispatcher();
		}
		if (mipBias < 0)
		{
			throw new Exception("Mip bias cannot be smaller than zero in that context!");
		}
		bool flag = true;
		string text = null;
		if (database is ILocalAssetDatabase { dataSource: FileSystemDataSource dataSource })
		{
			text = dataSource.rootPath + "/StreamingData~";
			if (database != AssetDatabase.game)
			{
				flag = false;
			}
		}
		if (text == null)
		{
			throw new ArgumentException("Master VT file path is null.");
		}
		ILocalAssetDatabase vtMipXDatabase = AssetDatabase.GetTransient(0L, text + "/." + folder);
		VirtualTexturingConfig virtualTexturingConfig = Resources.Load<VirtualTexturingConfig>("VirtualTexturingConfig");
		ParallelOptions opts = new ParallelOptions
		{
			MaxDegreeOfParallelism = ((!useParallelImport) ? 1 : Environment.ProcessorCount)
		};
		int total = 0;
		Task importTask = Task.Run(delegate
		{
			List<VTTextureAsset> texture2DPreProcessedAssets = database.GetAssets(default(SearchFilter<VTTextureAsset>)).ToList();
			List<SurfaceAsset> list = database.GetAssets(default(SearchFilter<SurfaceAsset>)).ToList();
			int assetsToProcess = texture2DPreProcessedAssets.Count + list.Count;
			for (int i = 0; i < list.Count; i++)
			{
				try
				{
					using (SurfaceAsset surfaceAsset = list[i])
					{
						s_Progress.Set("VT post process - Apply Surface MipBias", "Applying Mip Bias to " + surfaceAsset.name, (float)total / (float)assetsToProcess);
						log.InfoFormat("Processing {0} ({1}/{2})", surfaceAsset, total + 1, assetsToProcess);
						if (!s_Progress.shouldCancel)
						{
							surfaceAsset.LoadProperties(useVT: false);
							if (surfaceAsset.isVTMaterial && surfaceAsset.hasVTSurfaceAsset)
							{
								surfaceAsset.UpdateMipBias(vtMipXDatabase, mipBias, virtualTexturingConfig, tileSize, midMipCount);
							}
							goto IL_0127;
						}
					}
					goto end_IL_0067;
					IL_0127:
					Interlocked.Increment(ref total);
					continue;
					end_IL_0067:;
				}
				catch (Exception exception)
				{
					log.ErrorFormat(exception, "Error with {0}", list[i]);
					continue;
				}
				break;
			}
			Parallel.ForEach(texture2DPreProcessedAssets, opts, delegate(VTTextureAsset texture2DPreProcessedAsset, ParallelLoopState state, long index)
			{
				try
				{
					s_Progress.Set("VT post process - Apply Texture MipBias", "Applying Mip Bias to " + texture2DPreProcessedAsset.name, (float)total / (float)assetsToProcess);
					log.InfoFormat("Processing {0} ({1}/{2})", texture2DPreProcessedAsset, total + 1, assetsToProcess);
					if (s_Progress.shouldCancel)
					{
						state.Stop();
					}
					texture2DPreProcessedAsset.LoadHeader();
					using (Colossal.IO.AssetDatabase.TextureAsset textureAsset = texture2DPreProcessedAsset.textureAsset)
					{
						textureAsset.LoadData(0);
						if (textureAsset.width < tileSize || textureAsset.height < tileSize)
						{
							log.ErrorFormat("That texture [{0}] dimension is too small to be supported by the VT system textureSize: {1}x{2} VT tileSize: {3}", textureAsset.name, textureAsset.width, textureAsset.height, tileSize);
						}
						using VTTextureAsset vTTextureAsset = vtMipXDatabase.AddAsset<VTTextureAsset>(texture2DPreProcessedAsset.name, texture2DPreProcessedAsset.id);
						vTTextureAsset.Save(mipBias, textureAsset, tileSize, midMipCount, virtualTexturingConfig);
					}
					Interlocked.Increment(ref total);
				}
				catch (Exception exception2)
				{
					log.ErrorFormat(exception2, "Error with {0}", texture2DPreProcessedAssets);
				}
			});
		});
		if (flag)
		{
			using VTSettingsAsset vTSettingsAsset = vtMipXDatabase.AddAsset<VTSettingsAsset>("VT");
			vTSettingsAsset.Save(mipBias, tileSize, midMipCount);
		}
		Report report = new Report();
		await ExecuteMainThreadQueue(importTask, report);
	}
}
```

- `private static GetSkinningInfo(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]& bones, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Boolean`  

```csharp
private static bool GetSkinningInfo(ModelImporter.Model model, out ModelImporter.Model.BoneInfo[] bones, Report.Prefab report)
	{
		bones = model.bones;
		if (model.HasAttribute(VertexAttribute.BlendIndices))
		{
			if (model.rootBoneIndex == -1)
			{
				report.AddWarning(model.name + " is missing root bone");
				return false;
			}
			if (model.bones == null)
			{
				report.AddWarning(model.name + " is missing bind poses");
				return false;
			}
			if (!model.HasAttribute(VertexAttribute.BlendWeight) && model.GetAttributeData(VertexAttribute.BlendIndices).dimension != 1)
			{
				report.AddWarning(model.name + " has BlendIndices but no BlendWeight. Assuming rigid skinning..");
				return false;
			}
			return true;
		}
		if (model.HasAttribute(VertexAttribute.BlendWeight))
		{
			report.AddWarning(model.name + " has BlendWeight but is missing BlendIndices");
		}
		return false;
	}
```

- `public static GetTextureReferenceCount(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32& surfaceCount) : System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>>`  

```csharp
public static Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> GetTextureReferenceCount(IEnumerable<SurfaceAsset> surfaces, out int surfaceCount)
	{
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> dictionary = new Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>>();
		surfaceCount = 0;
		foreach (SurfaceAsset surface in surfaces)
		{
			using (surface)
			{
				surface.LoadProperties(useVT: false);
				foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture in surface.textures)
				{
					if (!dictionary.TryGetValue(texture.Value, out var value))
					{
						value = new List<SurfaceAsset>();
						dictionary.Add(texture.Value, value);
					}
					value.Add(surface);
				}
				surfaceCount++;
			}
		}
		return dictionary;
	}
```

- `private static GetUniqueString(System.String input, System.Int32 currentIndex, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] array) : System.String`  

```csharp
private static string GetUniqueString(string input, int currentIndex, ProceduralAnimationProperties.BoneInfo[] array)
	{
		int num = 0;
		for (int i = 0; i < currentIndex; i++)
		{
			if (array[i].name.StartsWith(input))
			{
				num++;
			}
		}
		if (num == 0)
		{
			return input;
		}
		return $"{input} {num}";
	}
```

- `public static HideVTSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces) : System.Void`  

```csharp
public static void HideVTSourceTextures(IEnumerable<SurfaceAsset> surfaces)
	{
		s_Progress.Set("VT post process - Hiding converted textures", "", 0f);
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> dictionary = new Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>>();
		Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> dictionary2 = new Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>>();
		foreach (SurfaceAsset surface in surfaces)
		{
			surface.LoadProperties(useVT: true);
			if (surface.isVTMaterial)
			{
				foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture in surface.textures)
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
				foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture2 in surface.textures)
				{
					AddReferenceTo(dictionary2, texture2.Value, surface);
				}
			}
			surface.Unload();
		}
		List<Colossal.IO.AssetDatabase.TextureAsset> list = AssetDatabase.global.GetAssets(default(SearchFilter<Colossal.IO.AssetDatabase.TextureAsset>)).ToList();
		for (int i = 0; i < list.Count; i++)
		{
			Colossal.IO.AssetDatabase.TextureAsset textureAsset = list[i];
			s_Progress.Set("VT post process - Hiding", "Processing " + textureAsset.name, (float)i / (float)dictionary.Count);
			if (dictionary.ContainsKey(textureAsset))
			{
				if (dictionary2.ContainsKey(textureAsset))
				{
					log.WarnFormat("Texture {0} is referenced {1} times by VT materials and {2} times by non VT materials. It will be duplicated on disk.", textureAsset, dictionary[textureAsset].Count, dictionary2[textureAsset].Count);
					log.InfoFormat("Detail for {0}:\nvt: {1}\nnon vt: {2}", textureAsset, string.Join(", ", dictionary[textureAsset]), string.Join(", ", dictionary2[textureAsset]));
				}
				else
				{
					log.InfoFormat($"Hiding {textureAsset}");
				}
			}
		}
		static void AddReferenceTo(Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, SurfaceAsset surface)
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

- `private static ImportAssetGroup(System.String projectRootPath, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.Collections.Generic.List`1[[System.Collections.Generic.List`1[[Colossal.AssetPipeline.LOD, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& lods, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, Colossal.AssetPipeline.Diagnostic.Report report, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport) : System.Boolean`  

```csharp
private static bool ImportAssetGroup(string projectRootPath, string relativeRootPath, SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset> assetGroup, out List<List<Colossal.AssetPipeline.LOD>> lods, out Action<string, ImportMode, Report, HashSet<SurfaceAsset>, IPrefabFactory> postImportOperations, Report report, Report.Asset assetReport)
	{
		lods = null;
		postImportOperations = null;
		using (s_ProfImportAssetGroup.Auto())
		{
			try
			{
				log.Info("Start processing " + assetGroup);
				using (Report.ImportStep importStep = report.AddImportStep("Import asset group"))
				{
					Colossal.AssetPipeline.Settings settings = ImportSettings(assetGroup, (step: importStep, asset: assetReport));
					SourceAssetCollector.AssetGroup<IAsset> assetGroup2 = CreateAssetGroupFromSettings(projectRootPath, settings, assetGroup, assetReport);
					foreach (IAsset item in assetGroup2)
					{
						log.Verbose($"   {item}");
					}
					if (settings.pipeline == Pipeline.Default)
					{
						ImportTextures(settings, relativeRootPath, assetGroup2, (step: importStep, asset: assetReport));
						ImportModels(settings, relativeRootPath, assetGroup2, (step: importStep, asset: assetReport));
						CreateGeometriesAndSurfaces(settings, relativeRootPath, assetGroup2, out postImportOperations, (parent: report, asset: assetReport));
					}
					else if (settings.pipeline == Pipeline.Characters)
					{
						ImportDidimo(settings, assetGroup2, (step: importStep, asset: assetReport));
						CreateDidimoAssets(settings, relativeRootPath, assetGroup2, out postImportOperations, (parent: report, step: importStep, asset: assetReport));
					}
				}
				return true;
			}
			catch (Exception exception)
			{
				log.ErrorFormat(exception, "Error processing {0}.. Skipped!", assetGroup.ToString());
				lods = null;
				return false;
			}
		}
	}
```

- `private static ImportDidimo(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  

```csharp
private static System.Void ImportDidimo(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `private static ImportModels(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  

```csharp
private static System.Void ImportModels(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `public static ImportPath(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths, Colossal.AssetPipeline.ImportMode importMode, System.Boolean convertToVT, System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback = null, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Threading.Tasks.Task`  

```csharp
public static async Task ImportPath(string projectRootPath, IEnumerable<string> relativePaths, ImportMode importMode, bool convertToVT, Func<string, string, float, bool> progressCallback = null, IPrefabFactory prefabFactory = null)
	{
		if (targetDatabase == null)
		{
			throw new Exception("targetDatabase must be set");
		}
		if (s_MainThreadDispatcher == null)
		{
			s_MainThreadDispatcher = new MainThreadDispatcher();
		}
		using (s_ImportPath.Auto())
		{
			Report report = new Report();
			int failures = 0;
			int total = 0;
			using (PerformanceCounter perf = PerformanceCounter.Start(delegate(TimeSpan t)
			{
				log.Info(string.Format("Completed {0} asset groups import in {1:F3}s. Errors {2}. {3}", total, t.TotalSeconds, failures, s_Progress.shouldCancel ? "(Canceled)" : ""));
			}))
			{
				using (Report.ImportStep report2 = report.AddImportStep("Cache importers & post processors"))
				{
					ImporterCache.CacheSupportedExtensions(report2);
					PostProcessorCache.CachePostProcessors(report2);
				}
				SetReportCallback(progressCallback);
				AddSupportedThemes(projectRootPath);
				SourceAssetCollector assetCollector;
				using (report.AddImportStep("Collect source assets"))
				{
					s_Progress.Set("Importing assets", "Collecting files...", 0f);
					assetCollector = new SourceAssetCollector(projectRootPath, relativePaths);
				}
				ParallelOptions opts = new ParallelOptions
				{
					MaxDegreeOfParallelism = ((!useParallelImport) ? 1 : Environment.ProcessorCount)
				};
				HashSet<SurfaceAsset> VTMaterials = new HashSet<SurfaceAsset>();
				int parallelCount = 0;
				await ExecuteMainThreadQueue(Task.Run(() => Parallel.ForEach(assetCollector, opts, delegate(SourceAssetCollector.AssetGroup<SourceAssetCollector.Asset> asset, ParallelLoopState state, long index)
				{
					string relativeRootPath = MakeRelativePath(asset.rootPath, projectRootPath);
					Report.Asset assetReport = report.AddAsset(asset.name);
					Interlocked.Increment(ref parallelCount);
					s_Progress.Set($"Importing {parallelCount} assets ({total + 1}/{assetCollector.count})", "Importing textures and meshes for " + asset.name, (float)total / (float)assetCollector.count);
					if (s_Progress.shouldCancel)
					{
						state.Stop();
					}
					if (ImportAssetGroup(projectRootPath, relativeRootPath, asset, out var _, out var postImportOperations, report, assetReport))
					{
						s_MainThreadDispatcher.Dispatch(delegate
						{
							postImportOperations?.Invoke(relativeRootPath, importMode, report, VTMaterials, prefabFactory);
						});
					}
					else
					{
						Interlocked.Increment(ref failures);
					}
					Interlocked.Increment(ref total);
					Interlocked.Decrement(ref parallelCount);
					s_Progress.Set($"Importing {parallelCount} assets ({total + 1}/{assetCollector.count})", "Completed textures and meshes for " + asset.name, (float)total / (float)assetCollector.count);
				})), report);
				if (convertToVT)
				{
					using Report.ImportStep report3 = report.AddImportStep("Convert materials to VT");
					ProcessSurfacesForVT(VTMaterials, null, (importMode & ImportMode.Forced) == ImportMode.Forced, report3);
				}
				s_Progress.Set("Completed", "", 1f);
				report.totalTime = perf.result;
			}
			report.Log(log);
			s_MainThreadDispatcher = null;
		}
	}
```

- `private static ImportSettings(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : Colossal.AssetPipeline.Settings`  

```csharp
private static Colossal.AssetPipeline.Settings ImportSettings(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `private static ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  

```csharp
private static System.Void ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `private static ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<Colossal.AssetPipeline.TextureAsset, System.Boolean> predicate, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  

```csharp
private static System.Void ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<Colossal.AssetPipeline.TextureAsset, System.Boolean> predicate, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report);
```

- `public static InstantiateRenderPrefabs<T>(System.Collections.Generic.IEnumerable<System.ValueTuple<T, System.String>> prefabs, System.Boolean smartInstantiate, System.Boolean ignoreLODs) : System.Void`  

```csharp
public static System.Void InstantiateRenderPrefabs<T>(System.Collections.Generic.IEnumerable<System.ValueTuple<T, System.String>> prefabs, System.Boolean smartInstantiate, System.Boolean ignoreLODs);
```

- `private static IsArtRootPath(System.String rootPathName, System.String path, System.String& artProjectPath, System.String& artProjectRelativePath) : System.Boolean`  

```csharp
public static bool IsArtRootPath(string rootPathName, string[] paths, out string artProjectPath, out List<string> artProjectRelativePaths)
	{
		artProjectPath = null;
		artProjectRelativePaths = new List<string>(paths.Length);
		foreach (string text in paths)
		{
			if (!string.IsNullOrEmpty(text))
			{
				if (!IsArtRootPath(rootPathName, text, out var artProjectPath2, out var artProjectRelativePath))
				{
					return false;
				}
				if (artProjectPath != null && artProjectPath2 != artProjectPath)
				{
					throw new Exception("Root project path does not match. Previous: " + artProjectPath + " Current: " + artProjectPath2);
				}
				artProjectPath = artProjectPath2;
				artProjectRelativePaths.Add(artProjectRelativePath);
			}
		}
		return true;
	}
```

- `public static IsArtRootPath(System.String rootPathName, System.String[] paths, System.String& artProjectPath, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& artProjectRelativePaths) : System.Boolean`  

```csharp
public static bool IsArtRootPath(string rootPathName, string[] paths, out string artProjectPath, out List<string> artProjectRelativePaths)
	{
		artProjectPath = null;
		artProjectRelativePaths = new List<string>(paths.Length);
		foreach (string text in paths)
		{
			if (!string.IsNullOrEmpty(text))
			{
				if (!IsArtRootPath(rootPathName, text, out var artProjectPath2, out var artProjectRelativePath))
				{
					return false;
				}
				if (artProjectPath != null && artProjectPath2 != artProjectPath)
				{
					throw new Exception("Root project path does not match. Previous: " + artProjectPath + " Current: " + artProjectPath2);
				}
				artProjectPath = artProjectPath2;
				artProjectRelativePaths.Add(artProjectRelativePath);
			}
		}
		return true;
	}
```

- `private static IsLODsValid(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets) : System.Boolean`  

```csharp
private static bool IsLODsValid(IReadOnlyList<List<Colossal.AssetPipeline.LOD>> assets)
	{
		if (assets == null || assets.Count == 0)
		{
			return false;
		}
		foreach (List<Colossal.AssetPipeline.LOD> asset in assets)
		{
			foreach (Colossal.AssetPipeline.LOD item in asset)
			{
				if (item.geometry == null && (item.surfaces == null || item.surfaces.Length == 0))
				{
					return false;
				}
				if (item.geometry != null && !item.geometry.isValid)
				{
					return false;
				}
				if (item.surfaces != null && (item.surfaces.Length == 0 || item.surfaces.Any((Surface surface) => !surface.isValid)))
				{
					return false;
				}
			}
		}
		return true;
	}
```

- `private static MakeRelativePath(System.String path, System.String rootPath) : System.String`  

```csharp
private static string MakeRelativePath(string path, string rootPath)
	{
		if (path.IndexOf(rootPath) == 0)
		{
			return path.Substring(rootPath.Length + 1);
		}
		throw new FormatException(path + " is not relative to " + rootPath);
	}
```

- `public static ProcessSurfacesForVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
public static void ProcessSurfacesForVT(IEnumerable<SurfaceAsset> surfacesToConvert, IEnumerable<SurfaceAsset> surfaces, bool force, Report.ImportStep report)
	{
		int midMipsCount = 3;
		int tileSize = 512;
		int mipBias = 20;
		ConvertSurfacesToVT(surfacesToConvert, surfaces, writeVTSettings: false, tileSize, midMipsCount, mipBias, force, report);
		BuildMidMipsCache(surfaces, tileSize, midMipsCount, AssetDatabase.game);
		HideVTSourceTextures(surfacesToConvert);
		ResaveCache(report);
	}
```

- `private static ReportTextureReferenceStats(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
private static void ReportTextureReferenceStats(Dictionary<Colossal.IO.AssetDatabase.TextureAsset, List<SurfaceAsset>> textureReferencesMap, Report.ImportStep report)
	{
		int num = 0;
		int num2 = 0;
		int num3 = 0;
		foreach (Colossal.IO.AssetDatabase.TextureAsset key in textureReferencesMap.Keys)
		{
			if (textureReferencesMap[key].Count == 1)
			{
				num++;
			}
			else if (textureReferencesMap[key].Count == 2)
			{
				num2++;
			}
			else
			{
				num3++;
			}
		}
		report.AddMessage($"Singles: {num}");
		report.AddMessage($"Doubles: {num2}");
		report.AddMessage($"Multiple: {num3}");
	}
```

- `private static ResaveCache(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
private static void ResaveCache(Report.ImportStep report)
	{
		s_Progress.Set("VT post process", "Resaving asset cache", 100f);
		report.AddMessage(AssetDatabase.global.ResaveCache().Result);
	}
```

- `private static ResolveRelativePath(System.String projectRootPath, System.String target, System.String to) : System.String`  

```csharp
private static string ResolveRelativePath(string projectRootPath, string target, string to)
	{
		if (target.StartsWith('/'))
		{
			return Path.GetFullPath(Path.Combine(projectRootPath, target.Substring(1)));
		}
		return Path.GetFullPath(Path.Combine(to, target));
	}
```

- `public static SetReportCallback(System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback) : System.Void`  

```csharp
public static void SetReportCallback(Func<string, string, float, bool> progressCallback)
	{
		s_Progress.Reset(progressCallback);
	}
```

- `private static SetupComponents(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  

```csharp
private static void SetupComponents(Colossal.AssetPipeline.Settings settings, RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Report.Prefab report)
	{
		if (lod.level == 0)
		{
			SetupEmissiveComponent(settings, meshPrefab, lod, report);
			if (settings.useProceduralAnimation)
			{
				SetupProceduralAnimationComponent(settings, meshPrefab, lod, report);
			}
		}
	}
```

- `private static SetupEmissiveComponent(Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod) : System.Void`  

```csharp
private static void SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Report.Prefab report)
	{
		List<EmissiveProperties.MultiLightMapping> multiLightProps = new List<EmissiveProperties.MultiLightMapping>();
		List<EmissiveProperties.SingleLightMapping> list = new List<EmissiveProperties.SingleLightMapping>();
		int num = 0;
		Surface[] surfaces = lod.surfaces;
		foreach (Surface surface in surfaces)
		{
			if (surface.emissiveLayers.Count == 0)
			{
				if (surface.HasProperty("_EmissiveColorMap"))
				{
					list.Add(new EmissiveProperties.SingleLightMapping
					{
						purpose = (surface.name.Contains("Neon") ? EmissiveProperties.Purpose.NeonSign : EmissiveProperties.Purpose.DecorativeLight),
						intensity = 5f,
						materialId = num++
					});
				}
				continue;
			}
			foreach (Surface.EmissiveLayer emissiveLayer in surface.emissiveLayers)
			{
				multiLightProps.Add(new EmissiveProperties.MultiLightMapping
				{
					intensity = emissiveLayer.intensity,
					luminance = emissiveLayer.luminance,
					color = emissiveLayer.color,
					layerId = emissiveLayer.layerId,
					purpose = EmissiveProperties.Purpose.None,
					colorOff = Color.black,
					animationIndex = -1,
					responseTime = 0f
				});
			}
		}
		if (list.Count > 0)
		{
			if (!meshPrefab.TryGet<EmissiveProperties>(out var component))
			{
				component = meshPrefab.AddComponent<EmissiveProperties>();
				component.m_SingleLights = list;
				report.AddComponent(component.ToString()).AddMessage($"Missing EmissiveProperties. {list.Count} single lights found. Please set up correctly...");
				log.WarnFormat(meshPrefab, "Mesh prefab {1} was missing EmissiveProperties. {0} single lights found. Please set up correctly...", list.Count, meshPrefab.name);
			}
			else if (component.m_SingleLights.Count != list.Count)
			{
				report.AddComponent(component.ToString()).AddMessage($"EmissiveProperties already added but the asset contains a different lightCount than set. Expected: {list.Count} Found: {component.m_SingleLights.Count}. Please set up correctly...");
				log.WarnFormat(meshPrefab, "Mesh prefab {2} has an EmissiveProperties but the asset contains a different lightCount than set. Expected: {0} Found: {1}. Please set up correctly...", list.Count, component.m_SingleLights.Count, meshPrefab.name);
			}
		}
		if (multiLightProps.Count <= 0)
		{
			return;
		}
		if (!meshPrefab.TryGet<EmissiveProperties>(out var component2))
		{
			component2 = meshPrefab.AddComponent<EmissiveProperties>();
			component2.m_MultiLights = multiLightProps;
			report.AddComponent(component2.ToString()).AddMessage($"Missing EmissiveProperties. {multiLightProps.Count} light layers found. Please set up correctly...");
			log.WarnFormat(meshPrefab, "Mesh prefab {1} was missing EmissiveProperties. {0} light layers found. Please set up correctly...", multiLightProps.Count, meshPrefab.name);
			return;
		}
		if (component2.m_MultiLights.Count != multiLightProps.Count)
		{
			report.AddComponent(component2.ToString()).AddWarning($"EmissiveProperties already added but the asset contains a different light layer count than set. Expected: {list.Count} Found: {component2.m_MultiLights.Count}. Please set up correctly...");
			log.WarnFormat(meshPrefab, "Mesh prefab {2} has an EmissiveProperties but the asset contains a different light layer count than set. Expected: {0} Found: {1}. Please set up correctly...", list.Count, component2.m_MultiLights.Count, meshPrefab.name);
		}
		int i2;
		int i;
		for (i2 = 0; i2 < multiLightProps.Count; i2 = i)
		{
			EmissiveProperties.MultiLightMapping multiLightMapping = component2.m_MultiLights.Find((EmissiveProperties.MultiLightMapping x) => x.layerId == multiLightProps[i2].layerId);
			if (multiLightMapping != null)
			{
				multiLightProps[i2].purpose = multiLightMapping.purpose;
				multiLightProps[i2].color = multiLightMapping.color;
				multiLightProps[i2].colorOff = multiLightMapping.colorOff;
				multiLightProps[i2].animationIndex = multiLightMapping.animationIndex;
				multiLightProps[i2].responseTime = multiLightMapping.responseTime;
			}
			i = i2 + 1;
		}
		component2.m_MultiLights = multiLightProps;
	}
```

- `private static SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  

```csharp
private static void SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Report.Prefab report)
	{
		List<EmissiveProperties.MultiLightMapping> multiLightProps = new List<EmissiveProperties.MultiLightMapping>();
		List<EmissiveProperties.SingleLightMapping> list = new List<EmissiveProperties.SingleLightMapping>();
		int num = 0;
		Surface[] surfaces = lod.surfaces;
		foreach (Surface surface in surfaces)
		{
			if (surface.emissiveLayers.Count == 0)
			{
				if (surface.HasProperty("_EmissiveColorMap"))
				{
					list.Add(new EmissiveProperties.SingleLightMapping
					{
						purpose = (surface.name.Contains("Neon") ? EmissiveProperties.Purpose.NeonSign : EmissiveProperties.Purpose.DecorativeLight),
						intensity = 5f,
						materialId = num++
					});
				}
				continue;
			}
			foreach (Surface.EmissiveLayer emissiveLayer in surface.emissiveLayers)
			{
				multiLightProps.Add(new EmissiveProperties.MultiLightMapping
				{
					intensity = emissiveLayer.intensity,
					luminance = emissiveLayer.luminance,
					color = emissiveLayer.color,
					layerId = emissiveLayer.layerId,
					purpose = EmissiveProperties.Purpose.None,
					colorOff = Color.black,
					animationIndex = -1,
					responseTime = 0f
				});
			}
		}
		if (list.Count > 0)
		{
			if (!meshPrefab.TryGet<EmissiveProperties>(out var component))
			{
				component = meshPrefab.AddComponent<EmissiveProperties>();
				component.m_SingleLights = list;
				report.AddComponent(component.ToString()).AddMessage($"Missing EmissiveProperties. {list.Count} single lights found. Please set up correctly...");
				log.WarnFormat(meshPrefab, "Mesh prefab {1} was missing EmissiveProperties. {0} single lights found. Please set up correctly...", list.Count, meshPrefab.name);
			}
			else if (component.m_SingleLights.Count != list.Count)
			{
				report.AddComponent(component.ToString()).AddMessage($"EmissiveProperties already added but the asset contains a different lightCount than set. Expected: {list.Count} Found: {component.m_SingleLights.Count}. Please set up correctly...");
				log.WarnFormat(meshPrefab, "Mesh prefab {2} has an EmissiveProperties but the asset contains a different lightCount than set. Expected: {0} Found: {1}. Please set up correctly...", list.Count, component.m_SingleLights.Count, meshPrefab.name);
			}
		}
		if (multiLightProps.Count <= 0)
		{
			return;
		}
		if (!meshPrefab.TryGet<EmissiveProperties>(out var component2))
		{
			component2 = meshPrefab.AddComponent<EmissiveProperties>();
			component2.m_MultiLights = multiLightProps;
			report.AddComponent(component2.ToString()).AddMessage($"Missing EmissiveProperties. {multiLightProps.Count} light layers found. Please set up correctly...");
			log.WarnFormat(meshPrefab, "Mesh prefab {1} was missing EmissiveProperties. {0} light layers found. Please set up correctly...", multiLightProps.Count, meshPrefab.name);
			return;
		}
		if (component2.m_MultiLights.Count != multiLightProps.Count)
		{
			report.AddComponent(component2.ToString()).AddWarning($"EmissiveProperties already added but the asset contains a different light layer count than set. Expected: {list.Count} Found: {component2.m_MultiLights.Count}. Please set up correctly...");
			log.WarnFormat(meshPrefab, "Mesh prefab {2} has an EmissiveProperties but the asset contains a different light layer count than set. Expected: {0} Found: {1}. Please set up correctly...", list.Count, component2.m_MultiLights.Count, meshPrefab.name);
		}
		int i2;
		int i;
		for (i2 = 0; i2 < multiLightProps.Count; i2 = i)
		{
			EmissiveProperties.MultiLightMapping multiLightMapping = component2.m_MultiLights.Find((EmissiveProperties.MultiLightMapping x) => x.layerId == multiLightProps[i2].layerId);
			if (multiLightMapping != null)
			{
				multiLightProps[i2].purpose = multiLightMapping.purpose;
				multiLightProps[i2].color = multiLightMapping.color;
				multiLightProps[i2].colorOff = multiLightMapping.colorOff;
				multiLightProps[i2].animationIndex = multiLightMapping.animationIndex;
				multiLightProps[i2].responseTime = multiLightMapping.responseTime;
			}
			i = i2 + 1;
		}
		component2.m_MultiLights = multiLightProps;
	}
```

- `private static SetupLODs(Colossal.AssetPipeline.Settings settings, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> meshPrefabs) : System.Void`  

```csharp
private static System.Void SetupLODs(Colossal.AssetPipeline.Settings settings, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> meshPrefabs);
```

- `private static SetupProceduralAnimationComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  

```csharp
private static void SetupProceduralAnimationComponent(Colossal.AssetPipeline.Settings settings, RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Report.Prefab report)
	{
		if (lod.geometry == null || !GetSkinningInfo(lod.geometry.models[0], out var bones, report))
		{
			return;
		}
		if (!meshPrefab.TryGet<ProceduralAnimationProperties>(out var component))
		{
			log.WarnFormat(meshPrefab, "Mesh prefab {0} was missing ProceduralAnimationProperties. Please set up correctly...", meshPrefab.name);
			component = meshPrefab.AddComponent<ProceduralAnimationProperties>();
			report.AddComponent(component.ToString());
		}
		ProceduralAnimationProperties.BoneInfo[] bones2 = new ProceduralAnimationProperties.BoneInfo[bones.Length];
		int i = 0;
		while (i < bones.Length)
		{
			bones2[i] = new ProceduralAnimationProperties.BoneInfo
			{
				name = GetUniqueString(bones[i].name, i, bones2),
				position = bones[i].localPosition,
				rotation = bones[i].localRotation,
				scale = bones[i].localScale,
				parentId = bones[i].parentIndex,
				bindPose = bones[i].bindPose
			};
			if (component.m_Bones != null)
			{
				ProceduralAnimationProperties.BoneInfo boneInfo = Array.Find(component.m_Bones, (ProceduralAnimationProperties.BoneInfo x) => x.name == bones2[i].name);
				if (boneInfo != null)
				{
					bones2[i].m_Acceleration = boneInfo.m_Acceleration;
					bones2[i].m_Speed = boneInfo.m_Speed;
					bones2[i].m_ConnectionID = boneInfo.m_ConnectionID;
					bones2[i].m_SourceID = boneInfo.m_SourceID;
					bones2[i].m_Type = boneInfo.m_Type;
				}
			}
			int num = i + 1;
			i = num;
		}
		component.m_Bones = bones2;
	}
```

- `private static TestTextureSizesUniformity(Colossal.IO.AssetDatabase.SurfaceAsset asset, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription description) : System.Int32`  

```csharp
private static int TestTextureSizesUniformity(SurfaceAsset asset, int tileSize, MaterialLibrary.MaterialDescription description)
	{
		int num = description.m_Stacks.Length;
		int[] array = new int[num];
		int[] array2 = new int[num];
		for (int i = 0; i < num; i++)
		{
			array[i] = -1;
		}
		foreach (KeyValuePair<string, Colossal.IO.AssetDatabase.TextureAsset> texture in asset.textures)
		{
			int stackConfigIndex = description.GetStackConfigIndex(texture.Key);
			if (stackConfigIndex != -1)
			{
				Colossal.IO.AssetDatabase.TextureAsset value = texture.Value;
				value.LoadData(0);
				if (value.width < tileSize)
				{
					return -1;
				}
				if (value.height < tileSize)
				{
					return -2;
				}
				if (array[stackConfigIndex] == -1)
				{
					array[stackConfigIndex] = value.width;
					array2[stackConfigIndex] = value.height;
				}
				else if (array[stackConfigIndex] != value.width || array2[stackConfigIndex] != value.height)
				{
					return -4;
				}
			}
		}
		return 0;
	}
```

- `private static ToJsonSchema(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static string ToJsonSchema(FieldInfo fieldInfo)
	{
		string name = fieldInfo.Name;
		Type fieldType = fieldInfo.FieldType;
		bool nullable = name == "materialTemplate";
		string text = "\"type\": " + ToJsonType(fieldType, nullable);
		if (fieldType.IsEnum)
		{
			return text + ", \"enum\": " + Enum.GetNames(fieldType).ToJSONString();
		}
		if (fieldType.IsArray)
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetElementType()).ToJSONString();
		}
		if (typeof(IList).IsAssignableFrom(fieldType))
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetGenericArguments()[0]).ToJSONString();
		}
		return name switch
		{
			"importerTypeHints" => text + ", \"patternProperties\": { \"^\\\\.[A-Za-z0-9]+$\": { \"$ref\": \"#/definitions/importers\" } }, \"additionalProperties\": false", 
			"sharedAssets" => text + ", \"patternProperties\": { \"^[A-Za-z0-9_*{}]+(\\\\.[A-Za-z0-9]+)?(/_[A-Za-z0-9]+)?$\": { \"type\": \"string\", \"format\": \"uri-reference\" } }, \"additionalProperties\": false", 
			"importSettings" => text + ", \"additionalProperties\": { " + GetSettings() + " }", 
			_ => text, 
		};
	}
```

- `private static ToJsonSchema(System.Type type, Colossal.Json.Variant previous = null) : Colossal.Json.Variant`  

```csharp
private static string ToJsonSchema(FieldInfo fieldInfo)
	{
		string name = fieldInfo.Name;
		Type fieldType = fieldInfo.FieldType;
		bool nullable = name == "materialTemplate";
		string text = "\"type\": " + ToJsonType(fieldType, nullable);
		if (fieldType.IsEnum)
		{
			return text + ", \"enum\": " + Enum.GetNames(fieldType).ToJSONString();
		}
		if (fieldType.IsArray)
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetElementType()).ToJSONString();
		}
		if (typeof(IList).IsAssignableFrom(fieldType))
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetGenericArguments()[0]).ToJSONString();
		}
		return name switch
		{
			"importerTypeHints" => text + ", \"patternProperties\": { \"^\\\\.[A-Za-z0-9]+$\": { \"$ref\": \"#/definitions/importers\" } }, \"additionalProperties\": false", 
			"sharedAssets" => text + ", \"patternProperties\": { \"^[A-Za-z0-9_*{}]+(\\\\.[A-Za-z0-9]+)?(/_[A-Za-z0-9]+)?$\": { \"type\": \"string\", \"format\": \"uri-reference\" } }, \"additionalProperties\": false", 
			"importSettings" => text + ", \"additionalProperties\": { " + GetSettings() + " }", 
			_ => text, 
		};
	}
```

- `private static ToJsonSchema(System.Reflection.FieldInfo fieldInfo) : System.String`  

```csharp
private static string ToJsonSchema(FieldInfo fieldInfo)
	{
		string name = fieldInfo.Name;
		Type fieldType = fieldInfo.FieldType;
		bool nullable = name == "materialTemplate";
		string text = "\"type\": " + ToJsonType(fieldType, nullable);
		if (fieldType.IsEnum)
		{
			return text + ", \"enum\": " + Enum.GetNames(fieldType).ToJSONString();
		}
		if (fieldType.IsArray)
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetElementType()).ToJSONString();
		}
		if (typeof(IList).IsAssignableFrom(fieldType))
		{
			return text + ", \"items\": " + ToJsonSchema(fieldType.GetGenericArguments()[0]).ToJSONString();
		}
		return name switch
		{
			"importerTypeHints" => text + ", \"patternProperties\": { \"^\\\\.[A-Za-z0-9]+$\": { \"$ref\": \"#/definitions/importers\" } }, \"additionalProperties\": false", 
			"sharedAssets" => text + ", \"patternProperties\": { \"^[A-Za-z0-9_*{}]+(\\\\.[A-Za-z0-9]+)?(/_[A-Za-z0-9]+)?$\": { \"type\": \"string\", \"format\": \"uri-reference\" } }, \"additionalProperties\": false", 
			"importSettings" => text + ", \"additionalProperties\": { " + GetSettings() + " }", 
			_ => text, 
		};
	}
```

- `private static ToJsonType(System.Type type, System.Boolean nullable = False) : System.String`  

```csharp
private static string ToJsonType(Type type, bool nullable = false)
	{
		if (type == typeof(string))
		{
			if (!nullable)
			{
				return "\"string\"";
			}
			return "[ \"string\", \"null\" ]";
		}
		if (type.IsEnum)
		{
			return "\"string\"";
		}
		if (type == typeof(uint))
		{
			return "\"nonNegativeInteger\"";
		}
		if (type == typeof(int))
		{
			return "\"integer\"";
		}
		if (type == typeof(float) || type == typeof(double))
		{
			return "\"number\"";
		}
		if (type == typeof(bool))
		{
			return "\"boolean\"";
		}
		if (type.IsArray || typeof(IList).IsAssignableFrom(type))
		{
			return "\"array\"";
		}
		return "\"object\"";
	}
```


## Nested types

- `Game.AssetPipeline.AssetImportPipeline+ThemesConfig`  
- `Game.AssetPipeline.AssetImportPipeline+Progress`  
- `Game.AssetPipeline.AssetImportPipeline+<>c`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__74<T>`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass21_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass21_1`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass21_2`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass25_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass26_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_1`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_10`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_11`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_2`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_3`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_4`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_5`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_6`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_7`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_8`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass27_9`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass34_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass35_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass40_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass46_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass49_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass52_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass74_0<T>`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass84_0`  
- `Game.AssetPipeline.AssetImportPipeline+<>c__DisplayClass84_1`  
- `Game.AssetPipeline.AssetImportPipeline+<ApplyVTMipBias>d__84`  
- `Game.AssetPipeline.AssetImportPipeline+<ExecuteMainThreadQueue>d__16`  
- `Game.AssetPipeline.AssetImportPipeline+<ImportPath>d__21`  


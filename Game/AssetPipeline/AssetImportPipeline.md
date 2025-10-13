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
private static System.Void AddSimplifiedProperties(Colossal.Json.Variant schema);
```

- `private static AddSupportedThemes(System.String projectRootPath) : System.Void`  

```csharp
private static System.Void AddSupportedThemes(System.String projectRootPath);
```

- `private static AdjustNamingConvention(System.String input) : System.String`  

```csharp
private static System.String AdjustNamingConvention(System.String input);
```

- `private static AdjustXBounds(UnityEngine.Transform parent, System.Single x) : System.Void`  

```csharp
private static System.Void AdjustXBounds(UnityEngine.Transform parent, System.Single x);
```

- `private static AdjustZBounds(UnityEngine.Transform parent, System.Single z) : System.Void`  

```csharp
private static System.Void AdjustZBounds(UnityEngine.Transform parent, System.Single z);
```

- `public static ApplyVTMipBias(Colossal.IO.AssetDatabase.IAssetDatabase database, System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipCount, System.String folder) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task ApplyVTMipBias(Colossal.IO.AssetDatabase.IAssetDatabase database, System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipCount, System.String folder);
```

- `public static BuildMidMipsCache(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public static System.Void BuildMidMipsCache(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
```

- `private static CastStruct<TFrom, TTo>(TFrom s) : TTo`  

```csharp
private static TTo CastStruct<TFrom, TTo>(TFrom s);
```

- `public static CollectDataToImport(System.String projectRootPath, System.String[] assetPaths, Colossal.AssetPipeline.Diagnostic.Report report) : System.Collections.Generic.IDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>, Colossal.AssetPipeline.Settings>`  

```csharp
public static System.Collections.Generic.IDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>, Colossal.AssetPipeline.Settings> CollectDataToImport(System.String projectRootPath, System.String[] assetPaths, Colossal.AssetPipeline.Diagnostic.Report report);
```

- `public static ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
public static System.Void ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `public static ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean writeVTSettings, System.Int32 tileSize, System.Int32 midMipsCount, System.Int32 mipBias, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
public static System.Void ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean writeVTSettings, System.Int32 tileSize, System.Int32 midMipsCount, System.Int32 mipBias, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `private static CreateAssetGroupFromSettings(System.String projectRootPath, Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport) : Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset>`  

```csharp
private static Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> CreateAssetGroupFromSettings(System.String projectRootPath, Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport);
```

- `private static CreateBackground(UnityEngine.Transform parent, System.String name, UnityEngine.Vector3 position, UnityEngine.Vector3 size) : System.Void`  

```csharp
private static System.Void CreateBackground(UnityEngine.Transform parent, System.String name, UnityEngine.Vector3 position, UnityEngine.Vector3 size);
```

- `private static CreateBounds(UnityEngine.Transform parent) : System.Void`  

```csharp
private static System.Void CreateBounds(UnityEngine.Transform parent);
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
private static System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> CreateRenderPrefab(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> asset, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory);
```

- `private static CreateRenderPrefab(System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : Game.Prefabs.RenderPrefab`  

```csharp
private static Game.Prefabs.RenderPrefab CreateRenderPrefab(System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory);
```

- `private static CreateRenderPrefabs(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Void`  

```csharp
private static System.Void CreateRenderPrefabs(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory);
```

- `private static CreateStylePrefab(System.ValueTuple<System.String, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Colossal.Animations.Animation, Colossal.Animations.BoneHierarchy, System.String, System.Int32, Colossal.Hash128>>, System.Int32, System.Int32> style, System.String sourcePath, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.AnimationAsset> overrideSafeGuard, System.Collections.Generic.List<Game.Prefabs.RenderPrefab> prefabs, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : Game.Prefabs.CharacterStyle`  

```csharp
private static Game.Prefabs.CharacterStyle CreateStylePrefab(System.ValueTuple<System.String, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Colossal.Animations.Animation, Colossal.Animations.BoneHierarchy, System.String, System.Int32, Colossal.Hash128>>, System.Int32, System.Int32> style, System.String sourcePath, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.AnimationAsset> overrideSafeGuard, System.Collections.Generic.List<Game.Prefabs.RenderPrefab> prefabs, Game.AssetPipeline.IPrefabFactory prefabFactory);
```

- `private static CreateTitle(UnityEngine.Transform parent, System.String text, UnityEngine.Vector3 textPosOffset, UnityEngine.Color bgColor, UnityEngine.Color txtColor, System.Int32 txtSize, System.Single txtPadding) : System.Void`  

```csharp
private static System.Void CreateTitle(UnityEngine.Transform parent, System.String text, UnityEngine.Vector3 textPosOffset, UnityEngine.Color bgColor, UnityEngine.Color txtColor, System.Int32 txtSize, System.Single txtPadding);
```

- `private static DisposeLODs(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD>> assets) : System.Void`  

```csharp
private static System.Void DisposeLODs(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD>> assets);
```

- `private static DisposeLODs(System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> assets) : System.Void`  

```csharp
private static System.Void DisposeLODs(System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> assets);
```

- `private static ExecuteMainThreadQueue(System.Threading.Tasks.Task importTask, Colossal.AssetPipeline.Diagnostic.Report report) : System.Threading.Tasks.Task`  

```csharp
private static System.Threading.Tasks.Task ExecuteMainThreadQueue(System.Threading.Tasks.Task importTask, Colossal.AssetPipeline.Diagnostic.Report report);
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
public static System.Void GenerateJSONSchema();
```

- `private static GetDefinitions() : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant GetDefinitions();
```

- `public static GetImportChainFor(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ISettingable>`  

```csharp
public static System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ISettingable> GetImportChainFor(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private static GetNameWithoutGUID(System.String str) : System.String`  

```csharp
private static System.String GetNameWithoutGUID(System.String str);
```

- `private static GetSettings() : System.String`  

```csharp
private static System.String GetSettings();
```

- `private static GetSkinningInfo(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]& bones, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Boolean`  

```csharp
private static System.Boolean GetSkinningInfo(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]& bones, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
```

- `public static GetTextureReferenceCount(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32& surfaceCount) : System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>>`  

```csharp
public static System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> GetTextureReferenceCount(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32& surfaceCount);
```

- `private static GetUniqueString(System.String input, System.Int32 currentIndex, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] array) : System.String`  

```csharp
private static System.String GetUniqueString(System.String input, System.Int32 currentIndex, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] array);
```

- `public static HideVTSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces) : System.Void`  

```csharp
public static System.Void HideVTSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces);
```

- `private static ImportAssetGroup(System.String projectRootPath, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.Collections.Generic.List`1[[System.Collections.Generic.List`1[[Colossal.AssetPipeline.LOD, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& lods, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, Colossal.AssetPipeline.Diagnostic.Report report, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport) : System.Boolean`  

```csharp
private static System.Boolean ImportAssetGroup(System.String projectRootPath, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.Collections.Generic.List`1[[System.Collections.Generic.List`1[[Colossal.AssetPipeline.LOD, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& lods, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, Colossal.AssetPipeline.Diagnostic.Report report, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport);
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
public static System.Threading.Tasks.Task ImportPath(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths, Colossal.AssetPipeline.ImportMode importMode, System.Boolean convertToVT, System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback, Game.AssetPipeline.IPrefabFactory prefabFactory);
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
private static System.Boolean IsArtRootPath(System.String rootPathName, System.String path, System.String& artProjectPath, System.String& artProjectRelativePath);
```

- `public static IsArtRootPath(System.String rootPathName, System.String[] paths, System.String& artProjectPath, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& artProjectRelativePaths) : System.Boolean`  

```csharp
public static System.Boolean IsArtRootPath(System.String rootPathName, System.String[] paths, System.String& artProjectPath, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& artProjectRelativePaths);
```

- `private static IsLODsValid(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets) : System.Boolean`  

```csharp
private static System.Boolean IsLODsValid(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets);
```

- `private static MakeRelativePath(System.String path, System.String rootPath) : System.String`  

```csharp
private static System.String MakeRelativePath(System.String path, System.String rootPath);
```

- `public static ProcessSurfacesForVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
public static System.Void ProcessSurfacesForVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `private static ReportTextureReferenceStats(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
private static System.Void ReportTextureReferenceStats(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `private static ResaveCache(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  

```csharp
private static System.Void ResaveCache(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report);
```

- `private static ResolveRelativePath(System.String projectRootPath, System.String target, System.String to) : System.String`  

```csharp
private static System.String ResolveRelativePath(System.String projectRootPath, System.String target, System.String to);
```

- `public static SetReportCallback(System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback) : System.Void`  

```csharp
public static System.Void SetReportCallback(System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback);
```

- `private static SetupComponents(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  

```csharp
private static System.Void SetupComponents(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
```

- `private static SetupEmissiveComponent(Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod) : System.Void`  

```csharp
private static System.Void SetupEmissiveComponent(Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod);
```

- `private static SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  

```csharp
private static System.Void SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
```

- `private static SetupLODs(Colossal.AssetPipeline.Settings settings, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> meshPrefabs) : System.Void`  

```csharp
private static System.Void SetupLODs(Colossal.AssetPipeline.Settings settings, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> meshPrefabs);
```

- `private static SetupProceduralAnimationComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  

```csharp
private static System.Void SetupProceduralAnimationComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report);
```

- `private static TestTextureSizesUniformity(Colossal.IO.AssetDatabase.SurfaceAsset asset, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription description) : System.Int32`  

```csharp
private static System.Int32 TestTextureSizesUniformity(Colossal.IO.AssetDatabase.SurfaceAsset asset, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription description);
```

- `private static ToJsonSchema(System.Object obj) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant ToJsonSchema(System.Object obj);
```

- `private static ToJsonSchema(System.Type type, Colossal.Json.Variant previous = null) : Colossal.Json.Variant`  

```csharp
private static Colossal.Json.Variant ToJsonSchema(System.Type type, Colossal.Json.Variant previous);
```

- `private static ToJsonSchema(System.Reflection.FieldInfo fieldInfo) : System.String`  

```csharp
private static System.String ToJsonSchema(System.Reflection.FieldInfo fieldInfo);
```

- `private static ToJsonType(System.Type type, System.Boolean nullable = False) : System.String`  

```csharp
private static System.String ToJsonType(System.Type type, System.Boolean nullable);
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


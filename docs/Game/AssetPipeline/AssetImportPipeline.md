# Game.AssetPipeline.AssetImportPipeline

**Assembly:** `Game`  
**Namespace:** `Game.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly Colossal.Logging.ILog log`  
- `public static System.Boolean useParallelImport`  
- `public static Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ImportPath`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfPostImport`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportModels`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportTextures`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateGeomsSurfaces`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportAssetGroup`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfImportDidimo`  
- `private static readonly Game.AssetPipeline.AssetImportPipeline+Progress s_Progress`  
- `private static Colossal.AssetPipeline.MainThreadDispatcher s_MainThreadDispatcher`  
- `public static System.Action<System.String, UnityEngine.Texture> OnDebugTexture`  
- `private static UnityEngine.Material s_BackgroundMaterial`  
- `private static const System.String kMainSettings`  
- `private static const System.Single kBoundSize`  
- `private static const System.Single kHalfBoundSize`  

## Properties

- `public static UnityEngine.Material backgroundMaterial { get }`  

## Methods

- `internal static <GetSettings>g__GetIfThen|54_0(Colossal.AssetPipeline.Importers.ISettings settings) : System.String`  
- `internal static <HideVTSourceTextures>g__AddReferenceTo|82_0(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> references, Colossal.IO.AssetDatabase.TextureAsset texture, Colossal.IO.AssetDatabase.SurfaceAsset surface) : System.Void`  
- `internal static <InstantiateRenderPrefabs>g__GetParent|74_0<T>(System.String path) : System.String`  
- `private static AddSimplifiedProperties(Colossal.Json.Variant schema) : System.Void`  
- `private static AddSupportedThemes(System.String projectRootPath) : System.Void`  
- `private static AdjustNamingConvention(System.String input) : System.String`  
- `private static AdjustXBounds(UnityEngine.Transform parent, System.Single x) : System.Void`  
- `private static AdjustZBounds(UnityEngine.Transform parent, System.Single z) : System.Void`  
- `public static ApplyVTMipBias(Colossal.IO.AssetDatabase.IAssetDatabase database, System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipCount, System.String folder) : System.Threading.Tasks.Task`  
- `public static BuildMidMipsCache(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32 tileSize, System.Int32 midMipsCount, Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  
- `private static CastStruct<TFrom, TTo>(TFrom s) : TTo`  
- `public static CollectDataToImport(System.String projectRootPath, System.String[] assetPaths, Colossal.AssetPipeline.Diagnostic.Report report) : System.Collections.Generic.IDictionary<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>, Colossal.AssetPipeline.Settings>`  
- `public static ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  
- `public static ConvertSurfacesToVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> allSurfaces, System.Boolean writeVTSettings, System.Int32 tileSize, System.Int32 midMipsCount, System.Int32 mipBias, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  
- `private static CreateAssetGroupFromSettings(System.String projectRootPath, Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport) : Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset>`  
- `private static CreateBackground(UnityEngine.Transform parent, System.String name, UnityEngine.Vector3 position, UnityEngine.Vector3 size) : System.Void`  
- `private static CreateBounds(UnityEngine.Transform parent) : System.Void`  
- `private static CreateDidimoAssets(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  
- `private static CreateGeometriesAndSurfaces(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  
- `private static CreatePrefab<T>(System.String suffix, System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : T`  
- `private static CreateRenderPrefab(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> asset, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>>`  
- `private static CreateRenderPrefab(System.String sourcePath, System.String name, System.Int32 lodLevel, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : Game.Prefabs.RenderPrefab`  
- `private static CreateRenderPrefabs(Colossal.AssetPipeline.Settings settings, System.String sourcePath, System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets, Colossal.AssetPipeline.ImportMode importMode, Colossal.AssetPipeline.Diagnostic.Report report, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SurfaceAsset> VTMaterials, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Void`  
- `private static CreateStylePrefab(System.ValueTuple<System.String, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Colossal.Animations.Animation, Colossal.Animations.BoneHierarchy, System.String, System.Int32, Colossal.Hash128>>, System.Int32, System.Int32> style, System.String sourcePath, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.AnimationAsset> overrideSafeGuard, System.Collections.Generic.List<Game.Prefabs.RenderPrefab> prefabs, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : Game.Prefabs.CharacterStyle`  
- `private static CreateTitle(UnityEngine.Transform parent, System.String text, UnityEngine.Vector3 textPosOffset, UnityEngine.Color bgColor, UnityEngine.Color txtColor, System.Int32 txtSize, System.Single txtPadding) : System.Void`  
- `private static DisposeLODs(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD>> assets) : System.Void`  
- `private static DisposeLODs(System.Collections.Generic.IReadOnlyList<Colossal.AssetPipeline.LOD> assets) : System.Void`  
- `private static ExecuteMainThreadQueue(System.Threading.Tasks.Task importTask, Colossal.AssetPipeline.Diagnostic.Report report) : System.Threading.Tasks.Task`  
- `private static FromManagedArray<T>(T[] array) : Unity.Collections.NativeArray<System.Byte>`  
- `private static FromManagedArray<T>(T[] array, System.Int32 offset, System.Int32 elementSize, System.Int32 countPerElement) : Unity.Collections.NativeArray<System.Byte>`  
- `public static GenerateJSONSchema() : System.Void`  
- `private static GetDefinitions() : Colossal.Json.Variant`  
- `public static GetImportChainFor(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset asset, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ISettingable>`  
- `private static GetNameWithoutGUID(System.String str) : System.String`  
- `private static GetSettings() : System.String`  
- `private static GetSkinningInfo(Colossal.AssetPipeline.Importers.ModelImporter+Model model, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[]& bones, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Boolean`  
- `public static GetTextureReferenceCount(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Int32& surfaceCount) : System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>>`  
- `private static GetUniqueString(System.String input, System.Int32 currentIndex, Game.Prefabs.ProceduralAnimationProperties+BoneInfo[] array) : System.String`  
- `public static HideVTSourceTextures(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces) : System.Void`  
- `private static ImportAssetGroup(System.String projectRootPath, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.Collections.Generic.List`1[[System.Collections.Generic.List`1[[Colossal.AssetPipeline.LOD, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& lods, System.Action`5[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Colossal.AssetPipeline.ImportMode, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Colossal.AssetPipeline.Diagnostic.Report, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.HashSet`1[[Colossal.IO.AssetDatabase.SurfaceAsset, Colossal.IO.AssetDatabase, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[Game.AssetPipeline.IPrefabFactory, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& postImportOperations, Colossal.AssetPipeline.Diagnostic.Report report, Colossal.AssetPipeline.Diagnostic.Report+Asset assetReport) : System.Boolean`  
- `private static ImportDidimo(Colossal.AssetPipeline.Settings settings, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  
- `private static ImportModels(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  
- `public static ImportPath(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths, Colossal.AssetPipeline.ImportMode importMode, System.Boolean convertToVT, System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback = null, Game.AssetPipeline.IPrefabFactory prefabFactory = null) : System.Threading.Tasks.Task`  
- `private static ImportSettings(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : Colossal.AssetPipeline.Settings`  
- `private static ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  
- `private static ImportTextures(Colossal.AssetPipeline.Settings settings, System.String relativeRootPath, Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<Colossal.AssetPipeline.TextureAsset, System.Boolean> predicate, System.ValueTuple<Colossal.AssetPipeline.Diagnostic.Report+ImportStep, Colossal.AssetPipeline.Diagnostic.Report+Asset> report) : System.Void`  
- `public static InstantiateRenderPrefabs<T>(System.Collections.Generic.IEnumerable<System.ValueTuple<T, System.String>> prefabs, System.Boolean smartInstantiate, System.Boolean ignoreLODs) : System.Void`  
- `private static IsArtRootPath(System.String rootPathName, System.String path, System.String& artProjectPath, System.String& artProjectRelativePath) : System.Boolean`  
- `public static IsArtRootPath(System.String rootPathName, System.String[] paths, System.String& artProjectPath, System.Collections.Generic.List`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& artProjectRelativePaths) : System.Boolean`  
- `private static IsLODsValid(System.Collections.Generic.IReadOnlyList<System.Collections.Generic.List<Colossal.AssetPipeline.LOD>> assets) : System.Boolean`  
- `private static MakeRelativePath(System.String path, System.String rootPath) : System.String`  
- `public static ProcessSurfacesForVT(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfacesToConvert, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaces, System.Boolean force, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  
- `private static ReportTextureReferenceStats(System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  
- `private static ResaveCache(Colossal.AssetPipeline.Diagnostic.Report+ImportStep report) : System.Void`  
- `private static ResolveRelativePath(System.String projectRootPath, System.String target, System.String to) : System.String`  
- `public static SetReportCallback(System.Func<System.String, System.String, System.Single, System.Boolean> progressCallback) : System.Void`  
- `private static SetupComponents(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  
- `private static SetupEmissiveComponent(Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod) : System.Void`  
- `private static SetupEmissiveComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  
- `private static SetupLODs(Colossal.AssetPipeline.Settings settings, System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.RenderPrefab, Colossal.AssetPipeline.Diagnostic.Report+Prefab>> meshPrefabs) : System.Void`  
- `private static SetupProceduralAnimationComponent(Colossal.AssetPipeline.Settings settings, Game.Prefabs.RenderPrefab meshPrefab, Colossal.AssetPipeline.LOD lod, Colossal.AssetPipeline.Diagnostic.Report+Prefab report) : System.Void`  
- `private static TestTextureSizesUniformity(Colossal.IO.AssetDatabase.SurfaceAsset asset, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription description) : System.Int32`  
- `private static ToJsonSchema(System.Object obj) : Colossal.Json.Variant`  
- `private static ToJsonSchema(System.Type type, Colossal.Json.Variant previous = null) : Colossal.Json.Variant`  
- `private static ToJsonSchema(System.Reflection.FieldInfo fieldInfo) : System.String`  
- `private static ToJsonType(System.Type type, System.Boolean nullable = False) : System.String`  

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


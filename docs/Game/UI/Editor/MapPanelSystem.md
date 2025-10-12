# Game.UI.Editor.MapPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.Hash128 m_CurrentSourceDataGuid`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  
- `private Game.UI.MapMetadataSystem m_MapMetadataSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.IMapTilePurchaseSystem m_MapTilePurchaseSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel`  
- `private Unity.Entities.EntityQuery m_TimeQuery`  
- `private Unity.Entities.EntityQuery m_ThemeQuery`  
- `public System.Boolean m_MapNameAsCityName`  
- `public System.Int32 m_StartingYear`  
- `public System.Int32 m_StartingMonth`  
- `public System.Single m_StartingTime`  
- `public System.Boolean m_CurrentYearAsStartingYear`  
- `private Game.UI.Widgets.IconButtonGroup m_ThemeButtonGroup`  
- `private Game.UI.Editor.LocalizationField m_MapNameLocalization`  
- `private Game.UI.Editor.LocalizationField m_MapDescriptionLocalization`  
- `private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Preview`  
- `private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Thumbnail`  
- `private Game.UI.Widgets.Button m_MapTileSelectionButton`  
- `private Game.UI.Editor.MapRequirementSystem m_MapRequirementSystem`  
- `private Game.UI.Widgets.PagedList m_RequiredListWidget`  
- `private Game.UI.Widgets.EditorGenerator m_Generator`  
- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform`  
- `private static readonly System.String kSelectStartingTilesPrompt`  
- `private static readonly System.String kStopSelectingStartingTilesPrompt`  

## Constructors

- `public MapPanelSystem()`  

## Methods

- `private <OnCreate>b__28_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `private <OnCreate>b__28_1() : System.Boolean`  
- `private <OnCreate>b__28_10(Unity.Mathematics.float3 value) : System.Void`  
- `private <OnCreate>b__28_11() : Unity.Mathematics.float2`  
- `private <OnCreate>b__28_12(Unity.Mathematics.float2 value) : System.Void`  
- `private <OnCreate>b__28_13() : System.Double`  
- `private <OnCreate>b__28_14(System.Double value) : System.Void`  
- `private <OnCreate>b__28_16() : System.Boolean`  
- `private <OnCreate>b__28_18() : System.Boolean`  
- `private <OnCreate>b__28_2(System.Boolean value) : System.Void`  
- `private <OnCreate>b__28_20() : System.Boolean`  
- `private <OnCreate>b__28_22() : System.Boolean`  
- `private <OnCreate>b__28_24() : System.Boolean`  
- `private <OnCreate>b__28_26() : System.Boolean`  
- `private <OnCreate>b__28_28() : System.Boolean`  
- `private <OnCreate>b__28_3() : System.Boolean`  
- `private <OnCreate>b__28_30() : System.Boolean`  
- `private <OnCreate>b__28_32() : System.Boolean`  
- `private <OnCreate>b__28_34() : System.Boolean`  
- `private <OnCreate>b__28_36() : System.Boolean`  
- `private <OnCreate>b__28_37() : System.Boolean`  
- `private <OnCreate>b__28_4() : System.Int32`  
- `private <OnCreate>b__28_5() : System.Boolean`  
- `private <OnCreate>b__28_6(System.Boolean value) : System.Void`  
- `private <OnCreate>b__28_7() : System.Int32`  
- `private <OnCreate>b__28_8() : System.Single`  
- `private <OnCreate>b__28_9() : Unity.Mathematics.float3`  
- `private <ShowSaveMapPanel>b__40_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  
- `private <ShowShareMapPanel>b__41_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  
- `private ApplyTime() : System.Void`  
- `private CaptureCameraProperties() : System.Void`  
- `private FetchThemes() : System.Void`  
- `private FetchTime() : System.Void`  
- `private GetMapInfo(Game.Assets.MapInfo merge = null) : Game.Assets.MapInfo`  
- `private GetMaps() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  
- `private InitLocalization(Game.Assets.MapMetadata asset = null) : System.Void`  
- `private InitPreview(Game.Assets.MapMetadata asset = null) : System.Void`  
- `public LoadMap(Colossal.Hash128 guid) : System.Threading.Tasks.Task`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnLoadMap(Colossal.Hash128 guid) : System.Void`  
- `private OnSaveMap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Game.Assets.MapMetadata> callback = null) : System.Void`  
- `private OnSelectPreview(Colossal.Hash128 guid) : System.Void`  
- `private OnSelectThumbnail(Colossal.Hash128 guid) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SaveClimate(Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : Colossal.IO.AssetDatabase.PrefabAsset`  
- `private SaveLocalization(Colossal.IO.AssetDatabase.ILocalAssetDatabase db, System.String fileName) : Colossal.IO.AssetDatabase.LocaleAsset[]`  
- `public SaveMap(System.String fileName, Colossal.Hash128 overwriteGuid, Game.Assets.MapInfo existing, Colossal.IO.AssetDatabase.ILocalAssetDatabase finalDb, Colossal.IO.AssetDatabase.AssetDataPath packagePath, System.Boolean embedLocalization, System.Action<Game.Assets.MapMetadata> callback = null) : System.Threading.Tasks.Task`  
- `private SetStartingMonth(System.Int32 value) : System.Void`  
- `private SetStartingTime(System.Single value) : System.Void`  
- `private SetStartingYear(System.Int32 value) : System.Void`  
- `private ShareMap(Game.Assets.MapMetadata map) : System.Void`  
- `public ShowLoadMapPanel() : System.Void`  
- `private ShowPreviewPicker() : System.Void`  
- `public ShowSaveMapPanel() : System.Void`  
- `private ShowShareMapPanel() : System.Void`  
- `private ShowThumbnailPicker() : System.Void`  
- `private ToggleMapTileSelection() : System.Void`  
- `private TryGetAssetItem(Game.Assets.MapMetadata asset, Game.UI.Editor.AssetItem& item) : System.Boolean`  
- `private UpdateMapTileButton(System.String text) : System.Void`  
- `private UpdateStartingTiles() : System.Void`  

## Nested types

- `Game.UI.Editor.MapPanelSystem+PreviewInfo`  
- `Game.UI.Editor.MapPanelSystem+<>c`  
- `Game.UI.Editor.MapPanelSystem+<>c__DisplayClass33_0`  
- `Game.UI.Editor.MapPanelSystem+<>c__DisplayClass48_0`  
- `Game.UI.Editor.MapPanelSystem+<>c__DisplayClass52_0`  
- `Game.UI.Editor.MapPanelSystem+<>c__DisplayClass53_0`  
- `Game.UI.Editor.MapPanelSystem+<>c__DisplayClass53_1`  
- `Game.UI.Editor.MapPanelSystem+<GetMaps>d__42`  
- `Game.UI.Editor.MapPanelSystem+<LoadMap>d__49`  
- `Game.UI.Editor.MapPanelSystem+<SaveMap>d__53`  


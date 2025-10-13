# Game.UI.Editor.MapPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Colossal.Hash128 m_CurrentSourceDataGuid;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Serialization.SaveGameSystem m_SaveGameSystem;
    private Game.UI.MapMetadataSystem m_MapMetadataSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.IMapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel;
    private Unity.Entities.EntityQuery m_TimeQuery;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    public System.Boolean m_MapNameAsCityName;
    public System.Int32 m_StartingYear;
    public System.Int32 m_StartingMonth;
    public System.Single m_StartingTime;
    public System.Boolean m_CurrentYearAsStartingYear;
    private Game.UI.Widgets.IconButtonGroup m_ThemeButtonGroup;
    private Game.UI.Editor.LocalizationField m_MapNameLocalization;
    private Game.UI.Editor.LocalizationField m_MapDescriptionLocalization;
    private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Preview;
    private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Thumbnail;
    private Game.UI.Widgets.Button m_MapTileSelectionButton;
    private Game.UI.Editor.MapRequirementSystem m_MapRequirementSystem;
    private Game.UI.Widgets.PagedList m_RequiredListWidget;
    private Game.UI.Widgets.EditorGenerator m_Generator;
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform;
    private static readonly System.String kSelectStartingTilesPrompt;
    private static readonly System.String kStopSelectingStartingTilesPrompt;

    public MapPanelSystem();

    private System.Void <OnCreate>b__28_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Boolean <OnCreate>b__28_1();
    private System.Void <OnCreate>b__28_10(Unity.Mathematics.float3 value);
    private Unity.Mathematics.float2 <OnCreate>b__28_11();
    private System.Void <OnCreate>b__28_12(Unity.Mathematics.float2 value);
    private System.Double <OnCreate>b__28_13();
    private System.Void <OnCreate>b__28_14(System.Double value);
    private System.Boolean <OnCreate>b__28_16();
    private System.Boolean <OnCreate>b__28_18();
    private System.Void <OnCreate>b__28_2(System.Boolean value);
    private System.Boolean <OnCreate>b__28_20();
    private System.Boolean <OnCreate>b__28_22();
    private System.Boolean <OnCreate>b__28_24();
    private System.Boolean <OnCreate>b__28_26();
    private System.Boolean <OnCreate>b__28_28();
    private System.Boolean <OnCreate>b__28_3();
    private System.Boolean <OnCreate>b__28_30();
    private System.Boolean <OnCreate>b__28_32();
    private System.Boolean <OnCreate>b__28_34();
    private System.Boolean <OnCreate>b__28_36();
    private System.Boolean <OnCreate>b__28_37();
    private System.Int32 <OnCreate>b__28_4();
    private System.Boolean <OnCreate>b__28_5();
    private System.Void <OnCreate>b__28_6(System.Boolean value);
    private System.Int32 <OnCreate>b__28_7();
    private System.Single <OnCreate>b__28_8();
    private Unity.Mathematics.float3 <OnCreate>b__28_9();
    private System.Void <ShowSaveMapPanel>b__40_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void <ShowShareMapPanel>b__41_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
    private System.Void ApplyTime();
    private System.Void CaptureCameraProperties();
    private System.Void FetchThemes();
    private System.Void FetchTime();
    private Game.Assets.MapInfo GetMapInfo(Game.Assets.MapInfo merge);
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetMaps();
    private System.Void InitLocalization(Game.Assets.MapMetadata asset);
    private System.Void InitPreview(Game.Assets.MapMetadata asset);
    public System.Threading.Tasks.Task LoadMap(Colossal.Hash128 guid);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnLoadMap(Colossal.Hash128 guid);
    private System.Void OnSaveMap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Game.Assets.MapMetadata> callback);
    private System.Void OnSelectPreview(Colossal.Hash128 guid);
    private System.Void OnSelectThumbnail(Colossal.Hash128 guid);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    private Colossal.IO.AssetDatabase.PrefabAsset SaveClimate(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    private Colossal.IO.AssetDatabase.LocaleAsset[] SaveLocalization(Colossal.IO.AssetDatabase.ILocalAssetDatabase db, System.String fileName);
    public System.Threading.Tasks.Task SaveMap(System.String fileName, Colossal.Hash128 overwriteGuid, Game.Assets.MapInfo existing, Colossal.IO.AssetDatabase.ILocalAssetDatabase finalDb, Colossal.IO.AssetDatabase.AssetDataPath packagePath, System.Boolean embedLocalization, System.Action<Game.Assets.MapMetadata> callback);
    private System.Void SetStartingMonth(System.Int32 value);
    private System.Void SetStartingTime(System.Single value);
    private System.Void SetStartingYear(System.Int32 value);
    private System.Void ShareMap(Game.Assets.MapMetadata map);
    public System.Void ShowLoadMapPanel();
    private System.Void ShowPreviewPicker();
    public System.Void ShowSaveMapPanel();
    private System.Void ShowShareMapPanel();
    private System.Void ShowThumbnailPicker();
    private System.Void ToggleMapTileSelection();
    private System.Boolean TryGetAssetItem(Game.Assets.MapMetadata asset, Game.UI.Editor.AssetItem& item);
    private System.Void UpdateMapTileButton(System.String text);
    private System.Void UpdateStartingTiles();
}
```


## Fields

- `private Colossal.Hash128 m_CurrentSourceDataGuid`  

```csharp
private Colossal.Hash128 m_CurrentSourceDataGuid;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SaveGameSystem;
```

- `private Game.UI.MapMetadataSystem m_MapMetadataSystem`  

```csharp
private Game.UI.MapMetadataSystem m_MapMetadataSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.IMapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.IMapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel`  

```csharp
private Game.UI.Editor.EditorAssetUploadPanel m_AssetUploadPanel;
```

- `private Unity.Entities.EntityQuery m_TimeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeQuery;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `public System.Boolean m_MapNameAsCityName`  

```csharp
public System.Boolean m_MapNameAsCityName;
```

- `public System.Int32 m_StartingYear`  

```csharp
public System.Int32 m_StartingYear;
```

- `public System.Int32 m_StartingMonth`  

```csharp
public System.Int32 m_StartingMonth;
```

- `public System.Single m_StartingTime`  

```csharp
public System.Single m_StartingTime;
```

- `public System.Boolean m_CurrentYearAsStartingYear`  

```csharp
public System.Boolean m_CurrentYearAsStartingYear;
```

- `private Game.UI.Widgets.IconButtonGroup m_ThemeButtonGroup`  

```csharp
private Game.UI.Widgets.IconButtonGroup m_ThemeButtonGroup;
```

- `private Game.UI.Editor.LocalizationField m_MapNameLocalization`  

```csharp
private Game.UI.Editor.LocalizationField m_MapNameLocalization;
```

- `private Game.UI.Editor.LocalizationField m_MapDescriptionLocalization`  

```csharp
private Game.UI.Editor.LocalizationField m_MapDescriptionLocalization;
```

- `private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Preview`  

```csharp
private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Preview;
```

- `private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Thumbnail`  

```csharp
private Game.UI.Editor.MapPanelSystem+PreviewInfo m_Thumbnail;
```

- `private Game.UI.Widgets.Button m_MapTileSelectionButton`  

```csharp
private Game.UI.Widgets.Button m_MapTileSelectionButton;
```

- `private Game.UI.Editor.MapRequirementSystem m_MapRequirementSystem`  

```csharp
private Game.UI.Editor.MapRequirementSystem m_MapRequirementSystem;
```

- `private Game.UI.Widgets.PagedList m_RequiredListWidget`  

```csharp
private Game.UI.Widgets.PagedList m_RequiredListWidget;
```

- `private Game.UI.Widgets.EditorGenerator m_Generator`  

```csharp
private Game.UI.Widgets.EditorGenerator m_Generator;
```

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Platform;
```

- `private static readonly System.String kSelectStartingTilesPrompt`  

```csharp
private static readonly System.String kSelectStartingTilesPrompt;
```

- `private static readonly System.String kStopSelectingStartingTilesPrompt`  

```csharp
private static readonly System.String kStopSelectingStartingTilesPrompt;
```


## Constructors

- `public MapPanelSystem()`  

```csharp
public MapPanelSystem();
```


## Methods

- `private <OnCreate>b__28_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <OnCreate>b__28_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private <OnCreate>b__28_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_1();
```

- `private <OnCreate>b__28_10(Unity.Mathematics.float3 value) : System.Void`  

```csharp
private System.Void <OnCreate>b__28_10(Unity.Mathematics.float3 value);
```

- `private <OnCreate>b__28_11() : Unity.Mathematics.float2`  

```csharp
private Unity.Mathematics.float2 <OnCreate>b__28_11();
```

- `private <OnCreate>b__28_12(Unity.Mathematics.float2 value) : System.Void`  

```csharp
private System.Void <OnCreate>b__28_12(Unity.Mathematics.float2 value);
```

- `private <OnCreate>b__28_13() : System.Double`  

```csharp
private System.Double <OnCreate>b__28_13();
```

- `private <OnCreate>b__28_14(System.Double value) : System.Void`  

```csharp
private System.Void <OnCreate>b__28_14(System.Double value);
```

- `private <OnCreate>b__28_16() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_16();
```

- `private <OnCreate>b__28_18() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_18();
```

- `private <OnCreate>b__28_2(System.Boolean value) : System.Void`  

```csharp
private System.Void <OnCreate>b__28_2(System.Boolean value);
```

- `private <OnCreate>b__28_20() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_20();
```

- `private <OnCreate>b__28_22() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_22();
```

- `private <OnCreate>b__28_24() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_24();
```

- `private <OnCreate>b__28_26() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_26();
```

- `private <OnCreate>b__28_28() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_28();
```

- `private <OnCreate>b__28_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_3();
```

- `private <OnCreate>b__28_30() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_30();
```

- `private <OnCreate>b__28_32() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_32();
```

- `private <OnCreate>b__28_34() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_34();
```

- `private <OnCreate>b__28_36() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_36();
```

- `private <OnCreate>b__28_37() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_37();
```

- `private <OnCreate>b__28_4() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__28_4();
```

- `private <OnCreate>b__28_5() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__28_5();
```

- `private <OnCreate>b__28_6(System.Boolean value) : System.Void`  

```csharp
private System.Void <OnCreate>b__28_6(System.Boolean value);
```

- `private <OnCreate>b__28_7() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__28_7();
```

- `private <OnCreate>b__28_8() : System.Single`  

```csharp
private System.Single <OnCreate>b__28_8();
```

- `private <OnCreate>b__28_9() : Unity.Mathematics.float3`  

```csharp
private Unity.Mathematics.float3 <OnCreate>b__28_9();
```

- `private <ShowSaveMapPanel>b__40_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void <ShowSaveMapPanel>b__40_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private <ShowShareMapPanel>b__41_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
private System.Void <ShowShareMapPanel>b__41_0(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```

- `private ApplyTime() : System.Void`  

```csharp
private System.Void ApplyTime();
```

- `private CaptureCameraProperties() : System.Void`  

```csharp
private System.Void CaptureCameraProperties();
```

- `private FetchThemes() : System.Void`  

```csharp
private System.Void FetchThemes();
```

- `private FetchTime() : System.Void`  

```csharp
private System.Void FetchTime();
```

- `private GetMapInfo(Game.Assets.MapInfo merge = null) : Game.Assets.MapInfo`  

```csharp
private Game.Assets.MapInfo GetMapInfo(Game.Assets.MapInfo merge);
```

- `private GetMaps() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetMaps();
```

- `private InitLocalization(Game.Assets.MapMetadata asset = null) : System.Void`  

```csharp
private System.Void InitLocalization(Game.Assets.MapMetadata asset);
```

- `private InitPreview(Game.Assets.MapMetadata asset = null) : System.Void`  

```csharp
private System.Void InitPreview(Game.Assets.MapMetadata asset);
```

- `public LoadMap(Colossal.Hash128 guid) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task LoadMap(Colossal.Hash128 guid);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnLoadMap(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void OnLoadMap(Colossal.Hash128 guid);
```

- `private OnSaveMap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Game.Assets.MapMetadata> callback = null) : System.Void`  

```csharp
private System.Void OnSaveMap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Game.Assets.MapMetadata> callback);
```

- `private OnSelectPreview(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void OnSelectPreview(Colossal.Hash128 guid);
```

- `private OnSelectThumbnail(Colossal.Hash128 guid) : System.Void`  

```csharp
private System.Void OnSelectThumbnail(Colossal.Hash128 guid);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SaveClimate(Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : Colossal.IO.AssetDatabase.PrefabAsset`  

```csharp
private Colossal.IO.AssetDatabase.PrefabAsset SaveClimate(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
```

- `private SaveLocalization(Colossal.IO.AssetDatabase.ILocalAssetDatabase db, System.String fileName) : Colossal.IO.AssetDatabase.LocaleAsset[]`  

```csharp
private Colossal.IO.AssetDatabase.LocaleAsset[] SaveLocalization(Colossal.IO.AssetDatabase.ILocalAssetDatabase db, System.String fileName);
```

- `public SaveMap(System.String fileName, Colossal.Hash128 overwriteGuid, Game.Assets.MapInfo existing, Colossal.IO.AssetDatabase.ILocalAssetDatabase finalDb, Colossal.IO.AssetDatabase.AssetDataPath packagePath, System.Boolean embedLocalization, System.Action<Game.Assets.MapMetadata> callback = null) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SaveMap(System.String fileName, Colossal.Hash128 overwriteGuid, Game.Assets.MapInfo existing, Colossal.IO.AssetDatabase.ILocalAssetDatabase finalDb, Colossal.IO.AssetDatabase.AssetDataPath packagePath, System.Boolean embedLocalization, System.Action<Game.Assets.MapMetadata> callback);
```

- `private SetStartingMonth(System.Int32 value) : System.Void`  

```csharp
private System.Void SetStartingMonth(System.Int32 value);
```

- `private SetStartingTime(System.Single value) : System.Void`  

```csharp
private System.Void SetStartingTime(System.Single value);
```

- `private SetStartingYear(System.Int32 value) : System.Void`  

```csharp
private System.Void SetStartingYear(System.Int32 value);
```

- `private ShareMap(Game.Assets.MapMetadata map) : System.Void`  

```csharp
private System.Void ShareMap(Game.Assets.MapMetadata map);
```

- `public ShowLoadMapPanel() : System.Void`  

```csharp
public System.Void ShowLoadMapPanel();
```

- `private ShowPreviewPicker() : System.Void`  

```csharp
private System.Void ShowPreviewPicker();
```

- `public ShowSaveMapPanel() : System.Void`  

```csharp
public System.Void ShowSaveMapPanel();
```

- `private ShowShareMapPanel() : System.Void`  

```csharp
private System.Void ShowShareMapPanel();
```

- `private ShowThumbnailPicker() : System.Void`  

```csharp
private System.Void ShowThumbnailPicker();
```

- `private ToggleMapTileSelection() : System.Void`  

```csharp
private System.Void ToggleMapTileSelection();
```

- `private TryGetAssetItem(Game.Assets.MapMetadata asset, Game.UI.Editor.AssetItem& item) : System.Boolean`  

```csharp
private System.Boolean TryGetAssetItem(Game.Assets.MapMetadata asset, Game.UI.Editor.AssetItem& item);
```

- `private UpdateMapTileButton(System.String text) : System.Void`  

```csharp
private System.Void UpdateMapTileButton(System.String text);
```

- `private UpdateStartingTiles() : System.Void`  

```csharp
private System.Void UpdateStartingTiles();
```


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


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
[Preserve]
	public MapPanelSystem()
	{
	}
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
private void ApplyTime()
	{
		TimeData component = new TimeData
		{
			m_StartingYear = m_StartingYear,
			m_StartingMonth = (byte)(m_StartingMonth - 1),
			TimeOffset = m_StartingTime
		};
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		Entity singletonEntity = m_TimeQuery.GetSingletonEntity();
		entityCommandBuffer.SetComponent(singletonEntity, component);
	}
```

- `private CaptureCameraProperties() : System.Void`  

```csharp
private void CaptureCameraProperties()
	{
		if (CameraController.TryGet(out var cameraController))
		{
			m_CityConfigurationSystem.m_CameraPivot = cameraController.pivot;
			m_CityConfigurationSystem.m_CameraAngle = cameraController.angle;
			m_CityConfigurationSystem.m_CameraZoom = cameraController.zoom;
		}
	}
```

- `private FetchThemes() : System.Void`  

```csharp
private void FetchThemes()
	{
		List<IconButton> list = new List<IconButton>();
		NativeArray<Entity> nativeArray = m_ThemeQuery.ToEntityArray(Allocator.Temp);
		foreach (Entity theme in nativeArray)
		{
			ThemePrefab prefab = m_PrefabSystem.GetPrefab<ThemePrefab>(theme);
			list.Add(new IconButton
			{
				icon = (ImageSystem.GetIcon(prefab) ?? "Media/Editor/Object.svg"),
				tooltip = LocalizedString.Id("Assets.THEME[" + prefab.name + "]"),
				action = delegate
				{
					m_CityConfigurationSystem.defaultTheme = theme;
				},
				selected = () => m_CityConfigurationSystem.defaultTheme == theme
			});
		}
		nativeArray.Dispose();
		m_ThemeButtonGroup.children = list.ToArray();
	}
```

- `private FetchTime() : System.Void`  

```csharp
private void FetchTime()
	{
		TimeData singleton = m_TimeQuery.GetSingleton<TimeData>();
		m_StartingYear = singleton.m_StartingYear;
		m_CurrentYearAsStartingYear = true;
		m_StartingMonth = singleton.m_StartingMonth + 1;
		m_StartingTime = singleton.TimeOffset;
	}
```

- `private GetMapInfo(Game.Assets.MapInfo merge = null) : Game.Assets.MapInfo`  

```csharp
private MapInfo GetMapInfo(MapInfo merge = null)
	{
		MapInfo obj = merge ?? new MapInfo();
		obj.displayName = m_MapMetadataSystem.mapName;
		obj.theme = m_MapMetadataSystem.theme;
		obj.temperatureRange = m_MapMetadataSystem.temperatureRange;
		obj.cloudiness = m_MapMetadataSystem.cloudiness;
		obj.precipitation = m_MapMetadataSystem.precipitation;
		obj.latitude = m_MapMetadataSystem.latitude;
		obj.longitude = m_MapMetadataSystem.longitude;
		obj.area = m_MapMetadataSystem.area;
		obj.surfaceWaterAvailability = m_MapMetadataSystem.surfaceWaterAvailability;
		obj.groundWaterAvailability = m_MapMetadataSystem.groundWaterAvailability;
		obj.resources = m_MapMetadataSystem.resources;
		obj.connections = m_MapMetadataSystem.connections;
		obj.nameAsCityName = m_MapNameAsCityName;
		obj.startingYear = (m_CurrentYearAsStartingYear ? (-1) : m_StartingYear);
		obj.buildableLand = m_MapMetadataSystem.buildableLand;
		return obj;
	}
```

- `private GetMaps() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
private IEnumerable<AssetItem> GetMaps()
	{
		foreach (MapMetadata asset in AssetDatabase.global.GetAssets(default(SearchFilter<MapMetadata>)))
		{
			using (asset)
			{
				if (!(asset.database is AssetDatabase<Colossal.IO.AssetDatabase.Game>) && TryGetAssetItem(asset, out var item))
				{
					yield return item;
				}
			}
		}
	}
```

- `private InitLocalization(Game.Assets.MapMetadata asset = null) : System.Void`  

```csharp
private void InitLocalization(MapMetadata asset = null)
	{
		if (asset != null)
		{
			m_MapNameLocalization.Initialize(asset.target.localeAssets, $"Maps.MAP_TITLE[{asset.target.displayName}]");
			m_MapDescriptionLocalization.Initialize(asset.target.localeAssets, $"Maps.MAP_DESCRIPTION[{asset.target.displayName}]");
		}
		else
		{
			m_MapNameLocalization.Initialize();
			m_MapDescriptionLocalization.Initialize();
		}
	}
```

- `private InitPreview(Game.Assets.MapMetadata asset = null) : System.Void`  

```csharp
private void InitPreview(MapMetadata asset = null)
	{
		m_Preview.Set(asset?.target?.preview, MenuHelpers.defaultPreview);
		m_Thumbnail.Set(asset?.target?.thumbnail, MenuHelpers.defaultThumbnail);
	}
```

- `public LoadMap(Colossal.Hash128 guid) : System.Threading.Tasks.Task`  

```csharp
public async Task LoadMap(Colossal.Hash128 guid)
	{
		CloseSubPanel();
		if (AssetDatabase.global.TryGetAsset(guid, out MapMetadata asset))
		{
			await GameManager.instance.Load(GameMode.Editor, Purpose.LoadMap, asset).ConfigureAwait(continueOnCapturedContext: false);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_Generator = new EditorGenerator();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_SaveGameSystem = base.World.GetOrCreateSystemManaged<SaveGameSystem>();
		m_MapMetadataSystem = base.World.GetOrCreateSystemManaged<MapMetadataSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_MapTilePurchaseSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_MapRequirementSystem = base.World.GetOrCreateSystemManaged<MapRequirementSystem>();
		m_AssetUploadPanel = base.World.GetOrCreateSystemManaged<EditorAssetUploadPanel>();
		m_TimeQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_ThemeQuery = GetEntityQuery(ComponentType.ReadOnly<ThemeData>());
		m_Preview = new PreviewInfo(new IconButton
		{
			action = ShowPreviewPicker
		});
		m_Thumbnail = new PreviewInfo(new IconButton
		{
			action = ShowThumbnailPicker
		});
		title = "Editor.MAP";
		IWidget[] array = new IWidget[2];
		IWidget[] array2 = new IWidget[2];
		EditorSection editorSection = new EditorSection
		{
			displayName = "Editor.MAP_SETTINGS",
			expanded = true
		};
		EditorSection editorSection2 = editorSection;
		IWidget[] obj = new IWidget[14]
		{
			new Group
			{
				displayName = "Editor.MAP_NAME",
				tooltip = "Editor.MAP_NAME_TOOLTIP",
				children = new IWidget[1] { m_MapNameLocalization = new LocalizationField("Editor.MAP_NAME") }
			},
			new Group
			{
				displayName = "Editor.MAP_DESCRIPTION",
				tooltip = "Editor.MAP_DESCRIPTION_TOOLTIP",
				children = new IWidget[1] { m_MapDescriptionLocalization = new LocalizationField("Editor.MAP_DESCRIPTION") }
			},
			new ToggleField
			{
				displayName = "Editor.MAP_NAME_AS_DEFAULT",
				tooltip = "Editor.MAP_NAME_AS_DEFAULT_TOOLTIP",
				accessor = new DelegateAccessor<bool>(() => m_MapNameAsCityName, delegate(bool value)
				{
					m_MapNameAsCityName = value;
				})
			},
			new Divider(),
			new IntInputField
			{
				displayName = "Editor.STARTING_YEAR",
				tooltip = "Editor.STARTING_YEAR_TOOLTIP",
				disabled = () => m_CurrentYearAsStartingYear,
				min = 0,
				max = 3000,
				accessor = new DelegateAccessor<int>(() => (!m_CurrentYearAsStartingYear) ? m_StartingYear : DateTime.Now.Year, SetStartingYear)
			},
			new ToggleField
			{
				displayName = "Editor.CURRENT_YEAR_AS_DEFAULT",
				tooltip = "Editor.CURRENT_YEAR_AS_DEFAULT_TOOLTIP",
				accessor = new DelegateAccessor<bool>(() => m_CurrentYearAsStartingYear, delegate(bool value)
				{
					m_CurrentYearAsStartingYear = value;
				})
			},
			new IntInputField
			{
				displayName = "Editor.STARTING_MONTH",
				tooltip = "Editor.STARTING_MONTH_TOOLTIP",
				min = 1,
				max = 12,
				accessor = new DelegateAccessor<int>(() => m_StartingMonth, SetStartingMonth)
			},
			new TimeSliderField
			{
				displayName = "Editor.STARTING_TIME",
				tooltip = "Editor.STARTING_TIME_TOOLTIP",
				min = 0f,
				max = 0.99930555f,
				accessor = new DelegateAccessor<float>(() => m_StartingTime, SetStartingTime)
			},
			new Group
			{
				displayName = "Editor.CAMERA_STARTING_POSITION",
				tooltip = "Editor.CAMERA_STARTING_POSITION_TOOLTIP",
				children = new IWidget[4]
				{
					new Float3InputField
					{
						displayName = "Editor.CAMERA_PIVOT",
						tooltip = "Editor.CAMERA_PIVOT_TOOLTIP",
						accessor = new DelegateAccessor<float3>(() => m_CityConfigurationSystem.m_CameraPivot, delegate(float3 value)
						{
							m_CityConfigurationSystem.m_CameraPivot = value;
						})
					},
					new Float2InputField
					{
						displayName = "Editor.CAMERA_ANGLE",
						tooltip = "Editor.CAMERA_ANGLE_TOOLTIP",
						accessor = new DelegateAccessor<float2>(() => m_CityConfigurationSystem.m_CameraAngle, delegate(float2 value)
						{
							m_CityConfigurationSystem.m_CameraAngle = value;
						})
					},
					new FloatInputField
					{
						displayName = "Editor.CAMERA_ZOOM",
						tooltip = "Editor.CAMERA_ZOOM_TOOLTIP",
						accessor = new DelegateAccessor<double>(() => m_CityConfigurationSystem.m_CameraZoom, delegate(double value)
						{
							m_CityConfigurationSystem.m_CameraZoom = (float)value;
						})
					},
					new Button
					{
						displayName = "Editor.CAPTURE_CAMERA_POSITION",
						tooltip = "Editor.CAPTURE_CAMERA_POSITION_TOOLTIP",
						action = CaptureCameraProperties
					}
				}
			},
			null,
			null,
			null,
			null,
			null
		};
		Button obj2 = new Button
		{
			displayName = kSelectStartingTilesPrompt,
			action = ToggleMapTileSelection
		};
		Button button = obj2;
		m_MapTileSelectionButton = obj2;
		obj[9] = button;
		obj[10] = new EditorSection
		{
			displayName = "Editor.THEME",
			tooltip = "Editor.THEME_TOOLTIP",
			expanded = true,
			children = new IWidget[1] { m_ThemeButtonGroup = new IconButtonGroup() }
		};
		obj[11] = new EditorSection
		{
			displayName = "Editor.CONTENT_PREREQUISITES",
			tooltip = "Editor.CONTENT_PREREQUISITES_TOOLTIP",
			expanded = true,
			children = new IWidget[1] { m_RequiredListWidget = EditorGenerator.NamedWidget(m_Generator.TryBuildList(new ObjectAccessor<PrefabEntityListWrapper<ContentPrefab>>(new PrefabEntityListWrapper<ContentPrefab>(m_CityConfigurationSystem.requiredContent, m_PrefabSystem), readOnly: false), 0, null, Array.Empty<object>()), "Editor.REQUIREMENTS", "Editor.REQUIREMENTS_TOOLTIP") }
		};
		obj[12] = new Group
		{
			displayName = "Editor.PREVIEW",
			tooltip = "Editor.PREVIEW_TOOLTIP",
			children = new IWidget[1] { m_Preview.button }
		};
		obj[13] = new Group
		{
			displayName = "Editor.THUMBNAIL",
			tooltip = "Editor.THUMBNAIL_TOOLTIP",
			children = new IWidget[1] { m_Thumbnail.button }
		};
		editorSection2.children = obj;
		array2[0] = editorSection;
		array2[1] = new EditorSection
		{
			displayName = "Editor.CHECKLIST",
			tooltip = "Editor.CHECKLIST_TOOLTIP",
			children = new IWidget[2]
			{
				new Group
				{
					displayName = "Editor.CHECKLIST_REQUIRED",
					tooltip = "Editor.CHECKLIST_REQUIRED_TOOLTIP",
					children = new IWidget[4]
					{
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_STARTING_TILES",
							tooltip = "Editor.CHECKLIST_STARTING_TILES_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.hasStartingArea)
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_WATER",
							tooltip = "Editor.CHECKLIST_WATER_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.StartingAreaHasResource(MapFeature.SurfaceWater) || m_MapRequirementSystem.StartingAreaHasResource(MapFeature.GroundWater))
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_ROAD_CONNECTION",
							tooltip = "Editor.CHECKLIST_ROAD_CONNECTION_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.roadConnection)
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_NAME",
							tooltip = "Editor.CHECKLIST_NAME_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapNameLocalization.IsValid())
						}
					}
				},
				new Group
				{
					displayName = "Editor.CHECKLIST_OPTIONAL",
					tooltip = "Editor.CHECKLIST_OPTIONAL_TOOLTIP",
					children = new IWidget[7]
					{
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_TRAIN_CONNECTION",
							tooltip = "Editor.CHECKLIST_TRAIN_CONNECTION_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.trainConnection)
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_AIR_CONNECTION",
							tooltip = "Editor.CHECKLIST_AIR_CONNECTION_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.airConnection)
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_ELECTRICITY_CONNECTION",
							tooltip = "Editor.CHECKLIST_ELECTRICITY_CONNECTION_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.electricityConnection)
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_OIL",
							tooltip = "Editor.CHECKLIST_OIL_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.MapHasResource(MapFeature.Oil))
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_ORE",
							tooltip = "Editor.CHECKLIST_ORE_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.MapHasResource(MapFeature.Ore))
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_FOREST",
							tooltip = "Editor.CHECKLIST_FOREST_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.MapHasResource(MapFeature.Forest))
						},
						new ToggleField
						{
							displayName = "Editor.CHECKLIST_FERTILE",
							tooltip = "Editor.CHECKLIST_FERTILE_TOOLTIP",
							disabled = () => true,
							accessor = new DelegateAccessor<bool>(() => m_MapRequirementSystem.MapHasResource(MapFeature.FertileLand))
						}
					}
				}
			}
		};
		array[0] = Scrollable.WithChildren(array2);
		array[1] = ButtonRow.WithChildren(new Button[3]
		{
			new Button
			{
				displayName = "Editor.LOAD_MAP",
				tooltip = "Editor.LOAD_MAP_TOOLTIP",
				action = ShowLoadMapPanel
			},
			new Button
			{
				displayName = "Editor.SAVE_MAP",
				tooltip = "Editor.SAVE_MAP_TOOLTIP",
				action = ShowSaveMapPanel
			},
			new Button
			{
				displayName = "GameListScreen.GAME_OPTION[shareMap]",
				action = ShowShareMapPanel,
				hidden = () => m_Platform == null || !m_Platform.cachedLoggedIn
			}
		});
		children = array;
		m_Platform = PlatformManager.instance.GetPSI<PdxSdkPlatform>("PdxSdk");
		PlatformManager.instance.onPlatformRegistered += delegate(IPlatformServiceIntegration psi)
		{
			if (psi is PdxSdkPlatform platform)
			{
				m_Platform = platform;
			}
		};
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (serializationContext.purpose == Purpose.NewMap || serializationContext.purpose == Purpose.LoadMap)
		{
			if (m_TimeQuery.IsEmptyIgnoreFilter)
			{
				Entity entity = base.EntityManager.CreateEntity();
				base.EntityManager.AddComponentData(entity, new TimeData
				{
					m_StartingYear = DateTime.Now.Year,
					m_StartingMonth = 6,
					m_StartingHour = 6,
					m_StartingMinutes = 0
				});
			}
			m_RequiredListWidget.SetPropertiesChanged();
			FetchThemes();
			FetchTime();
			m_CurrentSourceDataGuid = serializationContext.instigatorGuid;
			MapMetadata asset = AssetDatabase.global.GetAsset<MapMetadata>(m_CurrentSourceDataGuid);
			m_MapMetadataSystem.mapName = ((!string.IsNullOrEmpty(asset?.target?.displayName)) ? asset.target.displayName : Guid.NewGuid().ToString());
			InitLocalization(asset);
			InitPreview(asset);
		}
	}
```

- `private OnLoadMap(Colossal.Hash128 guid) : System.Void`  

```csharp
private void OnLoadMap(Colossal.Hash128 guid)
	{
		GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new ConfirmationDialog(null, "Common.DIALOG_MESSAGE[ProgressLoss]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), delegate(int ret)
		{
			if (ret == 0)
			{
				LoadMap(guid);
			}
		});
	}
```

- `private OnSaveMap(System.String fileName, System.Nullable<Colossal.Hash128> overwriteGuid, System.Action<Game.Assets.MapMetadata> callback = null) : System.Void`  

```csharp
private void OnSaveMap(string fileName, Colossal.Hash128? overwriteGuid, Action<MapMetadata> callback = null)
	{
		m_MapMetadataSystem.Update();
		if (overwriteGuid.HasValue)
		{
			GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new ConfirmationDialog(null, "Common.DIALOG_MESSAGE[OverwriteMap]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), delegate(int ret)
			{
				if (ret == 0)
				{
					CloseSubPanel();
					MapMetadata asset = AssetDatabase.global.GetAsset<MapMetadata>(overwriteGuid.Value);
					SourceMeta meta = asset.GetMeta();
					SaveMap(meta.displayName, overwriteGuid.Value, asset.target, asset.database, AssetDataPath.Create(meta.subPath, meta.fileName), asset.database != AssetDatabase.game, callback);
				}
			});
		}
		else
		{
			CloseSubPanel();
			SaveMap(fileName, Colossal.Hash128.Empty, null, AssetDatabase.user, SaveHelpers.GetAssetDataPath<MapMetadata>(AssetDatabase.user, fileName), embedLocalization: true, callback);
		}
	}
```

- `private OnSelectPreview(Colossal.Hash128 guid) : System.Void`  

```csharp
private void OnSelectPreview(Colossal.Hash128 guid)
	{
		m_Preview.Set(AssetDatabase.global.GetAsset<ImageAsset>(guid));
		CloseSubPanel();
	}
```

- `private OnSelectThumbnail(Colossal.Hash128 guid) : System.Void`  

```csharp
private void OnSelectThumbnail(Colossal.Hash128 guid)
	{
		m_Thumbnail.Set(AssetDatabase.global.GetAsset<ImageAsset>(guid));
		CloseSubPanel();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		base.activeSubPanel = null;
		m_MapRequirementSystem.Enabled = true;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		m_MapTilePurchaseSystem.selecting = false;
		m_MapRequirementSystem.Enabled = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		m_MapRequirementSystem.Update();
		if (m_MapTilePurchaseSystem.selecting)
		{
			UpdateMapTileButton(kStopSelectingStartingTilesPrompt);
			UpdateStartingTiles();
		}
		else
		{
			UpdateMapTileButton(kSelectStartingTilesPrompt);
		}
	}
```

- `private SaveClimate(Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : Colossal.IO.AssetDatabase.PrefabAsset`  

```csharp
private PrefabAsset SaveClimate(ILocalAssetDatabase database)
	{
		ClimateSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		ClimatePrefab prefab = m_PrefabSystem.GetPrefab<ClimatePrefab>(orCreateSystemManaged.currentClimate);
		if (prefab.builtin)
		{
			return null;
		}
		PrefabBase prefabBase = prefab.Clone();
		prefabBase.name = prefab.name;
		prefabBase.asset = database.AddAsset<PrefabAsset, ScriptableObject>(prefabBase.name, prefabBase);
		prefabBase.asset.Save();
		return prefabBase.asset;
	}
```

- `private SaveLocalization(Colossal.IO.AssetDatabase.ILocalAssetDatabase db, System.String fileName) : Colossal.IO.AssetDatabase.LocaleAsset[]`  

```csharp
private LocaleAsset[] SaveLocalization(ILocalAssetDatabase db, string fileName)
	{
		Dictionary<string, LocaleData> dictionary = new Dictionary<string, LocaleData>();
		m_MapNameLocalization.BuildLocaleData($"Maps.MAP_TITLE[{m_MapMetadataSystem.mapName}]", dictionary, m_MapMetadataSystem.mapName);
		m_MapDescriptionLocalization.BuildLocaleData($"Maps.MAP_DESCRIPTION[{m_MapMetadataSystem.mapName}]", dictionary);
		List<LocaleAsset> list = new List<LocaleAsset>(dictionary.Keys.Count);
		foreach (string key in dictionary.Keys)
		{
			LocaleAsset localeAsset = db.AddAsset<LocaleAsset>(fileName + "_" + key);
			LocalizationManager localizationManager = GameManager.instance.localizationManager;
			localeAsset.SetData(dictionary[key], localizationManager.LocaleIdToSystemLanguage(key), GameManager.instance.localizationManager.GetLocalizedName(key));
			localeAsset.Save();
			list.Add(localeAsset);
		}
		return list.ToArray();
	}
```

- `public SaveMap(System.String fileName, Colossal.Hash128 overwriteGuid, Game.Assets.MapInfo existing, Colossal.IO.AssetDatabase.ILocalAssetDatabase finalDb, Colossal.IO.AssetDatabase.AssetDataPath packagePath, System.Boolean embedLocalization, System.Action<Game.Assets.MapMetadata> callback = null) : System.Threading.Tasks.Task`  

```csharp
public async Task SaveMap(string fileName, Colossal.Hash128 overwriteGuid, MapInfo existing, ILocalAssetDatabase finalDb, AssetDataPath packagePath, bool embedLocalization, Action<MapMetadata> callback = null)
	{
		m_MapMetadataSystem.mapName = fileName;
		using ILocalAssetDatabase db = AssetDatabase.GetTransient(0L);
		MapInfo info = GetMapInfo(existing);
		AssetDataPath name = fileName;
		MapMetadata meta = db.AddAsset<MapMetadata>(name, overwriteGuid);
		meta.target = info;
		MapData mapData = (info.mapData = db.AddAsset<MapData>(name));
		info.climate = SaveClimate(db);
		m_CurrentSourceDataGuid = meta.id;
		m_SaveGameSystem.context = new Context(Purpose.SaveMap, Version.current, m_CurrentSourceDataGuid);
		m_SaveGameSystem.stream = mapData.GetWriteStream();
		await m_SaveGameSystem.RunOnce();
		string[] array = m_SaveGameSystem.referencedContent.Select((Entity x) => m_PrefabSystem.GetPrefabName(x)).ToArray();
		info.contentPrerequisites = ((array.Length != 0) ? array : null);
		if (m_Preview.CopyToTextureAsset(db, m_Preview.name, out var asset))
		{
			asset.Save();
			info.preview = asset;
		}
		TextureAsset asset2;
		if (m_Preview.Equals(m_Thumbnail))
		{
			info.thumbnail = asset;
		}
		else if (m_Thumbnail.CopyToTextureAsset(db, m_Thumbnail.name, out asset2))
		{
			asset2.Save();
			info.thumbnail = asset2;
		}
		if (embedLocalization)
		{
			info.localeAssets = SaveLocalization(db, fileName);
		}
		else
		{
			info.localeAssets = null;
		}
		meta.Save();
		using (AssetDatabase.global.DisableNotificationsScoped())
		{
			if (finalDb.Exists<PackageAsset>(packagePath, out var asset3))
			{
				Identifier id = asset3.id;
				finalDb.DeleteAsset(asset3);
				asset3 = finalDb.AddAsset<PackageAsset, ILocalAssetDatabase>(packagePath, db, id);
				asset3.Save();
			}
			else
			{
				asset3 = finalDb.AddAsset(packagePath, db);
				asset3.Save();
			}
		}
		if (finalDb.dataSource.hasCache)
		{
			string text = await finalDb.ResaveCache();
			if (!string.IsNullOrWhiteSpace(text))
			{
				UnityEngine.Debug.Log(text);
			}
		}
		GameManager.instance.RunOnMainThread(delegate
		{
			PlatformManager.instance.UnlockAchievement(Game.Achievements.Achievements.Cartography);
			InitPreview(meta);
			if (callback != null)
			{
				callback(meta);
			}
		});
	}
```

- `private SetStartingMonth(System.Int32 value) : System.Void`  

```csharp
private void SetStartingMonth(int value)
	{
		m_StartingMonth = value;
		ApplyTime();
	}
```

- `private SetStartingTime(System.Single value) : System.Void`  

```csharp
private void SetStartingTime(float value)
	{
		m_StartingTime = value;
		ApplyTime();
	}
```

- `private SetStartingYear(System.Int32 value) : System.Void`  

```csharp
private void SetStartingYear(int value)
	{
		m_StartingYear = value;
		ApplyTime();
	}
```

- `private ShareMap(Game.Assets.MapMetadata map) : System.Void`  

```csharp
private void ShareMap(MapMetadata map)
	{
		m_AssetUploadPanel.Show(map);
		base.activeSubPanel = m_AssetUploadPanel;
	}
```

- `public ShowLoadMapPanel() : System.Void`  

```csharp
public void ShowLoadMapPanel()
	{
		base.activeSubPanel = new LoadAssetPanel("Editor.LOAD_MAP", GetMaps(), OnLoadMap, base.CloseSubPanel);
	}
```

- `private ShowPreviewPicker() : System.Void`  

```csharp
private void ShowPreviewPicker()
	{
		base.activeSubPanel = new LoadAssetPanel("Editor.PREVIEW", EditorPrefabUtils.GetUserImages(), OnSelectPreview, base.CloseSubPanel);
	}
```

- `public ShowSaveMapPanel() : System.Void`  

```csharp
public void ShowSaveMapPanel()
	{
		base.activeSubPanel = new SaveAssetPanel("Editor.SAVE_MAP", GetMaps(), m_CurrentSourceDataGuid, delegate(string name, Colossal.Hash128? overwriteGuid)
		{
			OnSaveMap(name, overwriteGuid);
		}, base.CloseSubPanel);
	}
```

- `private ShowShareMapPanel() : System.Void`  

```csharp
private void ShowShareMapPanel()
	{
		base.activeSubPanel = new SaveAssetPanel("Editor.SAVE_MAP_SHARE", GetMaps(), m_CurrentSourceDataGuid, delegate(string name, Colossal.Hash128? overwriteGuid)
		{
			OnSaveMap(name, overwriteGuid, ShareMap);
		}, base.CloseSubPanel, "Editor.SAVE_SHARE");
	}
```

- `private ShowThumbnailPicker() : System.Void`  

```csharp
private void ShowThumbnailPicker()
	{
		base.activeSubPanel = new LoadAssetPanel("Editor.THUMBNAIL", EditorPrefabUtils.GetUserImages(), OnSelectThumbnail, base.CloseSubPanel);
	}
```

- `private ToggleMapTileSelection() : System.Void`  

```csharp
private void ToggleMapTileSelection()
	{
		m_MapTilePurchaseSystem.selecting = !m_MapTilePurchaseSystem.selecting;
	}
```

- `private TryGetAssetItem(Game.Assets.MapMetadata asset, Game.UI.Editor.AssetItem& item) : System.Boolean`  

```csharp
private bool TryGetAssetItem(MapMetadata asset, out AssetItem item)
	{
		try
		{
			MapInfo target = asset.target;
			SourceMeta meta = asset.GetMeta();
			item = new AssetItem
			{
				guid = asset.id,
				fileName = meta.fileName,
				displayName = meta.displayName,
				image = target.thumbnail.ToUri(MenuHelpers.defaultPreview),
				badge = ((meta.remoteStorageSourceName != "Local") ? meta.remoteStorageSourceName : null)
			};
			return true;
		}
		catch (Exception exception)
		{
			base.log.Error(exception);
			item = null;
		}
		return false;
	}
```

- `private UpdateMapTileButton(System.String text) : System.Void`  

```csharp
private void UpdateMapTileButton(string text)
	{
		if (m_MapTileSelectionButton.displayName.value != text)
		{
			m_MapTileSelectionButton.displayName = text;
			m_MapTileSelectionButton.SetPropertiesChanged();
		}
	}
```

- `private UpdateStartingTiles() : System.Void`  

```csharp
private void UpdateStartingTiles()
	{
	}
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


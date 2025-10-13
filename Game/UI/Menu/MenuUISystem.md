# Game.UI.Menu.MenuUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MenuUISystem : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.UI.MapMetadataSystem m_MapMetadataSystem;
    private Game.UI.Menu.StandaloneAssetUploadPanelUISystem m_AssetUploadPanelUISystem;
    private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
    private Game.Prefabs.Modes.GameModeSystem m_GameModeSystem;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ActiveScreenBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>> m_ThemesBinding;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.MapInfo>> m_MapsBinding;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.Int32>> m_AvailableMapFilters;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_SelectedMapFilter;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>> m_GameModesBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_CurrentGameModeBinding;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.SaveInfo>> m_SavesBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SavePreviewBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_LastSaveNameBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_SaveGameSlotsBinding;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.Menu.MenuUISystem+SaveabilityStatus> m_SaveabilityBinding;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding;
    private Game.UI.Menu.MenuUISystem+DefaultGameOptions m_DefaultGameOptions;
    private Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings m_PreviewSettings;
    private Unity.Entities.EntityQuery m_XPQuery;
    private System.Boolean m_IsLoading;
    private System.String m_LastSelectedCloudTarget;
    private Game.PSI.PdxSdk.PdxModsUI m_ModsUI;
    private static System.Int32 s_PreviewId;
    private static const System.String kPreviewName;
    private static const System.Int32 kPreviewWidth;
    private static const System.Int32 kPreviewHeight;
    private static const System.String kGroup;

    public Game.UI.Menu.MenuUISystem+MenuScreen activeScreen { get; set; }

    public MenuUISystem();

    private System.String <OnCreate>b__36_0();
    private Game.UI.Menu.MenuUISystem+DefaultGameOptions <OnCreate>b__36_2();
    private System.Void <UpdateClouds>b__42_0();
    private System.Void ApplyOptions(System.String cityName, System.Collections.Generic.Dictionary<System.String, System.Boolean> options);
    private System.Void ApplyTutorialSettings(System.Boolean showTutorials, System.Boolean resetTutorials);
    private System.Threading.Tasks.Task ContinueGame();
    public System.Void DeleteSave(System.String guid);
    private System.Void ExitToMainMenu();
    private System.Boolean FilterMaps(Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo> meta);
    private System.Collections.Generic.HashSet<System.Int32> GetAvailableMapFilters();
    private System.Collections.Generic.List<System.String> GetCreditFiles();
    private Game.UI.Menu.MenuUISystem+GameOptions GetGameOptions();
    private Game.UI.Menu.MenuUISystem+SaveabilityStatus GetSaveabilityStatus();
    public Game.Assets.SaveInfo GetSaveInfo(System.Boolean autoSave);
    private System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo> GetThemes();
    private System.Threading.Tasks.Task<System.Boolean> HandlesOverwrite(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName);
    private static System.Boolean IsDefaultAsset(Colossal.IO.AssetDatabase.IAssetData asset);
    private System.Boolean IsEditorEnabled();
    private System.Boolean IsModdingEnabled();
    private System.Boolean IsModsUIActive();
    private System.Boolean IsPdxModsUIEnabled();
    private System.Threading.Tasks.Task LoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss);
    private System.Threading.Tasks.Task NewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args);
    private System.Void OnContentAvailabilityChanged(Game.Prefabs.ContentPrefab contentPrefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnPSModsUIClosed();
    private System.Void OnSaveGameScreenVisibilityChanged(System.Boolean visible);
    private System.Void OnSelectMapFilter(System.Int32 tab);
    protected virtual System.Void OnWorldReady();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Threading.Tasks.Task QuickLoad(System.Boolean dismiss);
    private System.Threading.Tasks.Task QuickSave();
    private System.Void SafeContinueGame();
    private System.Void SafeLoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss);
    private System.Void SafeNewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args);
    private System.Void SafeQuickLoad(System.Boolean dismiss);
    private System.Void SafeQuickSave();
    private System.Void SafeSaveGame(System.String saveName);
    private System.Boolean SaveExists(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String name, Colossal.IO.AssetDatabase.PackageAsset& asset);
    private System.Threading.Tasks.Task SaveGame(System.String saveName);
    private System.Void SelectCloudTarget(System.String cloudTarget);
    public System.Void ShareMap(System.String id);
    public System.Void ShareSave(System.String id);
    private System.Void ShowModsUI();
    private System.Void StartEditor();
    private System.Void UpdateClouds(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    private System.Void UpdateMaps(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    private System.Void UpdateMaps();
    private System.Void UpdateSaves();
    private System.Void UpdateSaves(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.UI.MapMetadataSystem m_MapMetadataSystem`  

```csharp
private Game.UI.MapMetadataSystem m_MapMetadataSystem;
```

- `private Game.UI.Menu.StandaloneAssetUploadPanelUISystem m_AssetUploadPanelUISystem`  

```csharp
private Game.UI.Menu.StandaloneAssetUploadPanelUISystem m_AssetUploadPanelUISystem;
```

- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  

```csharp
private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
```

- `private Game.Prefabs.Modes.GameModeSystem m_GameModeSystem`  

```csharp
private Game.Prefabs.Modes.GameModeSystem m_GameModeSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ActiveScreenBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ActiveScreenBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>> m_ThemesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>> m_ThemesBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.MapInfo>> m_MapsBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.MapInfo>> m_MapsBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.Int32>> m_AvailableMapFilters`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.Int32>> m_AvailableMapFilters;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SelectedMapFilter`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_SelectedMapFilter;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>> m_GameModesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>> m_GameModesBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_CurrentGameModeBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_CurrentGameModeBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.SaveInfo>> m_SavesBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.SaveInfo>> m_SavesBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SavePreviewBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SavePreviewBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_LastSaveNameBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_LastSaveNameBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SaveGameSlotsBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_SaveGameSlotsBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Menu.MenuUISystem+SaveabilityStatus> m_SaveabilityBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.Menu.MenuUISystem+SaveabilityStatus> m_SaveabilityBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding;
```

- `private Game.UI.Menu.MenuUISystem+DefaultGameOptions m_DefaultGameOptions`  

```csharp
private Game.UI.Menu.MenuUISystem+DefaultGameOptions m_DefaultGameOptions;
```

- `private Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings m_PreviewSettings`  

```csharp
private Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings m_PreviewSettings;
```

- `private Unity.Entities.EntityQuery m_XPQuery`  

```csharp
private Unity.Entities.EntityQuery m_XPQuery;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```

- `private System.String m_LastSelectedCloudTarget`  

```csharp
private System.String m_LastSelectedCloudTarget;
```

- `private Game.PSI.PdxSdk.PdxModsUI m_ModsUI`  

```csharp
private Game.PSI.PdxSdk.PdxModsUI m_ModsUI;
```

- `private static System.Int32 s_PreviewId`  

```csharp
private static System.Int32 s_PreviewId;
```

- `private static const System.String kPreviewName`  

```csharp
private static const System.String kPreviewName;
```

- `private static const System.Int32 kPreviewWidth`  

```csharp
private static const System.Int32 kPreviewWidth;
```

- `private static const System.Int32 kPreviewHeight`  

```csharp
private static const System.Int32 kPreviewHeight;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.UI.Menu.MenuUISystem+MenuScreen activeScreen { get; set }`  

```csharp
public Game.UI.Menu.MenuUISystem+MenuScreen activeScreen { get; set; }
```


## Constructors

- `public MenuUISystem()`  

```csharp
[Preserve]
	public MenuUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__36_0() : System.String`  

```csharp
private System.String <OnCreate>b__36_0();
```

- `private <OnCreate>b__36_2() : Game.UI.Menu.MenuUISystem+DefaultGameOptions`  

```csharp
private Game.UI.Menu.MenuUISystem+DefaultGameOptions <OnCreate>b__36_2();
```

- `private <UpdateClouds>b__42_0() : System.Void`  

```csharp
private System.Void <UpdateClouds>b__42_0();
```

- `private ApplyOptions(System.String cityName, System.Collections.Generic.Dictionary<System.String, System.Boolean> options) : System.Void`  

```csharp
private void ApplyOptions(string cityName, Dictionary<string, bool> options)
	{
		m_CityConfigurationSystem.overrideCityName = cityName;
		if (options != null)
		{
			UserState userState = SharedSettings.instance.userState;
			if (options.TryGetValue("leftHandTraffic", out var value))
			{
				bool leftHandTraffic = (m_CityConfigurationSystem.overrideLeftHandTraffic = value);
				userState.leftHandTraffic = leftHandTraffic;
			}
			if (options.TryGetValue("naturalDisasters", out var value2))
			{
				bool leftHandTraffic = (m_CityConfigurationSystem.overrideNaturalDisasters = value2);
				userState.naturalDisasters = leftHandTraffic;
			}
			if (options.TryGetValue("unlockAll", out var value3))
			{
				bool leftHandTraffic = (m_CityConfigurationSystem.overrideUnlockAll = value3);
				userState.unlockAll = leftHandTraffic;
			}
			if (options.TryGetValue("unlimitedMoney", out var value4))
			{
				bool leftHandTraffic = (m_CityConfigurationSystem.overrideUnlimitedMoney = value4);
				userState.unlimitedMoney = leftHandTraffic;
			}
			if (options.TryGetValue("unlockMapTiles", out var value5))
			{
				bool leftHandTraffic = (m_CityConfigurationSystem.overrideUnlockMapTiles = value5);
				userState.unlockMapTiles = leftHandTraffic;
			}
			userState.ApplyAndSave();
		}
	}
```

- `private ApplyTutorialSettings(System.Boolean showTutorials, System.Boolean resetTutorials) : System.Void`  

```csharp
private void ApplyTutorialSettings(bool showTutorials, bool resetTutorials)
	{
		SharedSettings.instance.gameplay.showTutorials = showTutorials;
		if (resetTutorials)
		{
			SharedSettings.instance.userState.ResetTutorials();
		}
	}
```

- `private ContinueGame() : System.Threading.Tasks.Task`  

```csharp
private async Task ContinueGame()
	{
		try
		{
			SaveGameMetadata lastSave = GameManager.instance.settings.userState.lastSaveGameMetadata;
			if (lastSave != null && lastSave.isValidSaveGame)
			{
				m_MapMetadataSystem.mapName = lastSave.target.mapName;
				PlatformManager.instance.achievementsEnabled = !lastSave.target.isReadonly;
				await GameManager.instance.Load(GameMode.Game, Purpose.LoadGame, lastSave);
				SaveInfo target = lastSave.target;
				m_LastSaveNameBinding.Update(target.autoSave ? null : target.displayName);
				if (!target.autoSave)
				{
					m_LastSelectedCloudTarget = target.metaData.database.dataSource.remoteStorageSourceName;
				}
			}
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `public DeleteSave(System.String guid) : System.Void`  

```csharp
public void DeleteSave(string guid)
	{
		try
		{
			SaveHelpers.DeleteSaveGame(m_SavesBinding.value.Find((SaveInfo x) => x.id == guid).metaData);
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private ExitToMainMenu() : System.Void`  

```csharp
private async void ExitToMainMenu()
	{
		try
		{
			m_CityConfigurationSystem.overrideLoadedOptions = false;
			m_CityConfigurationSystem.overrideThemeName = null;
			await GameManager.instance.MainMenu();
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private FilterMaps(Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo> meta) : System.Boolean`  

```csharp
private bool FilterMaps(Metadata<MapInfo> meta)
	{
		if (m_AvailableMapFilters.value.Count > 1)
		{
			if (m_SelectedMapFilter.value < 0)
			{
				return true;
			}
			bool flag = IsDefaultAsset(meta);
			if (m_SelectedMapFilter.value == 0 && flag)
			{
				return GameManager.instance.ArePrerequisitesMet(meta);
			}
			if (m_SelectedMapFilter.value == 1 && !flag)
			{
				return true;
			}
			return false;
		}
		return true;
	}
```

- `private GetAvailableMapFilters() : System.Collections.Generic.HashSet<System.Int32>`  

```csharp
private HashSet<int> GetAvailableMapFilters()
	{
		HashSet<int> hashSet = new HashSet<int>(2);
		foreach (Metadata<MapInfo> asset in AssetDatabase.global.GetAssets(default(SearchFilter<Metadata<MapInfo>>)))
		{
			hashSet.Add((!IsDefaultAsset(asset)) ? 1 : 0);
		}
		return hashSet;
	}
```

- `private GetCreditFiles() : System.Collections.Generic.List<System.String>`  

```csharp
private List<string> GetCreditFiles()
	{
		return new List<string> { "Media/Menu/Credits.md", "Media/Menu/Licenses.md" };
	}
```

- `private GetGameOptions() : Game.UI.Menu.MenuUISystem+GameOptions`  

```csharp
private GameOptions GetGameOptions()
	{
		return new GameOptions(m_CityConfigurationSystem);
	}
```

- `private GetSaveabilityStatus() : Game.UI.Menu.MenuUISystem+SaveabilityStatus`  

```csharp
private SaveabilityStatus GetSaveabilityStatus()
	{
		int count = MenuHelpers.GetAvailableCloudTargets().Count;
		return new SaveabilityStatus
		{
			canSave = (count > 0),
			reasonHash = ((count > 0) ? null : "NoLocations")
		};
	}
```

- `public GetSaveInfo(System.Boolean autoSave) : Game.Assets.SaveInfo`  

```csharp
public SaveInfo GetSaveInfo(bool autoSave)
	{
		CitySystem existingSystemManaged = base.World.GetExistingSystemManaged<CitySystem>();
		DateTime currentDateTime = base.World.GetExistingSystemManaged<TimeSystem>().GetCurrentDateTime();
		Population componentData = base.EntityManager.GetComponentData<Population>(existingSystemManaged.City);
		m_MapMetadataSystem.Update();
		return new SaveInfo
		{
			theme = m_MapMetadataSystem.theme,
			cityName = m_CityConfigurationSystem.cityName,
			population = componentData.m_Population,
			money = existingSystemManaged.moneyAmount,
			xp = existingSystemManaged.XP,
			simulationDate = new SimulationDateTime(currentDateTime.Year, currentDateTime.DayOfYear - 1, currentDateTime.Hour, currentDateTime.Minute),
			options = new Dictionary<string, bool>
			{
				{ "leftHandTraffic", m_CityConfigurationSystem.leftHandTraffic },
				{ "naturalDisasters", m_CityConfigurationSystem.naturalDisasters },
				{ "unlockAll", m_CityConfigurationSystem.unlockAll },
				{ "unlimitedMoney", m_CityConfigurationSystem.unlimitedMoney },
				{ "unlockMapTiles", m_CityConfigurationSystem.unlockMapTiles }
			},
			mapName = m_MapMetadataSystem.mapName,
			autoSave = autoSave,
			modsEnabled = m_CityConfigurationSystem.usedMods.ToArray(),
			gameMode = m_GameModeSystem.currentModeName
		};
	}
```

- `private GetThemes() : System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>`  

```csharp
private List<ThemeInfo> GetThemes()
	{
		return new List<ThemeInfo>
		{
			new ThemeInfo
			{
				id = "European",
				icon = "Media/Game/Themes/European.svg"
			},
			new ThemeInfo
			{
				id = "North American",
				icon = "Media/Game/Themes/North American.svg"
			}
		};
	}
```

- `private HandlesOverwrite(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private Task<bool> HandlesOverwrite(ILocalAssetDatabase database, string saveName)
	{
		if (SaveExists(database, saveName, out var _) && !SharedSettings.instance.userInterface.dismissedConfirmations.Contains("SaveGame"))
		{
			TaskCompletionSource<bool> tcs = new TaskCompletionSource<bool>();
			GameManager.instance.RegisterCancellationOnQuit(tcs, stateOnCancel: false);
			GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new DismissibleConfirmationDialog("Common.DIALOG_TITLE[Warning]", "Common.DIALOG_MESSAGE[Overwrite]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), delegate(int msg, bool dismiss)
			{
				if (msg == 0 && dismiss)
				{
					SharedSettings.instance.userInterface.AddDismissedConfirmation("SaveGame");
				}
				tcs.SetResult(msg == 0);
			});
			return tcs.Task;
		}
		return Task.FromResult(result: true);
	}
```

- `private static IsDefaultAsset(Colossal.IO.AssetDatabase.IAssetData asset) : System.Boolean`  

```csharp
private static bool IsDefaultAsset(IAssetData asset)
	{
		return asset.database is AssetDatabase<Colossal.IO.AssetDatabase.Game>;
	}
```

- `private IsEditorEnabled() : System.Boolean`  

```csharp
private bool IsEditorEnabled()
	{
		if (!GameManager.instance.configuration.disableModding)
		{
			return Platform.PC.IsPlatformSet(Application.platform);
		}
		return false;
	}
```

- `private IsModdingEnabled() : System.Boolean`  

```csharp
private bool IsModdingEnabled()
	{
		return !GameManager.instance.configuration.disableModding;
	}
```

- `private IsModsUIActive() : System.Boolean`  

```csharp
private bool IsModsUIActive()
	{
		return m_ModsUI.isActive;
	}
```

- `private IsPdxModsUIEnabled() : System.Boolean`  

```csharp
private bool IsPdxModsUIEnabled()
	{
		if (!GameManager.instance.configuration.disablePDXSDK)
		{
			return !GameManager.instance.configuration.disableModding;
		}
		return false;
	}
```

- `private LoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss) : System.Threading.Tasks.Task`  

```csharp
private async Task LoadGame(LoadGameArgs args, bool dismiss)
	{
		try
		{
			if (dismiss)
			{
				SharedSettings.instance.userInterface.AddDismissedConfirmation("LoadGame");
			}
			SaveInfo saveInfo = m_SavesBinding.value.Find((SaveInfo x) => x.id == args.saveId);
			m_MapMetadataSystem.mapName = saveInfo.mapName;
			m_CityConfigurationSystem.overrideLoadedOptions = true;
			m_CityConfigurationSystem.overrideThemeName = null;
			m_GameModeSystem.overrideMode = args.gameMode;
			ApplyOptions(args.cityName, args.options);
			PlatformManager.instance.achievementsEnabled = !saveInfo.isReadonly;
			await GameManager.instance.Load(GameMode.Game, Purpose.LoadGame, saveInfo.metaData);
			m_LastSaveNameBinding.Update(saveInfo.autoSave ? null : saveInfo.displayName);
			if (!saveInfo.autoSave)
			{
				m_LastSelectedCloudTarget = saveInfo.metaData.database.dataSource.remoteStorageSourceName;
			}
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private NewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args) : System.Threading.Tasks.Task`  

```csharp
private async Task NewGame(NewGameArgs args)
	{
		try
		{
			MapInfo mapInfo = m_MapsBinding.value.Find((MapInfo x) => x.id == args.mapId);
			m_MapMetadataSystem.mapName = mapInfo.displayName;
			m_CityConfigurationSystem.overrideLoadedOptions = true;
			m_CityConfigurationSystem.overrideThemeName = args.theme;
			m_GameModeSystem.overrideMode = args.gameMode;
			ApplyOptions(args.cityName, args.options);
			PlatformManager.instance.achievementsEnabled = true;
			m_TimeSystem.startingYear = ((mapInfo.startingYear != -1) ? mapInfo.startingYear : DateTime.Now.Year);
			await GameManager.instance.Load(GameMode.Game, Purpose.NewGame, mapInfo.metaData);
			m_LastSaveNameBinding.Update(null);
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private OnContentAvailabilityChanged(Game.Prefabs.ContentPrefab contentPrefab) : System.Void`  

```csharp
private void OnContentAvailabilityChanged(ContentPrefab contentPrefab)
	{
		GameManager.instance.userInterface.appBindings.UpdateOwnedPrerequisiteBinding();
		UpdateMaps();
		UpdateSaves();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_MapMetadataSystem = base.World.GetOrCreateSystemManaged<MapMetadataSystem>();
		m_AssetUploadPanelUISystem = base.World.GetOrCreateSystemManaged<StandaloneAssetUploadPanelUISystem>();
		m_GameScreenUISystem = base.World.GetOrCreateSystemManaged<GameScreenUISystem>();
		m_GameModeSystem = base.World.GetOrCreateSystemManaged<GameModeSystem>();
		m_DefaultGameOptions = new DefaultGameOptions();
		AssetDatabase.global.LoadSettings("Save Preview Settings", m_PreviewSettings);
		AddBinding(m_ActiveScreenBinding = new ValueBinding<int>("menu", "activeScreen", 0));
		AddBinding(new ValueBinding<bool>("menu", "canExitGame", !Application.isConsolePlatform));
		AddBinding(new ValueBinding<string>("menu", "gameVersion", Version.current.fullVersion));
		AddBinding(m_SavePreviewBinding = new ValueBinding<string>("menu", "savePreview", null, ValueWriters.Nullable(new StringWriter())));
		AddUpdateBinding(new GetterValueBinding<string>("menu", "mapName", () => m_MapMetadataSystem.mapName, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_LastSaveNameBinding = new ValueBinding<string>("menu", "lastSaveName", null, ValueWriters.Nullable(new StringWriter())));
		int initialValue = -1;
		AddBinding(m_SaveGameSlotsBinding = new ValueBinding<int>("menu", "saveGameSlots", initialValue));
		AddBinding(m_AvailableCloudTargetsBinding = new ValueBinding<List<string>>("menu", "availableCloudTargets", MenuHelpers.GetAvailableCloudTargets(), new ListWriter<string>()));
		AddUpdateBinding(m_SelectedCloudTargetBinding = new GetterValueBinding<string>("menu", "selectedCloudTarget", () => MenuHelpers.GetSanitizedCloudTarget(SharedSettings.instance.userState.lastCloudTarget).name, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_SaveabilityBinding = new GetterValueBinding<SaveabilityStatus>("menu", "saveabilityStatus", GetSaveabilityStatus, new ValueWriter<SaveabilityStatus>()));
		AddBinding(m_ThemesBinding = new GetterValueBinding<List<ThemeInfo>>("menu", "themes", GetThemes, new ListWriter<ThemeInfo>(new ValueWriter<ThemeInfo>())));
		AddBinding(m_MapsBinding = new ValueBinding<List<MapInfo>>("menu", "maps", new List<MapInfo>(), new ListWriter<MapInfo>(new ValueWriter<MapInfo>())));
		AddBinding(m_AvailableMapFilters = new ValueBinding<HashSet<int>>("menu", "availableMapFilters", GetAvailableMapFilters(), new CollectionWriter<int>()));
		AddBinding(m_SelectedMapFilter = new ValueBinding<int>("menu", "selectedMapFilter", 0));
		AddBinding(m_SavesBinding = new ValueBinding<List<SaveInfo>>("menu", "saves", new List<SaveInfo>(), new ListWriter<SaveInfo>(new ValueWriter<SaveInfo>())));
		AddBinding(m_GameModesBinding = new GetterValueBinding<List<GameModeInfo>>("menu", "gameModes", m_GameModeSystem.GetGameModeInfo, new ListWriter<GameModeInfo>(new ValueWriter<GameModeInfo>())));
		AddBinding(m_CurrentGameModeBinding = new ValueBinding<string>("menu", "gameMode", m_GameModeSystem.currentModeName));
		AddBinding(new GetterValueBinding<List<string>>("menu", "creditFiles", GetCreditFiles, new ListWriter<string>(new StringWriter())));
		AddUpdateBinding(new GetterValueBinding<DefaultGameOptions>("menu", "defaultGameOptions", () => m_DefaultGameOptions, new ValueWriter<DefaultGameOptions>()));
		AddUpdateBinding(new GetterValueBinding<GameOptions>("menu", "gameOptions", GetGameOptions, new ValueWriter<GameOptions>()));
		AddUpdateBinding(new GetterValueBinding<bool>("menu", "modsEnabled", ModManager.AreModsEnabled));
		AddUpdateBinding(new GetterValueBinding<bool>("menu", "pdxModsUIEnabled", IsPdxModsUIEnabled));
		AddBinding(new ValueBinding<bool>("menu", "hideModsUIButton", !IsModdingEnabled()));
		AddBinding(new ValueBinding<bool>("menu", "hideEditorButton", !IsEditorEnabled()));
		AddBinding(new ValueBinding<bool>("menu", "displayModdingBetaBanners", initialValue: true));
		AddUpdateBinding(new GetterValueBinding<bool>("menu", "hasCompletedTutorials", () => SharedSettings.instance.userState.shownTutorials.ContainsValue(value: true)));
		AddUpdateBinding(new GetterValueBinding<bool>("menu", "showTutorials", () => SharedSettings.instance.gameplay.showTutorials));
		AddUpdateBinding(new GetterValueBinding<bool>("menu", "dismissLoadGameConfirmation", () => SharedSettings.instance.userInterface.dismissedConfirmations.Contains("LoadGame")));
		AddUpdateBinding(new GetterValueBinding<bool>("menu", "isModsUIActive", IsModsUIActive));
		AddBinding(new TriggerBinding<int>("menu", "setActiveScreen", m_ActiveScreenBinding.Update));
		AddBinding(new TriggerBinding("menu", "continueGame", SafeContinueGame));
		AddBinding(new TriggerBinding<NewGameArgs>("menu", "newGame", SafeNewGame, new ValueReader<NewGameArgs>()));
		AddBinding(new TriggerBinding<LoadGameArgs, bool>("menu", "loadGame", SafeLoadGame, new ValueReader<LoadGameArgs>()));
		AddBinding(new TriggerBinding<string>("menu", "saveGame", SafeSaveGame));
		AddBinding(new TriggerBinding<string>("menu", "deleteSave", DeleteSave));
		AddBinding(new TriggerBinding<string>("menu", "shareSave", ShareSave));
		AddBinding(new TriggerBinding<string>("menu", "shareMap", ShareMap));
		AddBinding(new TriggerBinding("menu", "quicksave", SafeQuickSave));
		AddBinding(new TriggerBinding<bool>("menu", "quickload", SafeQuickLoad));
		AddBinding(new TriggerBinding("menu", "startEditor", StartEditor));
		AddBinding(new TriggerBinding("menu", "showPdxModsUI", ShowModsUI));
		AddBinding(new TriggerBinding("menu", "exitToMainMenu", ExitToMainMenu));
		AddBinding(new TriggerBinding<bool>("menu", "onSaveGameScreenVisibilityChanged", OnSaveGameScreenVisibilityChanged));
		AddBinding(new TriggerBinding<bool, bool>("menu", "applyTutorialSettings", ApplyTutorialSettings));
		AddBinding(new TriggerBinding<string>("menu", "selectCloudTarget", SelectCloudTarget));
		AddBinding(new TriggerBinding<int>("menu", "selectMapFilter", OnSelectMapFilter));
		m_XPQuery = GetEntityQuery(ComponentType.ReadOnly<XP>());
		m_LastSelectedCloudTarget = SharedSettings.instance.userState.lastCloudTarget;
		m_ModsUI = new PdxModsUI();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ModsUI.Dispose();
		AssetDatabase.global.onAssetDatabaseChanged.Unsubscribe(UpdateClouds);
		AssetDatabase.global.onAssetDatabaseChanged.Unsubscribe(UpdateMaps);
		AssetDatabase.global.onAssetDatabaseChanged.Unsubscribe(UpdateSaves);
		m_PrefabSystem.onContentAvailabilityChanged -= OnContentAvailabilityChanged;
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		string currentModeName = m_GameModeSystem.currentModeName;
		m_CurrentGameModeBinding.Update((currentModeName == string.Empty) ? "NormalMode" : currentModeName);
	}
```

- `private OnPSModsUIClosed() : System.Void`  

```csharp
private async void OnPSModsUIClosed()
	{
		HashSet<Mod> hashSet = await m_ModsUI.platform.GetModsInActivePlayset();
		if (hashSet != null && hashSet.Count > 0)
		{
			GameManager.instance.userInterface.paradoxBindings.OnPSModsUIClosed(null, m_ModsUI.platform.DeactivateActivePlayset, m_ModsUI.Show);
		}
	}
```

- `private OnSaveGameScreenVisibilityChanged(System.Boolean visible) : System.Void`  

```csharp
private void OnSaveGameScreenVisibilityChanged(bool visible)
	{
		if (visible)
		{
			m_SavePreviewBinding.Update(string.Format("{0}{1}/{2}?width={3}&height={4}&op={5}&{6}#{7}", "screencapture://", Camera.main.tag.ToLowerInvariant(), "SaveGamePanel", 680, 383, "Screenshot", m_PreviewSettings.ToUri(), s_PreviewId++));
		}
		else
		{
			m_SavePreviewBinding.Update(null);
		}
	}
```

- `private OnSelectMapFilter(System.Int32 tab) : System.Void`  

```csharp
private void OnSelectMapFilter(int tab)
	{
		m_SelectedMapFilter.Update(tab);
		UpdateMaps();
	}
```

- `protected virtual OnWorldReady() : System.Void`  

```csharp
protected override void OnWorldReady()
	{
		GameManager.instance.userInterface.appBindings.UpdateOwnedPrerequisiteBinding();
		m_PrefabSystem.onContentAvailabilityChanged += OnContentAvailabilityChanged;
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe(UpdateClouds, delegate(AssetChangedEventArgs args)
		{
			ChangeType change = args.change;
			return change == ChangeType.DatabaseRegistered || change == ChangeType.DatabaseUnregistered;
		}, AssetChangedEventArgs.Default);
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe<MapMetadata>(UpdateMaps, AssetChangedEventArgs.Default);
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe<SaveGameMetadata>(UpdateSaves, AssetChangedEventArgs.Default);
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		if (context.purpose == Purpose.Cleanup)
		{
			m_ActiveScreenBinding.Update(0);
		}
	}
```

- `private QuickLoad(System.Boolean dismiss) : System.Threading.Tasks.Task`  

```csharp
private async Task QuickLoad(bool dismiss)
	{
		try
		{
			if (dismiss)
			{
				SharedSettings.instance.userInterface.AddDismissedConfirmation("LoadGame");
			}
			if (MenuHelpers.hasPreviouslySavedGame)
			{
				await ContinueGame();
			}
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private QuickSave() : System.Threading.Tasks.Task`  

```csharp
private async Task QuickSave()
	{
		_ = 1;
		try
		{
			string saveName = m_LastSaveNameBinding.value;
			if (string.IsNullOrEmpty(saveName))
			{
				saveName = m_CityConfigurationSystem.cityName;
			}
			if (string.IsNullOrEmpty(saveName))
			{
				saveName = "SaveGame";
			}
			ILocalAssetDatabase targetDatabase = MenuHelpers.GetSanitizedCloudTarget(m_LastSelectedCloudTarget).db;
			if (targetDatabase.name != null)
			{
				RenderTexture savePreview = ScreenCaptureHelper.CreateRenderTarget("SaveGamePanel", 680, 383);
				ScreenCaptureHelper.CaptureScreenshot(Camera.main, savePreview, m_PreviewSettings);
				SaveInfo saveInfo = GetSaveInfo(autoSave: false);
				if (await HandlesOverwrite(targetDatabase, saveName))
				{
					await GameManager.instance.Save(saveName, saveInfo, targetDatabase, savePreview);
				}
				CoreUtils.Destroy(savePreview);
			}
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private SafeContinueGame() : System.Void`  

```csharp
private void SafeContinueGame()
	{
		TaskManager.instance.EnqueueTask("SaveLoadGame", ContinueGame, 1);
	}
```

- `private SafeLoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss) : System.Void`  

```csharp
private void SafeLoadGame(LoadGameArgs args, bool dismiss)
	{
		TaskManager.instance.EnqueueTask("SaveLoadGame", () => LoadGame(args, dismiss), 1);
	}
```

- `private SafeNewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args) : System.Void`  

```csharp
private void SafeNewGame(NewGameArgs args)
	{
		TaskManager.instance.EnqueueTask("SaveLoadGame", () => NewGame(args), 1);
	}
```

- `private SafeQuickLoad(System.Boolean dismiss) : System.Void`  

```csharp
private void SafeQuickLoad(bool dismiss)
	{
		TaskManager.instance.EnqueueTask("SaveLoadGame", () => QuickLoad(dismiss), 1);
	}
```

- `private SafeQuickSave() : System.Void`  

```csharp
private void SafeQuickSave()
	{
		TaskManager.instance.EnqueueTask("SaveLoadGame", QuickSave, 1);
	}
```

- `private SafeSaveGame(System.String saveName) : System.Void`  

```csharp
private void SafeSaveGame(string saveName)
	{
		TaskManager.instance.EnqueueTask("SaveLoadGame", () => SaveGame(saveName), 1);
	}
```

- `private SaveExists(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String name, Colossal.IO.AssetDatabase.PackageAsset& asset) : System.Boolean`  

```csharp
private bool SaveExists(ILocalAssetDatabase database, string name, out PackageAsset asset)
	{
		return database.Exists<PackageAsset>(SaveHelpers.GetAssetDataPath<SaveGameMetadata>(database, name), out asset);
	}
```

- `private SaveGame(System.String saveName) : System.Threading.Tasks.Task`  

```csharp
private async Task SaveGame(string saveName)
	{
		_ = 1;
		try
		{
			Texture savePreview = UIManager.defaultUISystem.userImagesManager.GetUserImageTarget("SaveGamePanel", 680, 383);
			ILocalAssetDatabase targetDatabase = MenuHelpers.GetSanitizedCloudTarget(SharedSettings.instance.userState.lastCloudTarget).db;
			SaveInfo saveInfo = GetSaveInfo(autoSave: false);
			if (await HandlesOverwrite(targetDatabase, saveName))
			{
				m_GameScreenUISystem.SetScreen(GameScreenUISystem.GameScreen.PauseMenu);
				await GameManager.instance.Save(saveName, saveInfo, targetDatabase, savePreview);
				m_LastSaveNameBinding.Update(saveName);
				m_LastSelectedCloudTarget = saveInfo.metaData.database.dataSource.remoteStorageSourceName;
			}
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private SelectCloudTarget(System.String cloudTarget) : System.Void`  

```csharp
private void SelectCloudTarget(string cloudTarget)
	{
		SharedSettings.instance.userState.lastCloudTarget = cloudTarget;
		_ = MenuHelpers.GetSanitizedCloudTarget(cloudTarget).db.dataSource.maxSupportedFileLength;
	}
```

- `public ShareMap(System.String id) : System.Void`  

```csharp
public void ShareMap(string id)
	{
		foreach (MapInfo item in m_MapsBinding.value)
		{
			if (item.id == id)
			{
				m_AssetUploadPanelUISystem.Show(item.metaData);
				break;
			}
		}
	}
```

- `public ShareSave(System.String id) : System.Void`  

```csharp
public void ShareSave(string id)
	{
		foreach (SaveInfo item in m_SavesBinding.value)
		{
			if (item.id == id)
			{
				m_AssetUploadPanelUISystem.Show(item.metaData);
				break;
			}
		}
	}
```

- `private ShowModsUI() : System.Void`  

```csharp
private void ShowModsUI()
	{
		if (PlatformManager.instance.hasUgcPrivilege)
		{
			if (Platform.PlayStation.IsPlatformSet(Application.platform))
			{
				GameManager.instance.userInterface.paradoxBindings.OnPSModsUIOpened(m_ModsUI.Show);
				m_ModsUI.platform.onModsUIClosed -= OnPSModsUIClosed;
				m_ModsUI.platform.onModsUIClosed += OnPSModsUIClosed;
			}
			else
			{
				m_ModsUI.Show();
			}
		}
	}
```

- `private StartEditor() : System.Void`  

```csharp
private async void StartEditor()
	{
		try
		{
			m_CityConfigurationSystem.overrideLoadedOptions = false;
			m_CityConfigurationSystem.overrideThemeName = null;
			await GameManager.instance.Load(GameMode.Editor, Purpose.NewMap).ConfigureAwait(continueOnCapturedContext: false);
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
	}
```

- `private UpdateClouds(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private void UpdateClouds(AssetChangedEventArgs args)
	{
		GameManager.instance.RunOnMainThread(delegate
		{
			m_AvailableCloudTargetsBinding.Update(MenuHelpers.GetAvailableCloudTargets());
			m_SelectedCloudTargetBinding.Update();
		});
	}
```

- `private UpdateMaps(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private void UpdateMaps()
	{
		m_AvailableMapFilters.Update(GetAvailableMapFilters());
		if (!m_AvailableMapFilters.value.Contains(m_SelectedMapFilter.value))
		{
			m_SelectedMapFilter.Update((m_AvailableMapFilters.value.Count > 0) ? m_AvailableMapFilters.value.First() : (-1));
		}
		MenuHelpers.UpdateMeta(m_MapsBinding, FilterMaps);
	}
```

- `private UpdateMaps() : System.Void`  

```csharp
private void UpdateMaps()
	{
		m_AvailableMapFilters.Update(GetAvailableMapFilters());
		if (!m_AvailableMapFilters.value.Contains(m_SelectedMapFilter.value))
		{
			m_SelectedMapFilter.Update((m_AvailableMapFilters.value.Count > 0) ? m_AvailableMapFilters.value.First() : (-1));
		}
		MenuHelpers.UpdateMeta(m_MapsBinding, FilterMaps);
	}
```

- `private UpdateSaves() : System.Void`  

```csharp
private void UpdateSaves(AssetChangedEventArgs args)
	{
		GameManager.instance.RunOnMainThread(UpdateSaves);
	}
```

- `private UpdateSaves(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private void UpdateSaves(AssetChangedEventArgs args)
	{
		GameManager.instance.RunOnMainThread(UpdateSaves);
	}
```


## Nested types

- `Game.UI.Menu.MenuUISystem+MapFilter`  
- `Game.UI.Menu.MenuUISystem+MenuScreen`  
- `Game.UI.Menu.MenuUISystem+ThemeInfo`  
- `Game.UI.Menu.MenuUISystem+NewGameArgs`  
- `Game.UI.Menu.MenuUISystem+LoadGameArgs`  
- `Game.UI.Menu.MenuUISystem+GameOptions`  
- `Game.UI.Menu.MenuUISystem+DefaultGameOptions`  
- `Game.UI.Menu.MenuUISystem+SaveabilityStatus`  
- `Game.UI.Menu.MenuUISystem+<>c`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass59_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass60_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass61_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass62_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass65_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass68_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass71_0`  
- `Game.UI.Menu.MenuUISystem+<>c__DisplayClass73_0`  
- `Game.UI.Menu.MenuUISystem+<ContinueGame>d__58`  
- `Game.UI.Menu.MenuUISystem+<ExitToMainMenu>d__77`  
- `Game.UI.Menu.MenuUISystem+<LoadGame>d__62`  
- `Game.UI.Menu.MenuUISystem+<NewGame>d__60`  
- `Game.UI.Menu.MenuUISystem+<OnPSModsUIClosed>d__54`  
- `Game.UI.Menu.MenuUISystem+<QuickLoad>d__72`  
- `Game.UI.Menu.MenuUISystem+<QuickSave>d__70`  
- `Game.UI.Menu.MenuUISystem+<SaveGame>d__66`  
- `Game.UI.Menu.MenuUISystem+<StartEditor>d__76`  


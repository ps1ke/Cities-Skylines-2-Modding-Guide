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
public MenuUISystem();
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
private System.Void ApplyOptions(System.String cityName, System.Collections.Generic.Dictionary<System.String, System.Boolean> options);
```

- `private ApplyTutorialSettings(System.Boolean showTutorials, System.Boolean resetTutorials) : System.Void`  

```csharp
private System.Void ApplyTutorialSettings(System.Boolean showTutorials, System.Boolean resetTutorials);
```

- `private ContinueGame() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task ContinueGame();
```

- `public DeleteSave(System.String guid) : System.Void`  

```csharp
public System.Void DeleteSave(System.String guid);
```

- `private ExitToMainMenu() : System.Void`  

```csharp
private System.Void ExitToMainMenu();
```

- `private FilterMaps(Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo> meta) : System.Boolean`  

```csharp
private System.Boolean FilterMaps(Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo> meta);
```

- `private GetAvailableMapFilters() : System.Collections.Generic.HashSet<System.Int32>`  

```csharp
private System.Collections.Generic.HashSet<System.Int32> GetAvailableMapFilters();
```

- `private GetCreditFiles() : System.Collections.Generic.List<System.String>`  

```csharp
private System.Collections.Generic.List<System.String> GetCreditFiles();
```

- `private GetGameOptions() : Game.UI.Menu.MenuUISystem+GameOptions`  

```csharp
private Game.UI.Menu.MenuUISystem+GameOptions GetGameOptions();
```

- `private GetSaveabilityStatus() : Game.UI.Menu.MenuUISystem+SaveabilityStatus`  

```csharp
private Game.UI.Menu.MenuUISystem+SaveabilityStatus GetSaveabilityStatus();
```

- `public GetSaveInfo(System.Boolean autoSave) : Game.Assets.SaveInfo`  

```csharp
public Game.Assets.SaveInfo GetSaveInfo(System.Boolean autoSave);
```

- `private GetThemes() : System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>`  

```csharp
private System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo> GetThemes();
```

- `private HandlesOverwrite(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> HandlesOverwrite(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName);
```

- `private static IsDefaultAsset(Colossal.IO.AssetDatabase.IAssetData asset) : System.Boolean`  

```csharp
private static System.Boolean IsDefaultAsset(Colossal.IO.AssetDatabase.IAssetData asset);
```

- `private IsEditorEnabled() : System.Boolean`  

```csharp
private System.Boolean IsEditorEnabled();
```

- `private IsModdingEnabled() : System.Boolean`  

```csharp
private System.Boolean IsModdingEnabled();
```

- `private IsModsUIActive() : System.Boolean`  

```csharp
private System.Boolean IsModsUIActive();
```

- `private IsPdxModsUIEnabled() : System.Boolean`  

```csharp
private System.Boolean IsPdxModsUIEnabled();
```

- `private LoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task LoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss);
```

- `private NewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task NewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args);
```

- `private OnContentAvailabilityChanged(Game.Prefabs.ContentPrefab contentPrefab) : System.Void`  

```csharp
private System.Void OnContentAvailabilityChanged(Game.Prefabs.ContentPrefab contentPrefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnPSModsUIClosed() : System.Void`  

```csharp
private System.Void OnPSModsUIClosed();
```

- `private OnSaveGameScreenVisibilityChanged(System.Boolean visible) : System.Void`  

```csharp
private System.Void OnSaveGameScreenVisibilityChanged(System.Boolean visible);
```

- `private OnSelectMapFilter(System.Int32 tab) : System.Void`  

```csharp
private System.Void OnSelectMapFilter(System.Int32 tab);
```

- `protected virtual OnWorldReady() : System.Void`  

```csharp
protected virtual System.Void OnWorldReady();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private QuickLoad(System.Boolean dismiss) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task QuickLoad(System.Boolean dismiss);
```

- `private QuickSave() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task QuickSave();
```

- `private SafeContinueGame() : System.Void`  

```csharp
private System.Void SafeContinueGame();
```

- `private SafeLoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss) : System.Void`  

```csharp
private System.Void SafeLoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss);
```

- `private SafeNewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args) : System.Void`  

```csharp
private System.Void SafeNewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args);
```

- `private SafeQuickLoad(System.Boolean dismiss) : System.Void`  

```csharp
private System.Void SafeQuickLoad(System.Boolean dismiss);
```

- `private SafeQuickSave() : System.Void`  

```csharp
private System.Void SafeQuickSave();
```

- `private SafeSaveGame(System.String saveName) : System.Void`  

```csharp
private System.Void SafeSaveGame(System.String saveName);
```

- `private SaveExists(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String name, Colossal.IO.AssetDatabase.PackageAsset& asset) : System.Boolean`  

```csharp
private System.Boolean SaveExists(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String name, Colossal.IO.AssetDatabase.PackageAsset& asset);
```

- `private SaveGame(System.String saveName) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task SaveGame(System.String saveName);
```

- `private SelectCloudTarget(System.String cloudTarget) : System.Void`  

```csharp
private System.Void SelectCloudTarget(System.String cloudTarget);
```

- `public ShareMap(System.String id) : System.Void`  

```csharp
public System.Void ShareMap(System.String id);
```

- `public ShareSave(System.String id) : System.Void`  

```csharp
public System.Void ShareSave(System.String id);
```

- `private ShowModsUI() : System.Void`  

```csharp
private System.Void ShowModsUI();
```

- `private StartEditor() : System.Void`  

```csharp
private System.Void StartEditor();
```

- `private UpdateClouds(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void UpdateClouds(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `private UpdateMaps(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void UpdateMaps(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `private UpdateMaps() : System.Void`  

```csharp
private System.Void UpdateMaps();
```

- `private UpdateSaves() : System.Void`  

```csharp
private System.Void UpdateSaves();
```

- `private UpdateSaves(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void UpdateSaves(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
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


# Game.UI.Menu.MenuUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.UI.MapMetadataSystem m_MapMetadataSystem`  
- `private Game.UI.Menu.StandaloneAssetUploadPanelUISystem m_AssetUploadPanelUISystem`  
- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  
- `private Game.Prefabs.Modes.GameModeSystem m_GameModeSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ActiveScreenBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>> m_ThemesBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.MapInfo>> m_MapsBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.Int32>> m_AvailableMapFilters`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SelectedMapFilter`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>> m_GameModesBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_CurrentGameModeBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Game.Assets.SaveInfo>> m_SavesBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_SavePreviewBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_LastSaveNameBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SaveGameSlotsBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Menu.MenuUISystem+SaveabilityStatus> m_SaveabilityBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding`  
- `private Game.UI.Menu.MenuUISystem+DefaultGameOptions m_DefaultGameOptions`  
- `private Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings m_PreviewSettings`  
- `private Unity.Entities.EntityQuery m_XPQuery`  
- `private System.Boolean m_IsLoading`  
- `private System.String m_LastSelectedCloudTarget`  
- `private Game.PSI.PdxSdk.PdxModsUI m_ModsUI`  
- `private static System.Int32 s_PreviewId`  
- `private static const System.String kPreviewName`  
- `private static const System.Int32 kPreviewWidth`  
- `private static const System.Int32 kPreviewHeight`  
- `private static const System.String kGroup`  

## Properties

- `public Game.UI.Menu.MenuUISystem+MenuScreen activeScreen { get; set }`  

## Constructors

- `public MenuUISystem()`  

## Methods

- `private <OnCreate>b__36_0() : System.String`  
- `private <OnCreate>b__36_2() : Game.UI.Menu.MenuUISystem+DefaultGameOptions`  
- `private <UpdateClouds>b__42_0() : System.Void`  
- `private ApplyOptions(System.String cityName, System.Collections.Generic.Dictionary<System.String, System.Boolean> options) : System.Void`  
- `private ApplyTutorialSettings(System.Boolean showTutorials, System.Boolean resetTutorials) : System.Void`  
- `private ContinueGame() : System.Threading.Tasks.Task`  
- `public DeleteSave(System.String guid) : System.Void`  
- `private ExitToMainMenu() : System.Void`  
- `private FilterMaps(Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo> meta) : System.Boolean`  
- `private GetAvailableMapFilters() : System.Collections.Generic.HashSet<System.Int32>`  
- `private GetCreditFiles() : System.Collections.Generic.List<System.String>`  
- `private GetGameOptions() : Game.UI.Menu.MenuUISystem+GameOptions`  
- `private GetSaveabilityStatus() : Game.UI.Menu.MenuUISystem+SaveabilityStatus`  
- `public GetSaveInfo(System.Boolean autoSave) : Game.Assets.SaveInfo`  
- `private GetThemes() : System.Collections.Generic.List<Game.UI.Menu.MenuUISystem+ThemeInfo>`  
- `private HandlesOverwrite(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName) : System.Threading.Tasks.Task<System.Boolean>`  
- `private static IsDefaultAsset(Colossal.IO.AssetDatabase.IAssetData asset) : System.Boolean`  
- `private IsEditorEnabled() : System.Boolean`  
- `private IsModdingEnabled() : System.Boolean`  
- `private IsModsUIActive() : System.Boolean`  
- `private IsPdxModsUIEnabled() : System.Boolean`  
- `private LoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss) : System.Threading.Tasks.Task`  
- `private NewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args) : System.Threading.Tasks.Task`  
- `private OnContentAvailabilityChanged(Game.Prefabs.ContentPrefab contentPrefab) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnPSModsUIClosed() : System.Void`  
- `private OnSaveGameScreenVisibilityChanged(System.Boolean visible) : System.Void`  
- `private OnSelectMapFilter(System.Int32 tab) : System.Void`  
- `protected virtual OnWorldReady() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private QuickLoad(System.Boolean dismiss) : System.Threading.Tasks.Task`  
- `private QuickSave() : System.Threading.Tasks.Task`  
- `private SafeContinueGame() : System.Void`  
- `private SafeLoadGame(Game.UI.Menu.MenuUISystem+LoadGameArgs args, System.Boolean dismiss) : System.Void`  
- `private SafeNewGame(Game.UI.Menu.MenuUISystem+NewGameArgs args) : System.Void`  
- `private SafeQuickLoad(System.Boolean dismiss) : System.Void`  
- `private SafeQuickSave() : System.Void`  
- `private SafeSaveGame(System.String saveName) : System.Void`  
- `private SaveExists(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String name, Colossal.IO.AssetDatabase.PackageAsset& asset) : System.Boolean`  
- `private SaveGame(System.String saveName) : System.Threading.Tasks.Task`  
- `private SelectCloudTarget(System.String cloudTarget) : System.Void`  
- `public ShareMap(System.String id) : System.Void`  
- `public ShareSave(System.String id) : System.Void`  
- `private ShowModsUI() : System.Void`  
- `private StartEditor() : System.Void`  
- `private UpdateClouds(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `private UpdateMaps(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `private UpdateMaps() : System.Void`  
- `private UpdateSaves() : System.Void`  
- `private UpdateSaves(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

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


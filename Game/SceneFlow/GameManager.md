# Game.SceneFlow.GameManager

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Threading.ICoroutineHost`  

## Code

```csharp
public class GameManager : UnityEngine.MonoBehaviour, Game.Threading.ICoroutineHost
{
    private System.String[] <cmdLine>k__BackingField;
    private Game.SceneFlow.GameManager+Configuration m_Configuration;
    private System.String m_AdditionalCommandLineToggles;
    private Game.GameMode <gameMode>k__BackingField;
    private Game.Settings.SharedSettings <settings>k__BackingField;
    private Game.Modding.ModManager m_ModManager;
    private System.Threading.CancellationTokenSource m_Cts;
    private readonly System.Threading.CancellationTokenSource m_QuitRequested;
    private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_WorldReadySource;
    public UnityEngine.GameObject[] m_SettingsDependantObjects;
    private System.Int32 m_MainThreadId;
    private Game.SceneFlow.GameManager+State m_State;
    private Game.SceneFlow.OverlayScreen m_InitialEngagementScreen;
    private System.Boolean m_IsEngagementStarted;
    private Game.SceneFlow.GameManager+EventGameSaveLoad onGameSaveLoad;
    private Game.SceneFlow.GameManager+EventGamePreload onGamePreload;
    private Game.SceneFlow.GameManager+EventGamePreload onGameLoadingComplete;
    private Game.SceneFlow.GameManager+EventCallback onWorldReady;
    private System.Boolean m_StartUpTelemetryFired;
    private System.String m_UILocation;
    private Colossal.UI.UIManager m_UIManager;
    private Colossal.UI.UIInputSystem m_UIInputSystem;
    private Colossal.Localization.LocalizationManager <localizationManager>k__BackingField;
    private Game.SceneFlow.UserInterface <userInterface>k__BackingField;
    private readonly System.Collections.Concurrent.ConcurrentDictionary<System.Guid, System.Func<System.Boolean>> m_Updaters;
    private Game.UI.Thumbnails.ThumbnailCache <thumbnailCache>k__BackingField;
    private UnityEngine.LayerMask m_DefaultCullingMask;
    private UnityEngine.LayerMask m_DefaultVolumeLayerMask;
    private Game.Debug.ConsoleWindow m_Console;
    private Unity.Entities.World m_World;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Serialization.LoadGameSystem m_DeserializationSystem;
    private Game.Serialization.SaveGameSystem m_SerializationSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private static Colossal.Logging.ILog log;
    private static Game.SceneFlow.GameManager <instance>k__BackingField;
    private static System.String s_ModdingRuntime;
    public static const System.String kInMainMenuState;
    public static const System.String kInGameState;
    public static const System.String kInEditorState;
    private static const System.String kBootTask;

    public System.String[] cmdLine { get; private set; }
    public Game.SceneFlow.GameManager+Configuration configuration { get; }
    public static Game.SceneFlow.GameManager instance { get; private set; }
    public System.Boolean isMainThread { get; }
    public Game.GameMode gameMode { get; private set; }
    public System.Boolean isGameLoading { get; }
    public Game.Settings.SharedSettings settings { get; private set; }
    public Game.Modding.ModManager modManager { get; }
    public System.Threading.CancellationToken terminationToken { get; }
    public Game.SceneFlow.GameManager+State state { get; }
    public System.Boolean shouldUpdateManager { get; }
    public System.Boolean shouldUpdateWorld { get; }
    public static Colossal.UI.UIInputSystem UIInputSystem { get; }
    public Colossal.Localization.LocalizationManager localizationManager { get; private set; }
    public Game.SceneFlow.UserInterface userInterface { get; private set; }
    public Game.UI.Thumbnails.ThumbnailCache thumbnailCache { get; private set; }

    public GameManager();

    internal static System.Void <HandleUserFolderVersion>g__DeleteSettings|177_0(System.String settingsPath);
    private System.Threading.Tasks.Task <Initialize>b__54_1();
    private System.Threading.Tasks.Task <Initialize>b__54_2();
    private System.Void <ParseOptions>b__12_0(System.String option);
    private System.Void <ParseOptions>b__12_1(System.String option);
    private System.Void <ParseOptions>b__12_10(System.String option);
    private System.Void <ParseOptions>b__12_11(System.String option);
    private System.Void <ParseOptions>b__12_12(System.String option);
    private System.Void <ParseOptions>b__12_13(System.String option);
    private System.Void <ParseOptions>b__12_14(System.String option);
    private System.Void <ParseOptions>b__12_15(System.String option);
    private System.Void <ParseOptions>b__12_16(System.String option);
    private System.Void <ParseOptions>b__12_3(System.String option);
    private System.Void <ParseOptions>b__12_4(System.String option);
    private System.Void <ParseOptions>b__12_5(System.String option);
    private System.Void <ParseOptions>b__12_6(System.String option);
    private System.Void <ParseOptions>b__12_7(System.String option);
    private System.Void <ParseOptions>b__12_8(System.String option);
    private System.Void <ParseOptions>b__12_9(System.String option);
    private System.String <RegisterPdxSdk>b__105_10(System.String localeId);
    private System.Void <RegisterPdxSdk>b__105_16(Colossal.IO.AssetDatabase.UIModuleAsset asset, System.Boolean isInActivePlayset);
    private System.Void <RegisterPdxSdk>b__105_17(Colossal.IO.AssetDatabase.ExecutableAsset asset, System.Boolean isInActivePlayset);
    private System.Void <RegisterPdxSdk>b__105_2(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remaining);
    private System.Void <RegisterPdxSdk>b__105_6(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlcs);
    private System.Void <RegisterPdxSdk>g__OnActivePlaysetChanged|105_13();
    private System.Void <RegisterPdxSdk>g__OnAssetChanged|105_14(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    private System.String <SaveSimulationData>b__89_0(Unity.Entities.Entity x);
    private System.Boolean <ShowFallbackUI>b__124_1();
    internal static System.Threading.Tasks.Task <SubscribeToGdkUserEvents>g__RegisterDb|108_2();
    internal static System.Threading.Tasks.Task <SubscribeToGdkUserEvents>g__UnregisterDb|108_1();
    private System.Void <WaitForReadyState>b__57_0();
    public System.Boolean ArePrerequisitesMet(System.String[] contentPrerequisites);
    public System.Boolean ArePrerequisitesMet<T>(Colossal.IO.AssetDatabase.Metadata<T> meta);
    private System.Threading.Tasks.Task<System.Boolean> AutoLoad(Colossal.IO.AssetDatabase.IAssetData asset);
    private System.Threading.Tasks.Task<System.Boolean> AutoLoad(Colossal.Hash128 guid);
    private System.Void Awake();
    private System.Collections.IEnumerator CaptureScreenshot();
    private System.Threading.Tasks.Task CheckCapabilities();
    private System.Boolean CheckValidity();
    private System.Void CleanupMemory();
    private System.Void CreateSystems();
    private System.Void CreateUISystems();
    private System.Void CreateWorld();
    private System.Void DestroyWorld();
    private static System.Void DetectModdingRuntime();
    private static System.String DetectModdingRuntimeName();
    private System.Void DisableCameraRendering();
    private System.Threading.Tasks.Task DisposePlatforms();
    private System.Void DisposeThumbnails();
    private System.Void EnableCameraRendering();
    private System.Void EnableMemoryLeaksDetection();
    private System.Void EnableSettingsDependantObjects();
    private static System.IntPtr FindWindow(System.String strClassName, System.String strWindowName);
    public System.Void FocusChanged(System.Boolean hasFocus);
    private UnityEngine.Coroutine Game.Threading.ICoroutineHost.StartCoroutine(System.Collections.IEnumerator routine);
    public System.String[] GetAvailablePrerequisitesNames();
    private static System.Collections.Generic.Dictionary<System.String, System.String> GetDefaultBacktraceAttributes();
    private System.Guid GetSessionGuid(Colossal.Serialization.Entities.Purpose purpose, System.Guid existingGuid);
    private Game.SceneFlow.GameManager+Configuration+StdoutCaptureMode GetStdoutCaptureMode(System.String option);
    public static System.String GetSystemInfoString();
    public static System.String GetVersionsInfo();
    private static System.Int32 GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount);
    private System.Boolean HandleConfiguration();
    private System.Void HandleDeviceAssociationLost();
    private System.Void HandleDeviceDisconnected();
    private System.Void HandleDevicePaired();
    private System.Void HandleUserFolderVersion();
    private System.Void HandleUserUpdated(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags flags);
    private System.Void InitConsole();
    private System.Void Initialize();
    private System.Void InitializeLocalization();
    private System.Void InitializeModManager(System.Boolean ignoreParadox);
    private System.Threading.Tasks.Task InitializePlatformManager();
    private System.Void InitializeThumbnails();
    private System.Threading.Tasks.Task InitializeUI();
    private System.Void LateUpdate();
    private System.Void LateUpdateWorld();
    private static System.Void ListHarmonyPatches();
    private System.Threading.Tasks.Task<System.Boolean> Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.AsyncReadDescriptor descriptor, Colossal.Hash128 instigatorGuid, System.Guid sessionGuid);
    public System.Threading.Tasks.Task<System.Boolean> Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.IAssetData asset);
    public System.Threading.Tasks.Task<System.Boolean> Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.Hash128 guid);
    private System.Threading.Tasks.Task<Game.SceneFlow.AssetLibrary> LoadAssetLibraryAsync();
    private System.Void LoadPrefabs();
    private System.Threading.Tasks.Task LoadSimulationData(Colossal.Serialization.Entities.Context context, Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor);
    private System.Threading.Tasks.Task LoadUnityPrefabs();
    public System.Threading.Tasks.Task<System.Boolean> MainMenu();
    private static System.String[] MaskArguments(System.String[] cmdLine);
    private static System.String[] MergeAdditionalCommandLineArguments(System.String[] cmdLineArgs, System.String additionalCmdLine);
    private System.Void NotifyProgress(System.String identifier, System.Int32 progress);
    private System.Void OnDestroy();
    private System.Void OnGUI();
    private System.Void OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    private System.Void ParseOptions();
    private System.Void PostUpdateWorld();
    private System.Threading.Tasks.Task PreparePersistentStorage();
    private static System.Void PrintIndividualPatches(Colossal.Logging.ILog moddingLog, System.String patchType, System.Collections.Generic.IEnumerable<System.Object> patches, Game.SceneFlow.GameManager+LocalTypeCache typeCache);
    private static System.Void PrintPatchDetails(Colossal.Logging.ILog moddingLog, System.Object patchInfo, System.Type patchInfoType, Game.SceneFlow.GameManager+LocalTypeCache typeCache);
    public static System.Void QuitGame();
    public System.Void RegisterCancellationOnQuit(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Boolean stateOnCancel);
    private System.Void RegisterDeviceAndUserListeners();
    private System.Threading.Tasks.Task RegisterPdxSdk();
    public System.Guid RegisterUpdater(System.Action action);
    public System.Guid RegisterUpdater(System.Func<System.Boolean> func);
    private System.Void ReleaseConsole();
    private System.Void ReleaseUI();
    private System.Void ReportBootProgress(System.Single progress);
    public System.Void RunOnMainThread(System.Action action);
    public System.Threading.Tasks.Task<System.Boolean> Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, UnityEngine.Texture savePreview);
    public System.Threading.Tasks.Task<System.Boolean> Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Game.UI.ScreenCaptureHelper+AsyncRequest previewRequest);
    private System.Threading.Tasks.Task<System.String[]> SaveSimulationData(Colossal.Serialization.Entities.Context context, System.IO.Stream stream);
    private System.Threading.Tasks.Task SetInitialEngagementScreenActive();
    private static System.Void SetNativeStackTrace();
    public System.Threading.Tasks.Task SetScreenActive<T>();
    private static System.Void SetupCustomAssetTypes();
    private static System.Void SetWindowsTitle();
    private static System.Boolean SetWindowText(System.IntPtr hWnd, System.String lpString);
    private System.Void ShowFallbackUI(System.Exception ex);
    private System.Void SubscribeToGdkUserEvents();
    public System.Void TakeScreenshot();
    private System.Void TelemetryReady();
    private System.Threading.Tasks.Task TerminateGame();
    private System.Void TryCatchUnhandledExceptions();
    public System.Boolean UnregisterUpdater(System.Guid guid);
    private System.Void Update();
    private System.Void UpdatePlatforms();
    private System.Void UpdateUI();
    private System.Void UpdateUpdaters();
    private System.Void UpdateWorld();
    public System.Threading.Tasks.Task<System.Boolean> WaitForReadyState();
    private System.Boolean WantsToQuit();
}
```


## Fields

- `private System.String[] <cmdLine>k__BackingField`  

```csharp
private System.String[] <cmdLine>k__BackingField;
```

- `private Game.SceneFlow.GameManager+Configuration m_Configuration`  

```csharp
private Game.SceneFlow.GameManager+Configuration m_Configuration;
```

- `private System.String m_AdditionalCommandLineToggles`  

```csharp
private System.String m_AdditionalCommandLineToggles;
```

- `private Game.GameMode <gameMode>k__BackingField`  

```csharp
private Game.GameMode <gameMode>k__BackingField;
```

- `private Game.Settings.SharedSettings <settings>k__BackingField`  

```csharp
private Game.Settings.SharedSettings <settings>k__BackingField;
```

- `private Game.Modding.ModManager m_ModManager`  

```csharp
private Game.Modding.ModManager m_ModManager;
```

- `private System.Threading.CancellationTokenSource m_Cts`  

```csharp
private System.Threading.CancellationTokenSource m_Cts;
```

- `private readonly System.Threading.CancellationTokenSource m_QuitRequested`  

```csharp
private readonly System.Threading.CancellationTokenSource m_QuitRequested;
```

- `private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_WorldReadySource`  

```csharp
private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_WorldReadySource;
```

- `public UnityEngine.GameObject[] m_SettingsDependantObjects`  

```csharp
public UnityEngine.GameObject[] m_SettingsDependantObjects;
```

- `private System.Int32 m_MainThreadId`  

```csharp
private System.Int32 m_MainThreadId;
```

- `private Game.SceneFlow.GameManager+State m_State`  

```csharp
private Game.SceneFlow.GameManager+State m_State;
```

- `private Game.SceneFlow.OverlayScreen m_InitialEngagementScreen`  

```csharp
private Game.SceneFlow.OverlayScreen m_InitialEngagementScreen;
```

- `private System.Boolean m_IsEngagementStarted`  

```csharp
private System.Boolean m_IsEngagementStarted;
```

- `private Game.SceneFlow.GameManager+EventGameSaveLoad onGameSaveLoad`  

```csharp
private Game.SceneFlow.GameManager+EventGameSaveLoad onGameSaveLoad;
```

- `private Game.SceneFlow.GameManager+EventGamePreload onGamePreload`  

```csharp
private Game.SceneFlow.GameManager+EventGamePreload onGamePreload;
```

- `private Game.SceneFlow.GameManager+EventGamePreload onGameLoadingComplete`  

```csharp
private Game.SceneFlow.GameManager+EventGamePreload onGameLoadingComplete;
```

- `private Game.SceneFlow.GameManager+EventCallback onWorldReady`  

```csharp
private Game.SceneFlow.GameManager+EventCallback onWorldReady;
```

- `private System.Boolean m_StartUpTelemetryFired`  

```csharp
private System.Boolean m_StartUpTelemetryFired;
```

- `private System.String m_UILocation`  

```csharp
private System.String m_UILocation;
```

- `private Colossal.UI.UIManager m_UIManager`  

```csharp
private Colossal.UI.UIManager m_UIManager;
```

- `private Colossal.UI.UIInputSystem m_UIInputSystem`  

```csharp
private Colossal.UI.UIInputSystem m_UIInputSystem;
```

- `private Colossal.Localization.LocalizationManager <localizationManager>k__BackingField`  

```csharp
private Colossal.Localization.LocalizationManager <localizationManager>k__BackingField;
```

- `private Game.SceneFlow.UserInterface <userInterface>k__BackingField`  

```csharp
private Game.SceneFlow.UserInterface <userInterface>k__BackingField;
```

- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.Guid, System.Func<System.Boolean>> m_Updaters`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentDictionary<System.Guid, System.Func<System.Boolean>> m_Updaters;
```

- `private Game.UI.Thumbnails.ThumbnailCache <thumbnailCache>k__BackingField`  

```csharp
private Game.UI.Thumbnails.ThumbnailCache <thumbnailCache>k__BackingField;
```

- `private UnityEngine.LayerMask m_DefaultCullingMask`  

```csharp
private UnityEngine.LayerMask m_DefaultCullingMask;
```

- `private UnityEngine.LayerMask m_DefaultVolumeLayerMask`  

```csharp
private UnityEngine.LayerMask m_DefaultVolumeLayerMask;
```

- `private Game.Debug.ConsoleWindow m_Console`  

```csharp
private Game.Debug.ConsoleWindow m_Console;
```

- `private Unity.Entities.World m_World`  

```csharp
private Unity.Entities.World m_World;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Serialization.LoadGameSystem m_DeserializationSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_DeserializationSystem;
```

- `private Game.Serialization.SaveGameSystem m_SerializationSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SerializationSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static Game.SceneFlow.GameManager <instance>k__BackingField`  

```csharp
private static Game.SceneFlow.GameManager <instance>k__BackingField;
```

- `private static System.String s_ModdingRuntime`  

```csharp
private static System.String s_ModdingRuntime;
```

- `public static const System.String kInMainMenuState`  

```csharp
public static const System.String kInMainMenuState;
```

- `public static const System.String kInGameState`  

```csharp
public static const System.String kInGameState;
```

- `public static const System.String kInEditorState`  

```csharp
public static const System.String kInEditorState;
```

- `private static const System.String kBootTask`  

```csharp
private static const System.String kBootTask;
```


## Properties

- `public System.String[] cmdLine { get; private set }`  

```csharp
public System.String[] cmdLine { get; private set; }
```

- `public Game.SceneFlow.GameManager+Configuration configuration { get }`  

```csharp
public Game.SceneFlow.GameManager+Configuration configuration { get; }
```

- `public static Game.SceneFlow.GameManager instance { get; private set }`  

```csharp
public static Game.SceneFlow.GameManager instance { get; private set; }
```

- `public System.Boolean isMainThread { get }`  

```csharp
public System.Boolean isMainThread { get; }
```

- `public Game.GameMode gameMode { get; private set }`  

```csharp
public Game.GameMode gameMode { get; private set; }
```

- `public System.Boolean isGameLoading { get }`  

```csharp
public System.Boolean isGameLoading { get; }
```

- `public Game.Settings.SharedSettings settings { get; private set }`  

```csharp
public Game.Settings.SharedSettings settings { get; private set; }
```

- `public Game.Modding.ModManager modManager { get }`  

```csharp
public Game.Modding.ModManager modManager { get; }
```

- `public System.Threading.CancellationToken terminationToken { get }`  

```csharp
public System.Threading.CancellationToken terminationToken { get; }
```

- `public Game.SceneFlow.GameManager+State state { get }`  

```csharp
public Game.SceneFlow.GameManager+State state { get; }
```

- `public System.Boolean shouldUpdateManager { get }`  

```csharp
public System.Boolean shouldUpdateManager { get; }
```

- `public System.Boolean shouldUpdateWorld { get }`  

```csharp
public System.Boolean shouldUpdateWorld { get; }
```

- `public static Colossal.UI.UIInputSystem UIInputSystem { get }`  

```csharp
public static Colossal.UI.UIInputSystem UIInputSystem { get; }
```

- `public Colossal.Localization.LocalizationManager localizationManager { get; private set }`  

```csharp
public Colossal.Localization.LocalizationManager localizationManager { get; private set; }
```

- `public Game.SceneFlow.UserInterface userInterface { get; private set }`  

```csharp
public Game.SceneFlow.UserInterface userInterface { get; private set; }
```

- `public Game.UI.Thumbnails.ThumbnailCache thumbnailCache { get; private set }`  

```csharp
public Game.UI.Thumbnails.ThumbnailCache thumbnailCache { get; private set; }
```


## Constructors

- `public GameManager()`  

```csharp
public GameManager();
```


## Methods

- `internal static <HandleUserFolderVersion>g__DeleteSettings|177_0(System.String settingsPath) : System.Void`  

```csharp
internal static System.Void <HandleUserFolderVersion>g__DeleteSettings|177_0(System.String settingsPath);
```

- `private <Initialize>b__54_1() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <Initialize>b__54_1();
```

- `private <Initialize>b__54_2() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <Initialize>b__54_2();
```

- `private <ParseOptions>b__12_0(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_0(System.String option);
```

- `private <ParseOptions>b__12_1(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_1(System.String option);
```

- `private <ParseOptions>b__12_10(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_10(System.String option);
```

- `private <ParseOptions>b__12_11(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_11(System.String option);
```

- `private <ParseOptions>b__12_12(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_12(System.String option);
```

- `private <ParseOptions>b__12_13(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_13(System.String option);
```

- `private <ParseOptions>b__12_14(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_14(System.String option);
```

- `private <ParseOptions>b__12_15(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_15(System.String option);
```

- `private <ParseOptions>b__12_16(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_16(System.String option);
```

- `private <ParseOptions>b__12_3(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_3(System.String option);
```

- `private <ParseOptions>b__12_4(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_4(System.String option);
```

- `private <ParseOptions>b__12_5(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_5(System.String option);
```

- `private <ParseOptions>b__12_6(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_6(System.String option);
```

- `private <ParseOptions>b__12_7(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_7(System.String option);
```

- `private <ParseOptions>b__12_8(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_8(System.String option);
```

- `private <ParseOptions>b__12_9(System.String option) : System.Void`  

```csharp
private System.Void <ParseOptions>b__12_9(System.String option);
```

- `private <RegisterPdxSdk>b__105_10(System.String localeId) : System.String`  

```csharp
private System.String <RegisterPdxSdk>b__105_10(System.String localeId);
```

- `private <RegisterPdxSdk>b__105_16(Colossal.IO.AssetDatabase.UIModuleAsset asset, System.Boolean isInActivePlayset) : System.Void`  

```csharp
private System.Void <RegisterPdxSdk>b__105_16(Colossal.IO.AssetDatabase.UIModuleAsset asset, System.Boolean isInActivePlayset);
```

- `private <RegisterPdxSdk>b__105_17(Colossal.IO.AssetDatabase.ExecutableAsset asset, System.Boolean isInActivePlayset) : System.Void`  

```csharp
private System.Void <RegisterPdxSdk>b__105_17(Colossal.IO.AssetDatabase.ExecutableAsset asset, System.Boolean isInActivePlayset);
```

- `private <RegisterPdxSdk>b__105_2(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remaining) : System.Void`  

```csharp
private System.Void <RegisterPdxSdk>b__105_2(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remaining);
```

- `private <RegisterPdxSdk>b__105_6(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlcs) : System.Void`  

```csharp
private System.Void <RegisterPdxSdk>b__105_6(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlcs);
```

- `private <RegisterPdxSdk>g__OnActivePlaysetChanged|105_13() : System.Void`  

```csharp
private System.Void <RegisterPdxSdk>g__OnActivePlaysetChanged|105_13();
```

- `private <RegisterPdxSdk>g__OnAssetChanged|105_14(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void <RegisterPdxSdk>g__OnAssetChanged|105_14(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `private <SaveSimulationData>b__89_0(Unity.Entities.Entity x) : System.String`  

```csharp
private System.String <SaveSimulationData>b__89_0(Unity.Entities.Entity x);
```

- `private <ShowFallbackUI>b__124_1() : System.Boolean`  

```csharp
private System.Boolean <ShowFallbackUI>b__124_1();
```

- `internal static <SubscribeToGdkUserEvents>g__RegisterDb|108_2() : System.Threading.Tasks.Task`  

```csharp
internal static System.Threading.Tasks.Task <SubscribeToGdkUserEvents>g__RegisterDb|108_2();
```

- `internal static <SubscribeToGdkUserEvents>g__UnregisterDb|108_1() : System.Threading.Tasks.Task`  

```csharp
internal static System.Threading.Tasks.Task <SubscribeToGdkUserEvents>g__UnregisterDb|108_1();
```

- `private <WaitForReadyState>b__57_0() : System.Void`  

```csharp
private System.Void <WaitForReadyState>b__57_0();
```

- `public ArePrerequisitesMet(System.String[] contentPrerequisites) : System.Boolean`  

```csharp
public bool ArePrerequisitesMet(string[] contentPrerequisites)
	{
		if (contentPrerequisites == null)
		{
			return true;
		}
		foreach (string text in contentPrerequisites)
		{
			if (!m_PrefabSystem.TryGetPrefab(new PrefabID("ContentPrefab", text), out var prefab) || !((ContentPrefab)prefab).IsAvailable())
			{
				return false;
			}
		}
		return true;
	}
```

- `public ArePrerequisitesMet<T>(Colossal.IO.AssetDatabase.Metadata<T> meta) : System.Boolean`  

```csharp
public System.Boolean ArePrerequisitesMet<T>(Colossal.IO.AssetDatabase.Metadata<T> meta);
```

- `private AutoLoad(Colossal.IO.AssetDatabase.IAssetData asset) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private Task<bool> AutoLoad(Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out var asset))
		{
			return AutoLoad(asset);
		}
		log.WarnFormat("Couldn't load '{0}'. Asset doesn't exist!", guid);
		return Task.FromResult(result: false);
	}
```

- `private AutoLoad(Colossal.Hash128 guid) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private Task<bool> AutoLoad(Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out var asset))
		{
			return AutoLoad(asset);
		}
		log.WarnFormat("Couldn't load '{0}'. Asset doesn't exist!", guid);
		return Task.FromResult(result: false);
	}
```

- `private Awake() : System.Void`  

```csharp
private async void Awake()
	{
		_ = 1;
		try
		{
			CoroutineHost.Register(this);
			if (!CheckValidity())
			{
				return;
			}
			using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
			{
				log?.InfoFormat("GameManager created! ({0}ms)", t.TotalMilliseconds);
			}))
			{
				Task checkCapabilities = CheckCapabilities();
				DetectModdingRuntime();
				BacktraceHelper.SetDefaultAttributes(GetDefaultBacktraceAttributes());
				EnableMemoryLeaksDetection();
				Application.wantsToQuit += WantsToQuit;
				m_MainThreadId = Thread.CurrentThread.ManagedThreadId;
				m_State = State.Booting;
				Application.focusChanged += FocusChanged;
				SetNativeStackTrace();
				m_Cts = new CancellationTokenSource();
				CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
				LogManager.SetDefaultEffectiveness(Level.Info);
				BacktraceHelper.SetDefaultAttributes(GetDefaultBacktraceAttributes());
				log = LogManager.GetLogger("SceneFlow");
				TryCatchUnhandledExceptions();
				ParseOptions();
				InitConsole();
				if (!HandleConfiguration())
				{
					QuitGame();
					return;
				}
				DisableCameraRendering();
				await PreparePersistentStorage();
				HandleUserFolderVersion();
				await checkCapabilities;
				instance = this;
				Initialize();
			}
		}
		catch (Exception exception)
		{
			log.Fatal(exception);
			QuitGame();
		}
	}
```

- `private CaptureScreenshot() : System.Collections.IEnumerator`  

```csharp
private IEnumerator CaptureScreenshot()
	{
		yield return new WaitForEndOfFrame();
		ScreenUtility.CaptureScreenshot();
	}
```

- `private CheckCapabilities() : System.Threading.Tasks.Task`  

```csharp
private Task CheckCapabilities()
	{
		return Capabilities.CacheCapabilities();
	}
```

- `private CheckValidity() : System.Boolean`  

```csharp
private bool CheckValidity()
	{
		try
		{
			_ = instance.enabled;
		}
		catch (MissingReferenceException)
		{
			base.enabled = false;
			UnityEngine.Object.Destroy(base.gameObject);
			QuitGame();
			return false;
		}
		catch
		{
		}
		if (instance != null && instance != this)
		{
			base.enabled = false;
			UnityEngine.Object.Destroy(base.gameObject);
			return false;
		}
		return true;
	}
```

- `private CleanupMemory() : System.Void`  

```csharp
private void CleanupMemory()
	{
		Resources.UnloadUnusedAssets();
		foreach (Colossal.UI.UISystem uISystem in UIManager.UISystems)
		{
			uISystem.ClearCachedUnusedImages();
		}
		GC.Collect();
	}
```

- `private CreateSystems() : System.Void`  

```csharp
private void CreateSystems()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		log.Info("Creating ECS systems");
		SystemOrder.Initialize(m_UpdateSystem);
		userInterface.view.AudioSource = AudioManager.instance.UIHtmlAudioSource;
		Telemetry.gameplayData = new Telemetry.GameplayData(m_World);
	}
```

- `private CreateUISystems() : System.Void`  

```csharp
private void CreateUISystems()
	{
		foreach (Type item in ReflectionUtils.GetAllTypesDerivedFrom<UISystemBase>())
		{
			if (!item.IsAbstract)
			{
				m_World.GetOrCreateSystem(item);
			}
		}
	}
```

- `private CreateWorld() : System.Void`  

```csharp
private void CreateWorld()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		log.Info("Creating ECS world");
		CORuntimeApplication.Initialize();
		m_World = new World("Game");
		World.DefaultGameObjectInjectionWorld = m_World;
		m_PrefabSystem = m_World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UpdateSystem = m_World.GetOrCreateSystemManaged<UpdateSystem>();
		m_DeserializationSystem = m_World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_SerializationSystem = m_World.GetOrCreateSystemManaged<SaveGameSystem>();
	}
```

- `private DestroyWorld() : System.Void`  

```csharp
private void DestroyWorld()
	{
		Telemetry.gameplayData = null;
		World.DisposeAllWorlds();
		CORuntimeApplication.Shutdown();
		m_State = State.WorldDisposed;
	}
```

- `private static DetectModdingRuntime() : System.Void`  

```csharp
private static void DetectModdingRuntime()
	{
		s_ModdingRuntime = DetectModdingRuntimeName();
	}
```

- `private static DetectModdingRuntimeName() : System.String`  

```csharp
private static string DetectModdingRuntimeName()
	{
		try
		{
			Assembly[] assemblies = AppDomain.CurrentDomain.GetAssemblies();
			Assembly[] array = assemblies;
			foreach (Assembly assembly in array)
			{
				if (assembly.GetName().Name.Equals("BepInEx", StringComparison.OrdinalIgnoreCase))
				{
					return $"{assembly.GetName().Name} {assembly.GetName().Version}";
				}
			}
			array = assemblies;
			foreach (Assembly assembly2 in array)
			{
				if (assembly2.GetName().Name.Contains("BepInEx", StringComparison.OrdinalIgnoreCase))
				{
					return $"{assembly2.GetName().Name} {assembly2.GetName().Version}";
				}
				if (assembly2.GetTypes().Any((Type t) => t.Namespace != null && t.Namespace.StartsWith("BepInEx")))
				{
					return $"{assembly2.GetName().Name} {assembly2.GetName().Version}";
				}
			}
			return "Builtin";
		}
		catch
		{
			return "Unknown";
		}
	}
```

- `private DisableCameraRendering() : System.Void`  

```csharp
private void DisableCameraRendering()
	{
		Camera main = Camera.main;
		if (main != null)
		{
			m_DefaultCullingMask = main.cullingMask;
			main.cullingMask = 0;
			HDAdditionalCameraData component = main.GetComponent<HDAdditionalCameraData>();
			if (component != null)
			{
				m_DefaultVolumeLayerMask = component.volumeLayerMask;
				component.volumeLayerMask = 0;
			}
		}
	}
```

- `private DisposePlatforms() : System.Threading.Tasks.Task`  

```csharp
private async Task DisposePlatforms()
	{
		Task task = PlatformManager.instance.Dispose(disposeEvents: true, CancellationToken.None);
		while (!task.IsCompleted)
		{
			Update();
			await Task.Delay(500);
		}
		await task;
	}
```

- `private DisposeThumbnails() : System.Void`  

```csharp
private void DisposeThumbnails()
	{
		thumbnailCache?.Dispose();
	}
```

- `private EnableCameraRendering() : System.Void`  

```csharp
private void EnableCameraRendering()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		Camera main = Camera.main;
		if (main != null)
		{
			main.cullingMask = m_DefaultCullingMask;
			HDAdditionalCameraData component = main.GetComponent<HDAdditionalCameraData>();
			if (component != null)
			{
				component.volumeLayerMask = m_DefaultVolumeLayerMask;
			}
		}
	}
```

- `private EnableMemoryLeaksDetection() : System.Void`  

```csharp
private void EnableMemoryLeaksDetection()
	{
		NativeLeakDetection.Mode = NativeLeakDetectionMode.Disabled;
	}
```

- `private EnableSettingsDependantObjects() : System.Void`  

```csharp
private void EnableSettingsDependantObjects()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		GameObject[] settingsDependantObjects = m_SettingsDependantObjects;
		foreach (GameObject obj in settingsDependantObjects)
		{
			obj.SetActive(obj);
		}
	}
```

- `private static FindWindow(System.String strClassName, System.String strWindowName) : System.IntPtr`  

```csharp
private static System.IntPtr FindWindow(System.String strClassName, System.String strWindowName);
```

- `public FocusChanged(System.Boolean hasFocus) : System.Void`  

```csharp
public void FocusChanged(bool hasFocus)
	{
		InputManager.instance?.OnFocusChanged(hasFocus);
	}
```

- `private Game.Threading.ICoroutineHost.StartCoroutine(System.Collections.IEnumerator routine) : UnityEngine.Coroutine`  

```csharp
private UnityEngine.Coroutine Game.Threading.ICoroutineHost.StartCoroutine(System.Collections.IEnumerator routine);
```

- `public GetAvailablePrerequisitesNames() : System.String[]`  

```csharp
public string[] GetAvailablePrerequisitesNames()
	{
		return m_PrefabSystem.GetAvailablePrerequisitesNames();
	}
```

- `private static GetDefaultBacktraceAttributes() : System.Collections.Generic.Dictionary<System.String, System.String>`  

```csharp
private static Dictionary<string, string> GetDefaultBacktraceAttributes()
	{
		return new Dictionary<string, string>
		{
			["game.version"] = Version.current.fullVersion,
			["cohtml.version"] = Versioning.Build.ToString(),
			["pdxsdk.version"] = SDKVersion.Version,
			["atl.version"] = ATL.Version.getVersion(),
			["game.moddingRuntime"] = s_ModdingRuntime
		};
	}
```

- `private GetSessionGuid(Colossal.Serialization.Entities.Purpose purpose, System.Guid existingGuid) : System.Guid`  

```csharp
private Guid GetSessionGuid(Purpose purpose, Guid existingGuid)
	{
		if (purpose == Purpose.NewMap || purpose == Purpose.NewGame)
		{
			return Guid.NewGuid();
		}
		return existingGuid;
	}
```

- `private GetStdoutCaptureMode(System.String option) : Game.SceneFlow.GameManager+Configuration+StdoutCaptureMode`  

```csharp
private Configuration.StdoutCaptureMode GetStdoutCaptureMode(string option)
	{
		return option switch
		{
			"console" => Configuration.StdoutCaptureMode.Console, 
			"capture" => Configuration.StdoutCaptureMode.CaptureOnly, 
			"redirect" => Configuration.StdoutCaptureMode.Redirect, 
			_ => Configuration.StdoutCaptureMode.None, 
		};
	}
```

- `public static GetSystemInfoString() : System.String`  

```csharp
public static string GetSystemInfoString()
	{
		StringBuilder stringBuilder = new StringBuilder();
		stringBuilder.AppendLine("Type: " + SystemInfo.deviceType);
		stringBuilder.AppendLine("OS: " + SystemInfo.operatingSystem);
		stringBuilder.AppendLine("System memory: " + FormatUtils.FormatBytes((long)SystemInfo.systemMemorySize * 1024L * 1024));
		stringBuilder.AppendLine("Graphics device: " + SystemInfo.graphicsDeviceName + " (Version: " + SystemInfo.graphicsDeviceVersion + ")");
		stringBuilder.AppendLine("Graphics memory: " + FormatUtils.FormatBytes((long)SystemInfo.graphicsMemorySize * 1024L * 1024));
		stringBuilder.AppendLine("Max texture size: " + SystemInfo.maxTextureSize);
		stringBuilder.AppendLine("Shader level: " + SystemInfo.graphicsShaderLevel);
		stringBuilder.AppendLine("3D textures: " + SystemInfo.supports3DTextures);
		stringBuilder.AppendLine("Shadows: " + SystemInfo.supportsShadows);
		stringBuilder.AppendLine("Compute: " + SystemInfo.supportsComputeShaders);
		stringBuilder.AppendLine("CPU: " + SystemInfo.processorType);
		stringBuilder.AppendLine("Core count: " + SystemInfo.processorCount);
		stringBuilder.AppendLine("Platform: " + Application.platform);
		stringBuilder.AppendLine("Screen resolution: " + Screen.currentResolution.width + "x" + Screen.currentResolution.height + "x" + (int)Screen.currentResolution.refreshRateRatio.value);
		stringBuilder.AppendLine("Window resolution: " + Screen.width + "x" + Screen.height);
		stringBuilder.AppendLine("DPI: " + Screen.dpi);
		stringBuilder.AppendLine("Rendering Threading Mode: " + SystemInfo.renderingThreadingMode);
		stringBuilder.AppendLine("CLR: " + Environment.Version);
		stringBuilder.AppendLine("Modding runtime: " + s_ModdingRuntime);
		Type type = Type.GetType("Mono.Runtime");
		if (type != null)
		{
			MethodInfo method = type.GetMethod("GetDisplayName", BindingFlags.Static | BindingFlags.NonPublic);
			if (method != null)
			{
				stringBuilder.AppendLine("Scripting runtime: Mono " + method.Invoke(null, null));
			}
		}
		return stringBuilder.ToString().TrimEnd();
	}
```

- `public static GetVersionsInfo() : System.String`  

```csharp
public static string GetVersionsInfo()
	{
		StringBuilder stringBuilder = new StringBuilder();
		string text = null;
		text = "Mono";
		stringBuilder.AppendLine($"Date: {DateTime.UtcNow}");
		stringBuilder.AppendLine($"Game version: {Version.current.fullVersion} {Application.platform.ToPlatform()} {PlatformManager.instance.principalPlatformName}");
		stringBuilder.AppendLine("Game configuration: " + (UnityEngine.Debug.isDebugBuild ? "Development" : "Release") + " (" + text + ")");
		stringBuilder.AppendLine("COre version: " + Colossal.Core.Version.current.fullVersion);
		stringBuilder.AppendLine("Localization version: " + Colossal.Localization.Version.current.fullVersion);
		stringBuilder.AppendLine("UI version: " + Colossal.UI.Version.current.fullVersion);
		stringBuilder.AppendLine("Unity version: " + Application.unityVersion);
		stringBuilder.AppendLine($"Cohtml version: {Versioning.Build}");
		stringBuilder.AppendLine("ATL Version: " + ATL.Version.getVersion());
		PlatformManager.instance.LogVersion(stringBuilder);
		foreach (IDlc item in PlatformManager.instance.EnumerateLocalDLCs())
		{
			stringBuilder.AppendLine(item.internalName.Nicify() + ": " + item.version.fullVersion);
		}
		if (Application.genuineCheckAvailable)
		{
			stringBuilder.AppendLine($"Genuine: {Application.genuine}");
		}
		return stringBuilder.ToString().TrimEnd();
	}
```

- `private static GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount) : System.Int32`  

```csharp
private static System.Int32 GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount);
```

- `private HandleConfiguration() : System.Boolean`  

```csharp
private bool HandleConfiguration()
	{
		if (configuration.showHelp != null)
		{
			Console.WriteLine(configuration.showHelp);
			return false;
		}
		if (!string.IsNullOrEmpty(configuration.profilerTarget))
		{
			Profiler.logFile = configuration.profilerTarget;
			Profiler.enableBinaryLog = true;
			Profiler.enabled = true;
		}
		return true;
	}
```

- `private HandleDeviceAssociationLost() : System.Void`  

```csharp
private void HandleDeviceAssociationLost()
	{
		if (m_IsEngagementStarted)
		{
			SetScreenActive<ControllerPairingScreen>();
		}
		else if (m_InitialEngagementScreen > OverlayScreen.ControllerPairingChanged)
		{
			m_InitialEngagementScreen = OverlayScreen.ControllerPairingChanged;
		}
	}
```

- `private HandleDeviceDisconnected() : System.Void`  

```csharp
private void HandleDeviceDisconnected()
	{
		if (m_IsEngagementStarted)
		{
			SetScreenActive<ControllerDisconnectedScreen>();
		}
		else if (m_InitialEngagementScreen > OverlayScreen.ControllerDisconnected)
		{
			m_InitialEngagementScreen = OverlayScreen.ControllerDisconnected;
		}
	}
```

- `private HandleDevicePaired() : System.Void`  

```csharp
private void HandleDevicePaired()
	{
		if (!m_IsEngagementStarted)
		{
			m_InitialEngagementScreen = OverlayScreen.Engagement;
		}
	}
```

- `private HandleUserFolderVersion() : System.Void`  

```csharp
private void HandleUserFolderVersion()
	{
		try
		{
			Colossal.Version version = Version.current;
			string path = EnvPath.kUserDataPath + "/version";
			if (LongFile.Exists(path))
			{
				version = new Colossal.Version(LongFile.ReadAllText(path));
			}
			if (version < Version.current)
			{
				UnityEngine.Debug.Log("Persistent folder version is outdated " + version.fullVersion + " (Game: " + Version.current.fullVersion + ")");
				if (version < new Colossal.Version("1.0.6f2"))
				{
					UnityEngine.Debug.Log("User settings deleted due to outdated persistent folder version. Backups were created ending with ~");
					DeleteSettings(EnvPath.kUserDataPath);
					PlayerPrefs.DeleteAll();
					PlayerPrefs.Save();
				}
			}
			LongFile.WriteAllText(path, Version.current.fullVersion);
		}
		catch (Exception exception)
		{
			log.Error(exception);
		}
		static void DeleteSettings(string settingsPath)
		{
			foreach (FileInfo item in new DirectoryInfo(settingsPath).EnumerateFiles("*", SearchOption.AllDirectories))
			{
				if (item.Extension.ToLower() == ".coc")
				{
					string text = Path.ChangeExtension(item.FullName, ".coc~");
					LongFile.Delete(text);
					item.MoveTo(text);
				}
			}
		}
	}
```

- `private HandleUserUpdated(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  

```csharp
private void HandleUserUpdated(IPlatformServiceIntegration psi, UserChangedFlags flags)
	{
		if (m_IsEngagementStarted)
		{
			if (flags.HasFlag(UserChangedFlags.UserSigningOut) && !flags.HasFlag(UserChangedFlags.ChangingUser))
			{
				SetScreenActive<LoggedOutScreen>();
			}
		}
		else if (flags.HasFlag(UserChangedFlags.UserSigningOut) && m_InitialEngagementScreen > OverlayScreen.UserLoggedOut)
		{
			m_InitialEngagementScreen = OverlayScreen.UserLoggedOut;
		}
		else if (flags.HasFlag(UserChangedFlags.UserSignedInAgain))
		{
			m_InitialEngagementScreen = OverlayScreen.Engagement;
		}
	}
```

- `private InitConsole() : System.Void`  

```csharp
private void InitConsole()
	{
		if (configuration.captureStdout != Configuration.StdoutCaptureMode.None)
		{
			if (configuration.captureStdout != Configuration.StdoutCaptureMode.Redirect)
			{
				m_Console = new ConsoleWindow(Application.productName, configuration.captureStdout == Configuration.StdoutCaptureMode.Console);
			}
			LogManager.stdOutActive = true;
			log.Info("\u001b[1m\u001b[38;2;0;135;215mWelcome to Cities: Skylines II\u001b[0m");
			log.Info("\u001b[1m\u001b[38;2;0;135;215mColossal Order Oy - 2023\u001b[0m");
			Thread.Sleep(1000);
		}
	}
```

- `private Initialize() : System.Void`  

```csharp
private async void Initialize()
	{
		_ = 13;
		try
		{
			using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
			{
				log?.InfoFormat("GameManager initialized! ({0}ms)", t.TotalMilliseconds);
			}))
			{
				await TestScenarioSystem.Create(cmdLine);
				onGameLoadingComplete += OnMainMenuReached;
				ListHarmonyPatches();
				TaskManager taskManager = TaskManager.instance;
				InputManager.CreateInstance();
				AssetDatabase.global.SetSettingsConfiguration(configuration.saveAllSettings, configuration.cleanupSettings);
				await InitializePlatformManager();
				await taskManager.SharedTask("CacheAssets", () => AssetDatabase.global.CacheAssets(priorityAssets: true, m_Cts.Token));
				Task caching = taskManager.SharedTask("CacheAssets", () => AssetDatabase.global.CacheAssets(priorityAssets: false, m_Cts.Token));
				InitializeLocalization();
				settings = new SharedSettings(localizationManager);
				CreateWorld();
				InputManager.instance.SetDefaultControlScheme();
				await InitializeUI();
				TaskManager.instance.onNotifyProgress += NotifyProgress;
				ReportBootProgress(0f);
				Task engagement = SetInitialEngagementScreenActive();
				Task loading = SetScreenActive<LoadingScreen>();
				await SetScreenActive<SplashScreenSequence>();
				Task assetLoading = LoadUnityPrefabs();
				log.Info(GetVersionsInfo());
				log.Info(GetSystemInfoString());
				configuration.LogConfiguration();
				await engagement;
				RegisterDeviceAndUserListeners();
				m_ModManager = new ModManager(configuration.disableCodeModding);
				await caching;
				await RegisterPdxSdk();
				ReportBootProgress(0.3f);
				settings.LoadUserSettings();
				ReportBootProgress(0.5f);
				CreateSystems();
				InitializeModManager();
				settings.Apply();
				EnableSettingsDependantObjects();
				await assetLoading;
				ReportBootProgress(0.8f);
				LoadPrefabs();
				InitializeThumbnails();
				m_State = State.WorldReady;
				ReportBootProgress(1f);
				await Task.Yield();
				this.onWorldReady?.Invoke();
				await Task.WhenAll(loading, PlatformManager.instance.WaitForAchievements());
				EnableCameraRendering();
				m_WorldReadySource.TrySetResult(result: true);
				log.Info("Boot completed");
				bool flag = true;
				if (configuration.startGame.isValid)
				{
					flag = !(await AutoLoad(configuration.startGame));
				}
				else if (configuration.continuelastsave)
				{
					flag = !(await userInterface.appBindings.LauncherContinueGame());
				}
				if (flag)
				{
					await MainMenu();
				}
			}
		}
		catch (OperationCanceledException)
		{
			UnityEngine.Debug.Log("GameManager termination requested before initialization completed");
		}
		catch (Exception ex2)
		{
			log.Fatal(ex2);
			ShowFallbackUI(ex2);
		}
	}
```

- `private InitializeLocalization() : System.Void`  

```csharp
private void InitializeLocalization()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		localizationManager = new LocalizationManager("en-US", SystemLanguage.English, "English");
		localizationManager.LoadAvailableLocales();
	}
```

- `private InitializeModManager(System.Boolean ignoreParadox = False) : System.Void`  

```csharp
private void InitializeModManager(bool ignoreParadox = false)
	{
		if (m_UpdateSystem != null && (ignoreParadox || AssetDatabase<ParadoxMods>.instance.isCached))
		{
			m_ModManager.Initialize(m_UpdateSystem);
		}
	}
```

- `private InitializePlatformManager() : System.Threading.Tasks.Task`  

```csharp
private async Task InitializePlatformManager()
	{
		PlatformManager.instance.RegisterRichPresenceKey("#StatusInMainMenu", () => "In Main-Menu");
		PlatformManager.instance.RegisterRichPresenceKey("#StatusInGame", () => "In-Game");
		PlatformManager.instance.RegisterRichPresenceKey("#StatusInEditor", () => "In-Editor");
		await PlatformManager.instance.RegisterPSI(() => PlatformSupport.kCreateGDKPlatform(), m_Cts.Token).ConfigureAwait(continueOnCapturedContext: false);
		await PlatformManager.instance.RegisterPSI(PlatformSupport.kCreateDiscordRichPresence, m_Cts.Token).ConfigureAwait(continueOnCapturedContext: false);
		if (!(await PlatformManager.instance.Initialize(m_Cts.Token)))
		{
			log.ErrorFormat("A platform service integration failed to initialize");
			QuitGame();
		}
		EnvPath.UpdateSpecialPathCache();
		await AssetDatabase.global.RegisterDatabase(AssetDatabase<GdkCloud>.instance);
		SubscribeToGdkUserEvents();
		await Colossal.IO.AssetDatabase.ContentHelper.RegisterContent();
	}
```

- `private InitializeThumbnails() : System.Void`  

```csharp
private void InitializeThumbnails()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		thumbnailCache = new ThumbnailCache();
		thumbnailCache.Initialize();
	}
```

- `private InitializeUI() : System.Threading.Tasks.Task`  

```csharp
private async Task InitializeUI()
	{
		m_Cts.Token.ThrowIfCancellationRequested();
		ILog uiLog = UIManager.log;
		try
		{
			uiLog.Info("Bootstrapping cohtmlUISystem");
			m_UIManager = new UIManager(configuration.uiDeveloperMode);
			Colossal.UI.UISystem.Settings settings = Colossal.UI.UISystem.Settings.New;
			settings.localizationManager = new UILocalizationManager(localizationManager);
			settings.resourceHandler = new GameUIResourceHandler(this);
			Colossal.UI.UISystem uISystem = m_UIManager.CreateUISystem(settings);
			foreach (UIHostAsset asset in AssetDatabase.global.GetAssets(default(SearchFilter<UIHostAsset>)))
			{
				if (asset.scheme == "assetdb")
				{
					uISystem.AddDatabaseHostLocation(asset.hostname, asset.uiUri, asset.priority);
				}
				else
				{
					uISystem.AddHostLocation(asset.hostname, asset.uiPath, shouldWatch: true, asset.priority);
				}
			}
			m_UIInputSystem = new UIInputSystem(uISystem);
			userInterface = new UserInterface(m_UILocation, localizationManager, uISystem);
			m_World.GetOrCreateSystem<NotificationUISystem>();
			m_World.GetOrCreateSystem<OptionsUISystem>();
			this.settings.RegisterInOptionsUI();
			m_State = State.UIReady;
			InputManager.instance.CheckConflicts();
			log.DebugFormat("Time to UI {0}s", Time.realtimeSinceStartup);
			await userInterface.WaitForBindings();
		}
		catch (Exception exception)
		{
			uiLog.Error(exception);
		}
	}
```

- `private LateUpdate() : System.Void`  

```csharp
private void LateUpdate()
	{
		if (!m_Cts.IsCancellationRequested)
		{
			LateUpdateWorld();
		}
	}
```

- `private LateUpdateWorld() : System.Void`  

```csharp
private void LateUpdateWorld()
	{
		if (shouldUpdateWorld)
		{
			m_UpdateSystem.Update(SystemUpdatePhase.LateUpdate);
			m_UpdateSystem.Update(SystemUpdatePhase.DebugGizmos);
			CORuntimeApplication.Update();
		}
	}
```

- `private static ListHarmonyPatches() : System.Void`  

```csharp
private static void ListHarmonyPatches()
	{
		ILog logger = LogManager.GetLogger("Modding");
		logger.InfoFormat("Modding runtime: {0}", s_ModdingRuntime);
		try
		{
			LocalTypeCache localTypeCache = new LocalTypeCache();
			Assembly assembly = AppDomain.CurrentDomain.GetAssemblies().FirstOrDefault((Assembly a) => a.GetName().Name.Contains("Harmony"));
			if (assembly == null)
			{
				return;
			}
			log.Info("Harmony found.");
			Type type = assembly.GetType("Harmony.HarmonyInstance", throwOnError: false) ?? assembly.GetType("HarmonyLib.Harmony", throwOnError: false);
			if (type == null)
			{
				logger.Info("HarmonyInstance/Harmony class not found.");
				return;
			}
			MethodInfo method = localTypeCache.GetMethod(type, "GetAllPatchedMethods", BindingFlags.Static | BindingFlags.Public);
			if (method == null)
			{
				logger.Info("Method GetAllPatchedMethods not found.");
				return;
			}
			if (!(method.Invoke(null, null) is IEnumerable<MethodBase> enumerable))
			{
				logger.Info("No patched methods found.");
				return;
			}
			MethodInfo method2 = localTypeCache.GetMethod(type, "GetPatchInfo", BindingFlags.Static | BindingFlags.Public);
			if (method2 == null)
			{
				logger.Info("Method GetPatchInfo not found.");
				return;
			}
			Type type2 = assembly.GetType("HarmonyLib.Patches", throwOnError: false);
			if (type2 == null)
			{
				logger.Info("Patches class not found.");
				return;
			}
			foreach (MethodBase item in enumerable)
			{
				logger.InfoFormat("Patched Method: {0}.{1}", item.DeclaringType?.FullName ?? "<Global Type>", item.Name);
				object patchInfo = method2.Invoke(null, new object[1] { item });
				PrintPatchDetails(logger, patchInfo, type2, localTypeCache);
			}
		}
		catch (Exception exception)
		{
			log.Warn(exception, "ListHarmonyPatches failed");
		}
	}
```

- `private Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.AsyncReadDescriptor descriptor, Colossal.Hash128 instigatorGuid, System.Guid sessionGuid) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> Load(GameMode mode, Purpose purpose, Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out var asset))
		{
			return Load(mode, purpose, asset);
		}
		log.WarnFormat("Couldn't load '{0}'. Asset doesn't exist!", guid);
		return Task.FromResult(result: false);
	}
```

- `public Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.IAssetData asset = null) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> Load(GameMode mode, Purpose purpose, Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out var asset))
		{
			return Load(mode, purpose, asset);
		}
		log.WarnFormat("Couldn't load '{0}'. Asset doesn't exist!", guid);
		return Task.FromResult(result: false);
	}
```

- `public Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.Hash128 guid) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> Load(GameMode mode, Purpose purpose, Colossal.Hash128 guid)
	{
		if (AssetDatabase.global.TryGetAsset(guid, out var asset))
		{
			return Load(mode, purpose, asset);
		}
		log.WarnFormat("Couldn't load '{0}'. Asset doesn't exist!", guid);
		return Task.FromResult(result: false);
	}
```

- `private LoadAssetLibraryAsync() : System.Threading.Tasks.Task<Game.SceneFlow.AssetLibrary>`  

```csharp
private async Task<AssetLibrary> LoadAssetLibraryAsync()
	{
		using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.InfoFormat("LoadAssetLibraryAsync performed in {0}ms", t.TotalMilliseconds);
		}))
		{
			UnityEngine.ResourceRequest asyncLoad = Resources.LoadAsync<AssetLibrary>("GameAssetLibrary");
			while (!asyncLoad.isDone)
			{
				m_Cts.Token.ThrowIfCancellationRequested();
				await Task.Yield();
			}
			((AssetLibrary)asyncLoad.asset).Load(m_PrefabSystem, m_Cts.Token);
			return asyncLoad.asset as AssetLibrary;
		}
	}
```

- `private LoadPrefabs() : System.Void`  

```csharp
private void LoadPrefabs()
	{
		int count = 0;
		using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.InfoFormat("Loaded {1} prefabs in {0}s", t.TotalSeconds, count);
		}))
		{
			foreach (PrefabAsset asset in AssetDatabase.global.GetAssets(default(SearchFilter<PrefabAsset>)))
			{
				if (asset.Load() is PrefabBase prefab)
				{
					m_PrefabSystem.AddPrefab(prefab);
					count++;
				}
			}
		}
	}
```

- `private LoadSimulationData(Colossal.Serialization.Entities.Context context, Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor) : System.Threading.Tasks.Task`  

```csharp
private Task LoadSimulationData(Colossal.Serialization.Entities.Context context, AsyncReadDescriptor dataDescriptor)
	{
		this.onGamePreload?.Invoke(context.purpose, gameMode);
		CleanupMemory();
		m_DeserializationSystem.dataDescriptor = dataDescriptor;
		m_DeserializationSystem.context = context;
		return m_DeserializationSystem.RunOnce();
	}
```

- `private LoadUnityPrefabs() : System.Threading.Tasks.Task`  

```csharp
private Task LoadUnityPrefabs()
	{
		return LoadAssetLibraryAsync();
	}
```

- `public MainMenu() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public async Task<bool> MainMenu()
	{
		_ = 2;
		try
		{
			IAssetData asset = null;
			bool ret = await Load(GameMode.MainMenu, Purpose.Cleanup, asset);
			if (ret)
			{
				await AudioManager.instance.ResetAudioOnMainThread();
				await AudioManager.instance.PlayMenuMusic("Main Menu Theme");
				log.Info("MainMenu reached");
			}
			return ret;
		}
		catch (OperationCanceledException)
		{
		}
		catch (Exception exception)
		{
			log.Error(exception);
		}
		return false;
	}
```

- `private static MaskArguments(System.String[] cmdLine) : System.String[]`  

```csharp
private static string[] MaskArguments(string[] cmdLine)
	{
		try
		{
			HashSet<string> hashSet = new HashSet<string> { "pdx-launcher-session-token", "paradox-account-userid", "accessToken", "hubSessionId", "licensingIpc" };
			string[] array = (string[])cmdLine.Clone();
			for (int i = 0; i < array.Length; i++)
			{
				string text = array[i].TrimStart('-');
				int num = text.IndexOf('=');
				if (num != -1)
				{
					string input = text.Substring(num + 1);
					text = text.Substring(0, num);
					array[i] = text + "=" + input.Sensitive();
				}
				else if (hashSet.Contains(text) && i + 1 < array.Length)
				{
					array[i + 1] = array[i + 1].Sensitive();
				}
			}
			return array;
		}
		catch (Exception exception)
		{
			log.Warn(exception, "An error occured parsing the command line for logging");
			return Array.Empty<string>();
		}
	}
```

- `private static MergeAdditionalCommandLineArguments(System.String[] cmdLineArgs, System.String additionalCmdLine) : System.String[]`  

```csharp
private static string[] MergeAdditionalCommandLineArguments(string[] cmdLineArgs, string additionalCmdLine)
	{
		HashSet<string> hashSet = (string.IsNullOrEmpty(additionalCmdLine) ? new HashSet<string>() : additionalCmdLine.Split(new char[1] { ' ' }, StringSplitOptions.RemoveEmptyEntries).ToHashSet());
		if (hashSet.Count > 0)
		{
			string[] array = new string[cmdLineArgs.Length + hashSet.Count];
			cmdLineArgs.CopyTo(array, 0);
			hashSet.CopyTo(array, cmdLineArgs.Length);
			return array;
		}
		return cmdLineArgs;
	}
```

- `private NotifyProgress(System.String identifier, System.Int32 progress) : System.Void`  

```csharp
private void NotifyProgress(string identifier, int progress)
	{
		string titleId = identifier;
		string textId = identifier;
		ProgressState? progressState = ProgressState.Progressing;
		int? progress2 = progress;
		NotificationSystem.Push(identifier, null, null, titleId, textId, null, progressState, progress2);
		if (progress >= 100)
		{
			textId = identifier;
			titleId = identifier;
			progressState = ProgressState.Complete;
			progress2 = progress;
			NotificationSystem.Pop(identifier, 2f, null, null, textId, titleId, null, progressState, progress2);
		}
	}
```

- `private OnDestroy() : System.Void`  

```csharp
private void OnDestroy()
	{
		Application.wantsToQuit -= WantsToQuit;
	}
```

- `private OnGUI() : System.Void`  

```csharp
private void OnGUI()
	{
		if (shouldUpdateWorld && !m_Cts.IsCancellationRequested)
		{
			TerrainDebugSystem orCreateSystemManaged = m_World.GetOrCreateSystemManaged<TerrainDebugSystem>();
			if (orCreateSystemManaged.Enabled)
			{
				orCreateSystemManaged.RenderDebugUI();
			}
		}
	}
```

- `private OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private void OnMainMenuReached(Purpose purpose, GameMode mode)
	{
		if (mode == GameMode.MainMenu)
		{
			AutomationClientSystem.instance.OnMainMenuReached();
		}
	}
```

- `private ParseOptions() : System.Void`  

```csharp
private void ParseOptions()
	{
		OptionSet optionSet = new OptionSet().Add("cleanupSettings", "Cleanup unchanged settings", delegate(string option)
		{
			configuration.cleanupSettings = option != null;
		}).Add("saveAllSettings", "Dump all settings regardless if they have changed", delegate(string option)
		{
			configuration.saveAllSettings = option != null;
		}).Add("logsEffectiveness=", "Override effectiveness level of all logs", delegate(string option)
		{
			LogManager.SetDefaultEffectiveness(Level.GetLevel(option));
		})
			.Add("duplicateLogToDefault", "Duplicate logs to default log handler", delegate(string option)
			{
				configuration.duplicateLogToDefault = option != null;
			})
			.Add("developerMode", "Enable developer mode", delegate(string option)
			{
				configuration.developerMode = option != null;
			})
			.Add("uiDeveloperMode", "Enable UI debugger and memory tracker", delegate(string option)
			{
				configuration.uiDeveloperMode = option != null;
			})
			.Add("qaDeveloperMode", "Enable tests and automation", delegate(string option)
			{
				configuration.qaDeveloperMode = option != null;
			})
			.Add("help", "Display usage", delegate(string option)
			{
				configuration.showHelp = option;
			})
			.Add("disableThumbnails", "Disable thumbnails", delegate(string option)
			{
				configuration.noThumbnails = option != null;
			})
			.Add("disablePdxSdk", "Disables PDX SDK integration", delegate(string option)
			{
				configuration.disablePDXSDK = option != null;
			})
			.Add("disableModding", "Disable modding", delegate(string option)
			{
				configuration.disableModding = option != null;
				configuration.disableCodeModding = configuration.disableModding;
			})
			.Add("disableCodeModding", "Disable code modding", delegate(string option)
			{
				configuration.disableCodeModding = option != null;
			})
			.Add("disableUserSection", "Disable user section in main menu", delegate(string option)
			{
				configuration.disableUserSection = option != null;
			})
			.Add("startGame=", "Auto start the game with the asset referenced", delegate(string option)
			{
				configuration.startGame = Colossal.Hash128.Parse(option);
			})
			.Add("profile=", "Enable profiling to the specific file", delegate(string option)
			{
				configuration.profilerTarget = option;
			})
			.Add("captureStdout=", "Capture all logs on stdout. Options: \"console\",\"capture\"", delegate(string option)
			{
				configuration.captureStdout = GetStdoutCaptureMode(option);
			})
			.Add("continuelastsave", "Auto start the game with the asset referenced", delegate(string option)
			{
				configuration.continuelastsave = option != null;
			});
		try
		{
			string path = EnvPath.kUserDataPath + "/runOnce.txt";
			if (LongFile.Exists(path))
			{
				m_AdditionalCommandLineToggles = StringUtils.Concatenate(" ", m_AdditionalCommandLineToggles, File.ReadAllText(path));
				LongFile.Delete(path);
			}
			cmdLine = Environment.GetCommandLineArgs();
			cmdLine = MergeAdditionalCommandLineArguments(cmdLine, m_AdditionalCommandLineToggles);
			optionSet.Parse(cmdLine);
			log.InfoFormat("Command line: {0}", string.Join("\n", MaskArguments(cmdLine)));
			if (configuration.showHelp != null)
			{
				using (TextWriter textWriter = new StringWriter())
				{
					optionSet.WriteOptionDescriptions(textWriter);
					configuration.showHelp = textWriter.ToString();
					return;
				}
			}
		}
		catch (OptionException exception)
		{
			UnityEngine.Debug.LogException(exception);
		}
	}
```

- `private PostUpdateWorld() : System.Void`  

```csharp
private void PostUpdateWorld()
	{
		if (shouldUpdateWorld)
		{
			m_UpdateSystem.Update(SystemUpdatePhase.Cleanup);
		}
	}
```

- `private PreparePersistentStorage() : System.Threading.Tasks.Task`  

```csharp
private Task PreparePersistentStorage()
	{
		EnvPath.RegisterSpecialPath<SaveGameMetadata>(SaveGameMetadata.kPersistentLocation);
		EnvPath.RegisterSpecialPath<SaveGameData>(SaveGameMetadata.kPersistentLocation);
		EnvPath.RegisterSpecialPath<MapMetadata>(MapMetadata.kPersistentLocation);
		EnvPath.RegisterSpecialPath<MapData>(MapMetadata.kPersistentLocation);
		EnvPath.RegisterSpecialPath<CinematicCameraAsset>(CinematicCameraAsset.kPersistentLocation);
		return EnvPath.WipeTempPath();
	}
```

- `private static PrintIndividualPatches(Colossal.Logging.ILog moddingLog, System.String patchType, System.Collections.Generic.IEnumerable<System.Object> patches, Game.SceneFlow.GameManager+LocalTypeCache typeCache) : System.Void`  

```csharp
private static void PrintIndividualPatches(ILog moddingLog, string patchType, IEnumerable<object> patches, LocalTypeCache typeCache)
	{
		if (patches == null || !patches.Any())
		{
			return;
		}
		moddingLog.InfoFormat(" {0}:", patchType);
		using (moddingLog.indent.scoped)
		{
			foreach (object patch in patches)
			{
				MethodBase methodBase = typeCache.GetProperty(patch.GetType(), "PatchMethod").GetValue(patch, null) as MethodBase;
				if (methodBase != null)
				{
					string p = methodBase.DeclaringType?.FullName ?? "<Global Method>";
					moddingLog.InfoFormat("Patch Method: {0}.{1}", p, methodBase.Name);
				}
			}
		}
	}
```

- `private static PrintPatchDetails(Colossal.Logging.ILog moddingLog, System.Object patchInfo, System.Type patchInfoType, Game.SceneFlow.GameManager+LocalTypeCache typeCache) : System.Void`  

```csharp
private static void PrintPatchDetails(ILog moddingLog, object patchInfo, Type patchInfoType, LocalTypeCache typeCache)
	{
		if (patchInfo != null)
		{
			FieldInfo field = typeCache.GetField(patchInfoType, "Prefixes");
			FieldInfo field2 = typeCache.GetField(patchInfoType, "Postfixes");
			FieldInfo field3 = typeCache.GetField(patchInfoType, "Transpilers");
			FieldInfo field4 = typeCache.GetField(patchInfoType, "Finalizers");
			IEnumerable<object> patches = field?.GetValue(patchInfo) as IEnumerable<object>;
			IEnumerable<object> patches2 = field2?.GetValue(patchInfo) as IEnumerable<object>;
			IEnumerable<object> patches3 = field3?.GetValue(patchInfo) as IEnumerable<object>;
			IEnumerable<object> patches4 = field4?.GetValue(patchInfo) as IEnumerable<object>;
			PrintIndividualPatches(moddingLog, "Prefixes", patches, typeCache);
			PrintIndividualPatches(moddingLog, "Postfixes", patches2, typeCache);
			PrintIndividualPatches(moddingLog, "Transpilers", patches3, typeCache);
			PrintIndividualPatches(moddingLog, "Finalizers", patches4, typeCache);
		}
	}
```

- `public static QuitGame() : System.Void`  

```csharp
public static void QuitGame()
	{
		Application.Quit();
	}
```

- `public RegisterCancellationOnQuit(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Boolean stateOnCancel) : System.Void`  

```csharp
public async void RegisterCancellationOnQuit(TaskCompletionSource<bool> tcs, bool stateOnCancel)
	{
		await using (m_QuitRequested.Token.Register(delegate
		{
			tcs.TrySetResult(stateOnCancel);
		}))
		{
			await tcs.Task;
		}
	}
```

- `private RegisterDeviceAndUserListeners() : System.Void`  

```csharp
private void RegisterDeviceAndUserListeners()
	{
		InputManager.instance.EventActiveDeviceAssociationLost += HandleDeviceAssociationLost;
		InputManager.instance.EventActiveDeviceDisconnected += HandleDeviceDisconnected;
		InputManager.instance.EventDevicePaired += HandleDevicePaired;
		PlatformManager.instance.onUserUpdated += HandleUserUpdated;
	}
```

- `private RegisterPdxSdk() : System.Threading.Tasks.Task`  

```csharp
private async Task RegisterPdxSdk()
	{
		if (!configuration.disablePDXSDK)
		{
			PdxSdkConfiguration pdxConfiguration = new PdxSdkConfiguration
			{
				language = localizationManager.activeLocaleId,
				gameNamespace = "cities_skylines_2",
				gameVersion = Version.current.fullVersion,
				environment = ProductEnvironment.Live
			};
			await PlatformManager.instance.RegisterPSI(delegate
			{
				CancellationTokenSource cts = new CancellationTokenSource();
				string value;
				PdxSdkPlatform pdxSdkPlatform = new PdxSdkPlatform(pdxConfiguration)
				{
					translationHandler = (string localeId) => (!localizationManager.activeDictionary.TryGetValue(localeId, out value)) ? localeId : value
				};
				localizationManager.onActiveDictionaryChanged += delegate
				{
					pdxSdkPlatform.ChangeLanguage(localizationManager.activeLocaleId);
				};
				pdxSdkPlatform.onLegalDocumentStatusChanged += delegate(LegalDocument doc, int remaining)
				{
					if (remaining == 0)
					{
						TelemetryReady();
						PlatformManager.instance.EnableSharing();
					}
				};
				pdxSdkPlatform.onNoLogin += async delegate
				{
					try
					{
						if (state != State.Quitting && !configuration.disableModding)
						{
							await RegisterDatabase();
						}
					}
					catch (OperationCanceledException)
					{
					}
					catch (Exception exception)
					{
						InitializeModManager(ignoreParadox: true);
						PdxSdkPlatform.log.Error(exception);
					}
					finally
					{
						cts = new CancellationTokenSource();
					}
				};
				pdxSdkPlatform.onLoggedIn += async delegate
				{
					_ = 1;
					try
					{
						if (state != State.Quitting)
						{
							Task task = Task.CompletedTask;
							if (!configuration.disableModding)
							{
								task = pdxSdkPlatform.SyncMods();
							}
							if (!configuration.disableModding)
							{
								await task;
								await RegisterDatabase();
							}
						}
					}
					catch (OperationCanceledException)
					{
					}
					catch (Exception exception)
					{
						InitializeModManager(ignoreParadox: true);
						PdxSdkPlatform.log.Error(exception);
					}
					finally
					{
						cts = new CancellationTokenSource();
					}
				};
				pdxSdkPlatform.onLoggedOut += async delegate
				{
					cts.Cancel();
					cts = new CancellationTokenSource();
					if (!configuration.disableModding && await AssetDatabase.global.UnregisterDatabase(AssetDatabase<ParadoxMods>.instance))
					{
						AssetDatabase<ParadoxMods>.instance.Dispose();
					}
				};
				pdxSdkPlatform.onContentUnlocked += delegate(List<IDlc> dlcs)
				{
					if (dlcs != null)
					{
						foreach (IDlc dlc in dlcs)
						{
							if (!string.IsNullOrEmpty(dlc.internalName))
							{
								string internalName = dlc.internalName;
								string internalName2 = dlc.internalName;
								string internalName3 = dlc.internalName;
								ProgressState? progressState = ProgressState.Complete;
								NotificationSystem.Pop(internalName, 4f, null, null, internalName2, internalName3, null, progressState);
							}
						}
					}
					LoadUnityPrefabs();
				};
				pdxSdkPlatform.onDataSyncConflict += delegate
				{
					ProgressState? progressState = ProgressState.Warning;
					NotificationSystem.Push("PDXDataSyncConflict", null, null, "ActionRequired", "PDXDataSyncConflict", null, progressState, null, async delegate
					{
						TaskCompletionSource<int> tcs = new TaskCompletionSource<int>();
						userInterface.appBindings.ShowConfirmationDialog(new ParadoxCloudConflictResolutionDialog(), delegate(int msg)
						{
							tcs.SetResult(msg);
						});
						await tcs.Task;
						if (tcs.Task.Result != -1)
						{
							NotificationSystem.Pop("PDXDataSyncConflict");
							ProgressState? progressState2 = ProgressState.Indeterminate;
							NotificationSystem.Push("PDXDataSyncConflictResolving", null, null, "PDXDataSyncConflict", "PDXDataSyncConflictResolving", null, progressState2);
							if (await pdxSdkPlatform.SyncModConflict((tcs.Task.Result == 0) ? SyncDirection.Downstream : SyncDirection.Upstream))
							{
								progressState2 = ProgressState.Complete;
								NotificationSystem.Pop("PDXDataSyncConflictResolving", 1f, null, null, "PDXDataSyncConflict", "PDXDataSyncConflictResolved", null, progressState2);
							}
							else
							{
								progressState2 = ProgressState.Failed;
								NotificationSystem.Pop("PDXDataSyncConflictResolving", 1f, null, null, "PDXDataSyncConflict", "PDXDataSyncConflictFailed", null, progressState2);
							}
						}
					});
				};
				pdxSdkPlatform.onModSyncCompleted += delegate
				{
					if (!pdxSdkPlatform.HasLocalChanges())
					{
						NotificationSystem.Pop("PDXDataSyncConflict");
					}
				};
				return pdxSdkPlatform;
				async Task RegisterDatabase()
				{
					cts.Token.ThrowIfCancellationRequested();
					AssetDatabase<ParadoxMods> modsDatabase = AssetDatabase<ParadoxMods>.instance;
					IDataSourceProvider dataSource = modsDatabase.dataSource;
					if (dataSource is ParadoxModsDataSource dataSource2)
					{
						dataSource2.onAfterActivePlaysetOrModStatusChanged -= OnActivePlaysetChanged;
						modsDatabase.onAssetDatabaseChanged.Unsubscribe(OnAssetChanged);
						dataSource2.onEntryIsInActivePlaysetChanged -= OnEntryIsInActivePlaysetChanged;
						await AssetDatabase.global.RegisterDatabase(modsDatabase);
						modsDatabase.onAssetDatabaseChanged.Subscribe(OnAssetChanged);
						dataSource2.onEntryIsInActivePlaysetChanged += OnEntryIsInActivePlaysetChanged;
						dataSource2.onAfterActivePlaysetOrModStatusChanged += OnActivePlaysetChanged;
						await dataSource2.Populate();
					}
					InitializeModManager(!modsDatabase.isCached);
					void OnEntryIsInActivePlaysetChanged(Colossal.Hash128 guid, bool isInActivePlayset)
					{
						if (modsDatabase.TryGetAsset(guid, out var asset))
						{
							if (!(asset is ExecutableAsset executableAsset))
							{
								if (!(asset is UIModuleAsset uIModuleAsset))
								{
									if (!(asset is SurfaceAsset) && !(asset is MidMipCacheAsset))
									{
										if (asset is PrefabAsset prefabAsset)
										{
											try
											{
												log.DebugFormat("OnEntryIsInActivePlaysetChanged: {0} ({1})", asset.name, isInActivePlayset);
												PrefabBase prefabBase = prefabAsset.Load() as PrefabBase;
												if (isInActivePlayset)
												{
													if (m_PrefabSystem.AddPrefab(prefabBase))
													{
														log.DebugFormat("Loaded {0}", prefabBase.name);
													}
												}
												else if (m_PrefabSystem.RemovePrefab(prefabBase))
												{
													log.DebugFormat("Removed {0}", prefabBase.name);
												}
											}
											catch (Exception exception)
											{
												log.Error(exception);
											}
										}
									}
									else
									{
										m_World.GetOrCreateSystemManaged<TextureStreamingSystem>()?.MarkVTAssetsDirty();
									}
								}
								else
								{
									uIModuleAsset.isInActivePlayset = isInActivePlayset;
								}
							}
							else
							{
								executableAsset.isInActivePlayset = isInActivePlayset;
							}
						}
					}
				}
			}, m_Cts.Token).ConfigureAwait(continueOnCapturedContext: false);
		}
		else
		{
			PlatformManager.instance.EnableSharing();
			await Task.CompletedTask;
		}
		void OnActivePlaysetChanged()
		{
			m_World.GetOrCreateSystemManaged<TextureStreamingSystem>()?.RefreshVT(AssetDatabase<ParadoxMods>.instance);
		}
		void OnAssetChanged(AssetChangedEventArgs args)
		{
			if (args.change == Colossal.IO.AssetDatabase.ChangeType.AssetAdded)
			{
				IAssetData asset = args.asset;
				if (!(asset is UIModuleAsset uIModuleAsset))
				{
					if (asset is ExecutableAsset executableAsset)
					{
						executableAsset.onActivePlaysetChanged += delegate(ExecutableAsset executableAsset2, bool isInActivePlayset)
						{
							if (executableAsset2.isILAssembly && executableAsset2.isLoaded != isInActivePlayset)
							{
								m_ModManager?.RequireRestart();
							}
						};
					}
				}
				else
				{
					uIModuleAsset.onActivePlaysetChanged += delegate(UIModuleAsset uiModule, bool isInActivePlayset)
					{
						if (isInActivePlayset)
						{
							m_ModManager?.AddUIModule(uiModule);
						}
						else
						{
							m_ModManager?.RemoveUIModule(uiModule);
						}
					};
				}
			}
		}
	}
```

- `public RegisterUpdater(System.Action action) : System.Guid`  

```csharp
public Guid RegisterUpdater(Func<bool> func)
	{
		if (func != null)
		{
			Guid guid = Guid.NewGuid();
			m_Updaters.TryAdd(guid, func);
			log.DebugFormat("Updater {0} registered with guid {1}", func.Method.Name, guid.ToLowerNoDashString());
			return guid;
		}
		return Guid.Empty;
	}
```

- `public RegisterUpdater(System.Func<System.Boolean> func) : System.Guid`  

```csharp
public Guid RegisterUpdater(Func<bool> func)
	{
		if (func != null)
		{
			Guid guid = Guid.NewGuid();
			m_Updaters.TryAdd(guid, func);
			log.DebugFormat("Updater {0} registered with guid {1}", func.Method.Name, guid.ToLowerNoDashString());
			return guid;
		}
		return Guid.Empty;
	}
```

- `private ReleaseConsole() : System.Void`  

```csharp
private void ReleaseConsole()
	{
		m_Console?.Dispose();
	}
```

- `private ReleaseUI() : System.Void`  

```csharp
private void ReleaseUI()
	{
		userInterface?.Dispose();
		m_UIInputSystem?.Dispose();
		m_UIManager?.Dispose();
	}
```

- `private ReportBootProgress(System.Single progress) : System.Void`  

```csharp
private void ReportBootProgress(float progress)
	{
		TaskManager.instance.progress.Report(new ProgressTracker("Boot", ProgressTracker.Group.Group3)
		{
			progress = progress
		});
	}
```

- `public RunOnMainThread(System.Action action) : System.Void`  

```csharp
public void RunOnMainThread(Action action)
	{
		if (isMainThread)
		{
			action();
		}
		else
		{
			RegisterUpdater(action);
		}
	}
```

- `public Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, UnityEngine.Texture savePreview) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public async Task<bool> Save(string saveName, SaveInfo meta, ILocalAssetDatabase database, ScreenCaptureHelper.AsyncRequest previewRequest)
	{
		log.Info("Save " + saveName + " to " + database.name);
		this.onGameSaveLoad?.Invoke(saveName, start: true);
		ILocalAssetDatabase saveDatabase = AssetDatabase.GetTransient(0L);
		try
		{
			meta.sessionGuid = Telemetry.GetCurrentSession();
			meta.lastModified = DateTime.Now;
			AssetDataPath saveNameDataPath = saveName;
			SaveGameData saveGameData = saveDatabase.AddAsset<SaveGameData>(saveNameDataPath);
			Colossal.Serialization.Entities.Context context = new Colossal.Serialization.Entities.Context(Purpose.SaveGame, Version.current, saveGameData.id.guid);
			SaveInfo saveInfo = meta;
			saveInfo.contentPrerequisites = await SaveSimulationData(context, saveGameData.GetWriteStream());
			meta.saveGameData = saveGameData;
			if (previewRequest != null)
			{
				await previewRequest.Complete();
				using TextureImporter.Texture texture = TextureImporter.Texture.CreateUncompressed1Mip(saveName, previewRequest.width, previewRequest.height, sRGB: false, previewRequest.result);
				using TextureAsset textureAsset = saveDatabase.AddAsset(texture);
				meta.preview = textureAsset;
				textureAsset.Save();
			}
			PackageAsset p = await Task.Run(delegate
			{
				SaveGameMetadata saveGameMetadata = saveDatabase.AddAsset<SaveGameMetadata>(saveNameDataPath);
				saveGameMetadata.target = meta;
				saveGameMetadata.Save();
				AssetDataPath assetDataPath = SaveHelpers.GetAssetDataPath<SaveGameMetadata>(database, saveName);
				using (AssetDatabase.global.DisableNotificationsScoped())
				{
					if (database.Exists<PackageAsset>(assetDataPath, out var asset))
					{
						database.DeleteAsset(asset);
					}
					PackageAsset packageAsset = database.AddAsset(assetDataPath, saveDatabase);
					packageAsset.Save();
					settings.userState.lastSaveGameMetadata = saveGameMetadata;
					settings.userState.ApplyAndSave();
					Launcher.SaveLastSaveMetadata(meta);
					return packageAsset;
				}
			});
			this.onGameSaveLoad?.Invoke(saveName, start: false);
			log.InfoFormat("Saving completed {0}", p);
			return true;
		}
		finally
		{
			if (saveDatabase != null)
			{
				saveDatabase.Dispose();
			}
		}
	}
```

- `public Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Game.UI.ScreenCaptureHelper+AsyncRequest previewRequest) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public async Task<bool> Save(string saveName, SaveInfo meta, ILocalAssetDatabase database, ScreenCaptureHelper.AsyncRequest previewRequest)
	{
		log.Info("Save " + saveName + " to " + database.name);
		this.onGameSaveLoad?.Invoke(saveName, start: true);
		ILocalAssetDatabase saveDatabase = AssetDatabase.GetTransient(0L);
		try
		{
			meta.sessionGuid = Telemetry.GetCurrentSession();
			meta.lastModified = DateTime.Now;
			AssetDataPath saveNameDataPath = saveName;
			SaveGameData saveGameData = saveDatabase.AddAsset<SaveGameData>(saveNameDataPath);
			Colossal.Serialization.Entities.Context context = new Colossal.Serialization.Entities.Context(Purpose.SaveGame, Version.current, saveGameData.id.guid);
			SaveInfo saveInfo = meta;
			saveInfo.contentPrerequisites = await SaveSimulationData(context, saveGameData.GetWriteStream());
			meta.saveGameData = saveGameData;
			if (previewRequest != null)
			{
				await previewRequest.Complete();
				using TextureImporter.Texture texture = TextureImporter.Texture.CreateUncompressed1Mip(saveName, previewRequest.width, previewRequest.height, sRGB: false, previewRequest.result);
				using TextureAsset textureAsset = saveDatabase.AddAsset(texture);
				meta.preview = textureAsset;
				textureAsset.Save();
			}
			PackageAsset p = await Task.Run(delegate
			{
				SaveGameMetadata saveGameMetadata = saveDatabase.AddAsset<SaveGameMetadata>(saveNameDataPath);
				saveGameMetadata.target = meta;
				saveGameMetadata.Save();
				AssetDataPath assetDataPath = SaveHelpers.GetAssetDataPath<SaveGameMetadata>(database, saveName);
				using (AssetDatabase.global.DisableNotificationsScoped())
				{
					if (database.Exists<PackageAsset>(assetDataPath, out var asset))
					{
						database.DeleteAsset(asset);
					}
					PackageAsset packageAsset = database.AddAsset(assetDataPath, saveDatabase);
					packageAsset.Save();
					settings.userState.lastSaveGameMetadata = saveGameMetadata;
					settings.userState.ApplyAndSave();
					Launcher.SaveLastSaveMetadata(meta);
					return packageAsset;
				}
			});
			this.onGameSaveLoad?.Invoke(saveName, start: false);
			log.InfoFormat("Saving completed {0}", p);
			return true;
		}
		finally
		{
			if (saveDatabase != null)
			{
				saveDatabase.Dispose();
			}
		}
	}
```

- `private SaveSimulationData(Colossal.Serialization.Entities.Context context, System.IO.Stream stream) : System.Threading.Tasks.Task<System.String[]>`  

```csharp
private async Task<string[]> SaveSimulationData(Colossal.Serialization.Entities.Context context, Stream stream)
	{
		CleanupMemory();
		m_SerializationSystem.stream = stream;
		m_SerializationSystem.context = context;
		await m_SerializationSystem.RunOnce();
		string[] array = m_SerializationSystem.referencedContent.Select((Entity x) => m_PrefabSystem.GetPrefabName(x)).ToArray();
		return (array.Length != 0) ? array : null;
	}
```

- `private SetInitialEngagementScreenActive() : System.Threading.Tasks.Task`  

```csharp
private Task SetInitialEngagementScreenActive()
	{
		m_IsEngagementStarted = true;
		if (!PlatformManager.instance.requiresEngagement)
		{
			return Task.CompletedTask;
		}
		if (AutomationClientSystem.instance.IsConnected)
		{
			return Task.CompletedTask;
		}
		return m_InitialEngagementScreen switch
		{
			OverlayScreen.UserLoggedOut => SetScreenActive<LoggedOutScreen>(), 
			OverlayScreen.ControllerPairingChanged => SetScreenActive<ControllerPairingScreen>(), 
			OverlayScreen.ControllerDisconnected => SetScreenActive<ControllerDisconnectedScreen>(), 
			_ => SetScreenActive<EngagementScreen>(), 
		};
	}
```

- `private static SetNativeStackTrace() : System.Void`  

```csharp
private static void SetNativeStackTrace()
	{
		Application.SetStackTraceLogType(LogType.Assert, StackTraceLogType.Full);
		Application.SetStackTraceLogType(LogType.Error, StackTraceLogType.Full);
		Application.SetStackTraceLogType(LogType.Exception, StackTraceLogType.Full);
		Application.SetStackTraceLogType(LogType.Log, StackTraceLogType.Full);
		Application.SetStackTraceLogType(LogType.Warning, StackTraceLogType.Full);
		UnityEngine.Debug.Log("Game version: " + Version.current.fullVersion);
		UnityEngine.Debug.Log(GetSystemInfoString());
	}
```

- `public SetScreenActive<T>() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SetScreenActive<T>();
```

- `private static SetupCustomAssetTypes() : System.Void`  

```csharp
[RuntimeInitializeOnLoadMethod]
	private static void SetupCustomAssetTypes()
	{
		DefaultAssetFactory.instance.AddSupportedType(".SaveGameMetadata", () => new SaveGameMetadata());
		DefaultAssetFactory.instance.AddSupportedType(".MapMetadata", () => new MapMetadata());
		DefaultAssetFactory.instance.AddSupportedType(".CinematicCamera", () => new CinematicCameraAsset());
	}
```

- `private static SetWindowsTitle() : System.Void`  

```csharp
[RuntimeInitializeOnLoadMethod]
	private static void SetWindowsTitle()
	{
		IntPtr intPtr = FindWindow(null, Application.productName);
		if (intPtr != IntPtr.Zero)
		{
			SetWindowText(intPtr, "Cities: Skylines II");
		}
	}
```

- `private static SetWindowText(System.IntPtr hWnd, System.String lpString) : System.Boolean`  

```csharp
private static System.Boolean SetWindowText(System.IntPtr hWnd, System.String lpString);
```

- `private ShowFallbackUI(System.Exception ex) : System.Void`  

```csharp
private void ShowFallbackUI(Exception ex)
	{
		if (m_UIManager == null)
		{
			m_UIManager = new UIManager(developerMode: false);
		}
		ErrorPage errorPage = new ErrorPage();
		errorPage.AddAction("quit", QuitGame);
		errorPage.AddAction("visit", delegate
		{
			try
			{
				Process.Start(new ProcessStartInfo
				{
					FileName = "https://pdxint.at/3Do979W",
					UseShellExecute = true
				});
			}
			catch
			{
				QuitGame();
			}
		});
		errorPage.SetStopCode(ex);
		errorPage.SetRoot(EnvPath.kContentPath + "/Game/UI/.fatal", EnvPath.kContentPath + "/Game/.fatal");
		errorPage.SetFonts(EnvPath.kContentPath + "/Game/UI/Fonts", EnvPath.kContentPath + "/Game/Fonts.cok");
		Colossal.UI.UISystem.Settings settings = Colossal.UI.UISystem.Settings.New;
		settings.resourceHandler = new FatalResourceHandler(errorPage);
		settings.enableDebugger = false;
		Colossal.UI.UISystem uISystem = m_UIManager.CreateUISystem(settings);
		UIView.Settings settings2 = UIView.Settings.New;
		settings2.liveReload = true;
		uISystem.CreateView("fatal://error", settings2, GetComponent<Camera>()).enabled = true;
		if (m_UIInputSystem != null)
		{
			m_UIInputSystem.Dispose();
		}
		m_UIInputSystem = new UIInputSystem(uISystem);
		if (!shouldUpdateManager)
		{
			RegisterUpdater(delegate
			{
				m_UIInputSystem.DispatchInputEvents();
				m_UIManager.Update();
				return false;
			});
		}
	}
```

- `private SubscribeToGdkUserEvents() : System.Void`  

```csharp
private void SubscribeToGdkUserEvents()
	{
		PlatformManager.instance.onUserUpdated += async delegate(IUserSupport psi, UserChangedFlags flags)
		{
			if (PlatformManager.instance.IsPrincipalUserIntegration(psi))
			{
				if (flags.HasFlag(UserChangedFlags.UserSigningOut))
				{
					await UnregisterDb();
				}
				if (flags.HasFlag(UserChangedFlags.UserSignedInAgain) || flags.HasFlag(UserChangedFlags.UserStatus))
				{
					if (AssetDatabase.global.databases.FirstOrDefault((IAssetDatabase db) => db.name == "GdkCloud") == null)
					{
						await RegisterDb();
					}
					else if (flags.HasFlag(UserChangedFlags.UserStatus) && !flags.HasFlag(UserChangedFlags.ChangingUser))
					{
						await UnregisterDb();
						await RegisterDb();
					}
				}
			}
		};
		static async Task RegisterDb()
		{
			AssetDatabase<GdkCloud> cloudDatabase = AssetDatabase<GdkCloud>.instance;
			await AssetDatabase.global.RegisterDatabase(cloudDatabase);
			await cloudDatabase.PopulateFromDataSource(priorityData: false, CancellationToken.None, TaskManager.instance.progress.GetSubProgress());
		}
		static async Task UnregisterDb()
		{
			if (await AssetDatabase.global.UnregisterDatabase(AssetDatabase<GdkCloud>.instance))
			{
				AssetDatabase<GdkCloud>.instance.Dispose();
			}
		}
	}
```

- `public TakeScreenshot() : System.Void`  

```csharp
public void TakeScreenshot()
	{
		StartCoroutine(CaptureScreenshot());
	}
```

- `private TelemetryReady() : System.Void`  

```csharp
private void TelemetryReady()
	{
		if (!m_StartUpTelemetryFired)
		{
			Telemetry.FireSessionStartEvents();
			PlatformManager.instance.onAchievementUpdated += delegate(IAchievementsSupport p, AchievementId a)
			{
				Telemetry.AchievementUnlocked(a);
			};
			m_StartUpTelemetryFired = true;
		}
	}
```

- `private TerminateGame() : System.Threading.Tasks.Task`  

```csharp
private async Task TerminateGame()
	{
		if (m_Cts == null)
		{
			m_State = State.Terminated;
			QuitGame();
		}
		else
		{
			if (m_State == State.Quitting || m_State == State.Terminated)
			{
				return;
			}
			try
			{
				using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
				{
					log?.InfoFormat("GameManager destroyed ({0}ms)", t.TotalMilliseconds);
				}))
				{
					State quittingState = m_State;
					m_State = State.Quitting;
					m_QuitRequested.Cancel();
					await TaskManager.instance.Complete("SaveLoadGame");
					if (quittingState >= State.WorldReady)
					{
						LauncherSettings.SaveSettings(settings);
						await TaskManager.instance.SharedTask("CacheAssets", () => AssetDatabase.global.SaveSettings());
					}
					TaskManager.instance.onNotifyProgress -= NotifyProgress;
					m_Cts.Cancel();
					m_ModManager?.Dispose();
					DestroyWorld();
					DisposeThumbnails();
					bool flag = await DisposePlatforms().AwaitWithTimeout(TimeSpan.FromSeconds(10.0));
					ReleaseUI();
					InputManager.DestroyInstance();
					StopAllCoroutines();
					CoroutineHost.Register(null);
					bool flag2 = flag;
					flag = flag2 & await TaskManager.instance.CompleteAndClear().AwaitWithTimeout(TimeSpan.FromSeconds(10.0));
					VolumeHelper.Dispose();
					AssetDatabase.global.Dispose();
					LogManager.ReleaseResources();
					Colossal.Gizmos.ReleaseResources();
					LogManager.stdOutActive = false;
					ReleaseConsole();
					onGameLoadingComplete -= OnMainMenuReached;
					TestScenarioSystem.Destroy();
					instance = null;
					Application.focusChanged -= FocusChanged;
					if (flag)
					{
						UnityEngine.Debug.Log("Game terminated successfully");
					}
					else
					{
						UnityEngine.Debug.Log("Game terminated due to timeout");
					}
				}
			}
			catch (Exception exception)
			{
				instance = null;
				log.Error(exception);
			}
			finally
			{
				m_State = State.Terminated;
				QuitGame();
			}
		}
	}
```

- `private TryCatchUnhandledExceptions() : System.Void`  

```csharp
private void TryCatchUnhandledExceptions()
	{
		System.Threading.Tasks.TaskScheduler.UnobservedTaskException += delegate(object sender, UnobservedTaskExceptionEventArgs e)
		{
			e.SetObserved();
			log.Critical(e.Exception, "Unobserved exception triggered");
		};
		AppDomain.CurrentDomain.UnhandledException += delegate(object sender, UnhandledExceptionEventArgs e)
		{
			Exception exception = (Exception)e.ExceptionObject;
			log.Critical(exception, "Unhandled domain exception triggered");
		};
	}
```

- `public UnregisterUpdater(System.Guid guid) : System.Boolean`  

```csharp
public bool UnregisterUpdater(Guid guid)
	{
		if (m_Updaters.TryRemove(guid, out var value))
		{
			log.DebugFormat("Updater {0} with {1} unregistered", guid.ToLowerNoDashString(), value.Method.Name);
			return true;
		}
		log.DebugFormat("Updater {0} was not found");
		return false;
	}
```

- `private Update() : System.Void`  

```csharp
private void Update()
	{
		if (shouldUpdateManager && !m_Cts.IsCancellationRequested)
		{
			TestScenarioSystem.instance.Update();
			InputManager.instance.Update();
			m_UIInputSystem.DispatchInputEvents(InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse);
			UpdateWorld();
			UpdateUI();
			PostUpdateWorld();
		}
		UpdateUpdaters();
		UpdatePlatforms();
	}
```

- `private UpdatePlatforms() : System.Void`  

```csharp
private void UpdatePlatforms()
	{
		PlatformManager.instance.Update();
	}
```

- `private UpdateUI() : System.Void`  

```csharp
private void UpdateUI()
	{
		m_UIManager.Update();
		userInterface.Update();
	}
```

- `private UpdateUpdaters() : System.Void`  

```csharp
private void UpdateUpdaters()
	{
		foreach (KeyValuePair<Guid, Func<bool>> updater in m_Updaters)
		{
			if (updater.Value())
			{
				UnregisterUpdater(updater.Key);
			}
		}
	}
```

- `private UpdateWorld() : System.Void`  

```csharp
private void UpdateWorld()
	{
		if (shouldUpdateWorld)
		{
			CORuntimeApplication.ResetUpdateAllocator(m_World);
			m_UpdateSystem.Update(SystemUpdatePhase.MainLoop);
		}
	}
```

- `public WaitForReadyState() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public async Task<bool> WaitForReadyState()
	{
		_ = 1;
		try
		{
			await using (m_Cts.Token.Register(delegate
			{
				m_WorldReadySource.TrySetCanceled();
			}))
			{
				await m_WorldReadySource.Task.ConfigureAwait(continueOnCapturedContext: false);
			}
			return m_WorldReadySource.Task.IsCompletedSuccessfully;
		}
		catch (OperationCanceledException)
		{
			return false;
		}
	}
```

- `private WantsToQuit() : System.Boolean`  

```csharp
private bool WantsToQuit()
	{
		if (m_State != State.Quitting && m_State != State.Terminated)
		{
			TerminateGame();
			return false;
		}
		if (m_State == State.Quitting)
		{
			UnityEngine.Debug.LogWarning("TerminateGame is already in progress, please wait.");
			return false;
		}
		return true;
	}
```


## Events

- `onGameSaveLoad` : `Game.SceneFlow.GameManager+EventGameSaveLoad`  

```csharp
public event Game.SceneFlow.GameManager+EventGameSaveLoad onGameSaveLoad;
```

- `onGamePreload` : `Game.SceneFlow.GameManager+EventGamePreload`  

```csharp
public event Game.SceneFlow.GameManager+EventGamePreload onGamePreload;
```

- `onGameLoadingComplete` : `Game.SceneFlow.GameManager+EventGamePreload`  

```csharp
public event Game.SceneFlow.GameManager+EventGamePreload onGameLoadingComplete;
```

- `onWorldReady` : `Game.SceneFlow.GameManager+EventCallback`  

```csharp
public event Game.SceneFlow.GameManager+EventCallback onWorldReady;
```


## Nested types

- `Game.SceneFlow.GameManager+Configuration`  
- `Game.SceneFlow.GameManager+State`  
- `Game.SceneFlow.GameManager+EventCallback`  
- `Game.SceneFlow.GameManager+EventGamePreload`  
- `Game.SceneFlow.GameManager+EventGameSaveLoad`  
- `Game.SceneFlow.GameManager+LocalTypeCache`  
- `Game.SceneFlow.GameManager+<<SubscribeToGdkUserEvents>g__RegisterDb|108_2>d`  
- `Game.SceneFlow.GameManager+<<SubscribeToGdkUserEvents>g__UnregisterDb|108_1>d`  
- `Game.SceneFlow.GameManager+<>c`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass105_0`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass105_1`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass105_2`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass105_3`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass132_0`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass152_0`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass39_0`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass91_0`  
- `Game.SceneFlow.GameManager+<>c__DisplayClass93_0`  
- `Game.SceneFlow.GameManager+<Awake>d__51`  
- `Game.SceneFlow.GameManager+<CaptureScreenshot>d__191`  
- `Game.SceneFlow.GameManager+<DisposePlatforms>d__110`  
- `Game.SceneFlow.GameManager+<Initialize>d__54`  
- `Game.SceneFlow.GameManager+<InitializePlatformManager>d__107`  
- `Game.SceneFlow.GameManager+<InitializeUI>d__125`  
- `Game.SceneFlow.GameManager+<Load>d__93`  
- `Game.SceneFlow.GameManager+<LoadAssetLibraryAsync>d__153`  
- `Game.SceneFlow.GameManager+<MainMenu>d__99`  
- `Game.SceneFlow.GameManager+<RegisterCancellationOnQuit>d__39`  
- `Game.SceneFlow.GameManager+<RegisterPdxSdk>d__105`  
- `Game.SceneFlow.GameManager+<Save>d__91`  
- `Game.SceneFlow.GameManager+<SaveSimulationData>d__89`  
- `Game.SceneFlow.GameManager+<TerminateGame>d__64`  
- `Game.SceneFlow.GameManager+<WaitForReadyState>d__57`  


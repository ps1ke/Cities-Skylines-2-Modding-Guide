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
public System.Boolean ArePrerequisitesMet(System.String[] contentPrerequisites);
```

- `public ArePrerequisitesMet<T>(Colossal.IO.AssetDatabase.Metadata<T> meta) : System.Boolean`  

```csharp
public System.Boolean ArePrerequisitesMet<T>(Colossal.IO.AssetDatabase.Metadata<T> meta);
```

- `private AutoLoad(Colossal.IO.AssetDatabase.IAssetData asset) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> AutoLoad(Colossal.IO.AssetDatabase.IAssetData asset);
```

- `private AutoLoad(Colossal.Hash128 guid) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> AutoLoad(Colossal.Hash128 guid);
```

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private CaptureScreenshot() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator CaptureScreenshot();
```

- `private CheckCapabilities() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task CheckCapabilities();
```

- `private CheckValidity() : System.Boolean`  

```csharp
private System.Boolean CheckValidity();
```

- `private CleanupMemory() : System.Void`  

```csharp
private System.Void CleanupMemory();
```

- `private CreateSystems() : System.Void`  

```csharp
private System.Void CreateSystems();
```

- `private CreateUISystems() : System.Void`  

```csharp
private System.Void CreateUISystems();
```

- `private CreateWorld() : System.Void`  

```csharp
private System.Void CreateWorld();
```

- `private DestroyWorld() : System.Void`  

```csharp
private System.Void DestroyWorld();
```

- `private static DetectModdingRuntime() : System.Void`  

```csharp
private static System.Void DetectModdingRuntime();
```

- `private static DetectModdingRuntimeName() : System.String`  

```csharp
private static System.String DetectModdingRuntimeName();
```

- `private DisableCameraRendering() : System.Void`  

```csharp
private System.Void DisableCameraRendering();
```

- `private DisposePlatforms() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task DisposePlatforms();
```

- `private DisposeThumbnails() : System.Void`  

```csharp
private System.Void DisposeThumbnails();
```

- `private EnableCameraRendering() : System.Void`  

```csharp
private System.Void EnableCameraRendering();
```

- `private EnableMemoryLeaksDetection() : System.Void`  

```csharp
private System.Void EnableMemoryLeaksDetection();
```

- `private EnableSettingsDependantObjects() : System.Void`  

```csharp
private System.Void EnableSettingsDependantObjects();
```

- `private static FindWindow(System.String strClassName, System.String strWindowName) : System.IntPtr`  

```csharp
private static System.IntPtr FindWindow(System.String strClassName, System.String strWindowName);
```

- `public FocusChanged(System.Boolean hasFocus) : System.Void`  

```csharp
public System.Void FocusChanged(System.Boolean hasFocus);
```

- `private Game.Threading.ICoroutineHost.StartCoroutine(System.Collections.IEnumerator routine) : UnityEngine.Coroutine`  

```csharp
private UnityEngine.Coroutine Game.Threading.ICoroutineHost.StartCoroutine(System.Collections.IEnumerator routine);
```

- `public GetAvailablePrerequisitesNames() : System.String[]`  

```csharp
public System.String[] GetAvailablePrerequisitesNames();
```

- `private static GetDefaultBacktraceAttributes() : System.Collections.Generic.Dictionary<System.String, System.String>`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, System.String> GetDefaultBacktraceAttributes();
```

- `private GetSessionGuid(Colossal.Serialization.Entities.Purpose purpose, System.Guid existingGuid) : System.Guid`  

```csharp
private System.Guid GetSessionGuid(Colossal.Serialization.Entities.Purpose purpose, System.Guid existingGuid);
```

- `private GetStdoutCaptureMode(System.String option) : Game.SceneFlow.GameManager+Configuration+StdoutCaptureMode`  

```csharp
private Game.SceneFlow.GameManager+Configuration+StdoutCaptureMode GetStdoutCaptureMode(System.String option);
```

- `public static GetSystemInfoString() : System.String`  

```csharp
public static System.String GetSystemInfoString();
```

- `public static GetVersionsInfo() : System.String`  

```csharp
public static System.String GetVersionsInfo();
```

- `private static GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount) : System.Int32`  

```csharp
private static System.Int32 GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount);
```

- `private HandleConfiguration() : System.Boolean`  

```csharp
private System.Boolean HandleConfiguration();
```

- `private HandleDeviceAssociationLost() : System.Void`  

```csharp
private System.Void HandleDeviceAssociationLost();
```

- `private HandleDeviceDisconnected() : System.Void`  

```csharp
private System.Void HandleDeviceDisconnected();
```

- `private HandleDevicePaired() : System.Void`  

```csharp
private System.Void HandleDevicePaired();
```

- `private HandleUserFolderVersion() : System.Void`  

```csharp
private System.Void HandleUserFolderVersion();
```

- `private HandleUserUpdated(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  

```csharp
private System.Void HandleUserUpdated(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags flags);
```

- `private InitConsole() : System.Void`  

```csharp
private System.Void InitConsole();
```

- `private Initialize() : System.Void`  

```csharp
private System.Void Initialize();
```

- `private InitializeLocalization() : System.Void`  

```csharp
private System.Void InitializeLocalization();
```

- `private InitializeModManager(System.Boolean ignoreParadox = False) : System.Void`  

```csharp
private System.Void InitializeModManager(System.Boolean ignoreParadox);
```

- `private InitializePlatformManager() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task InitializePlatformManager();
```

- `private InitializeThumbnails() : System.Void`  

```csharp
private System.Void InitializeThumbnails();
```

- `private InitializeUI() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task InitializeUI();
```

- `private LateUpdate() : System.Void`  

```csharp
private System.Void LateUpdate();
```

- `private LateUpdateWorld() : System.Void`  

```csharp
private System.Void LateUpdateWorld();
```

- `private static ListHarmonyPatches() : System.Void`  

```csharp
private static System.Void ListHarmonyPatches();
```

- `private Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.AsyncReadDescriptor descriptor, Colossal.Hash128 instigatorGuid, System.Guid sessionGuid) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.AsyncReadDescriptor descriptor, Colossal.Hash128 instigatorGuid, System.Guid sessionGuid);
```

- `public Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.IAssetData asset = null) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.IAssetData asset);
```

- `public Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.Hash128 guid) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.Hash128 guid);
```

- `private LoadAssetLibraryAsync() : System.Threading.Tasks.Task<Game.SceneFlow.AssetLibrary>`  

```csharp
private System.Threading.Tasks.Task<Game.SceneFlow.AssetLibrary> LoadAssetLibraryAsync();
```

- `private LoadPrefabs() : System.Void`  

```csharp
private System.Void LoadPrefabs();
```

- `private LoadSimulationData(Colossal.Serialization.Entities.Context context, Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task LoadSimulationData(Colossal.Serialization.Entities.Context context, Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor);
```

- `private LoadUnityPrefabs() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task LoadUnityPrefabs();
```

- `public MainMenu() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> MainMenu();
```

- `private static MaskArguments(System.String[] cmdLine) : System.String[]`  

```csharp
private static System.String[] MaskArguments(System.String[] cmdLine);
```

- `private static MergeAdditionalCommandLineArguments(System.String[] cmdLineArgs, System.String additionalCmdLine) : System.String[]`  

```csharp
private static System.String[] MergeAdditionalCommandLineArguments(System.String[] cmdLineArgs, System.String additionalCmdLine);
```

- `private NotifyProgress(System.String identifier, System.Int32 progress) : System.Void`  

```csharp
private System.Void NotifyProgress(System.String identifier, System.Int32 progress);
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```

- `private OnGUI() : System.Void`  

```csharp
private System.Void OnGUI();
```

- `private OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private System.Void OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `private ParseOptions() : System.Void`  

```csharp
private System.Void ParseOptions();
```

- `private PostUpdateWorld() : System.Void`  

```csharp
private System.Void PostUpdateWorld();
```

- `private PreparePersistentStorage() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task PreparePersistentStorage();
```

- `private static PrintIndividualPatches(Colossal.Logging.ILog moddingLog, System.String patchType, System.Collections.Generic.IEnumerable<System.Object> patches, Game.SceneFlow.GameManager+LocalTypeCache typeCache) : System.Void`  

```csharp
private static System.Void PrintIndividualPatches(Colossal.Logging.ILog moddingLog, System.String patchType, System.Collections.Generic.IEnumerable<System.Object> patches, Game.SceneFlow.GameManager+LocalTypeCache typeCache);
```

- `private static PrintPatchDetails(Colossal.Logging.ILog moddingLog, System.Object patchInfo, System.Type patchInfoType, Game.SceneFlow.GameManager+LocalTypeCache typeCache) : System.Void`  

```csharp
private static System.Void PrintPatchDetails(Colossal.Logging.ILog moddingLog, System.Object patchInfo, System.Type patchInfoType, Game.SceneFlow.GameManager+LocalTypeCache typeCache);
```

- `public static QuitGame() : System.Void`  

```csharp
public static System.Void QuitGame();
```

- `public RegisterCancellationOnQuit(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Boolean stateOnCancel) : System.Void`  

```csharp
public System.Void RegisterCancellationOnQuit(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Boolean stateOnCancel);
```

- `private RegisterDeviceAndUserListeners() : System.Void`  

```csharp
private System.Void RegisterDeviceAndUserListeners();
```

- `private RegisterPdxSdk() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPdxSdk();
```

- `public RegisterUpdater(System.Action action) : System.Guid`  

```csharp
public System.Guid RegisterUpdater(System.Action action);
```

- `public RegisterUpdater(System.Func<System.Boolean> func) : System.Guid`  

```csharp
public System.Guid RegisterUpdater(System.Func<System.Boolean> func);
```

- `private ReleaseConsole() : System.Void`  

```csharp
private System.Void ReleaseConsole();
```

- `private ReleaseUI() : System.Void`  

```csharp
private System.Void ReleaseUI();
```

- `private ReportBootProgress(System.Single progress) : System.Void`  

```csharp
private System.Void ReportBootProgress(System.Single progress);
```

- `public RunOnMainThread(System.Action action) : System.Void`  

```csharp
public System.Void RunOnMainThread(System.Action action);
```

- `public Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, UnityEngine.Texture savePreview) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, UnityEngine.Texture savePreview);
```

- `public Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Game.UI.ScreenCaptureHelper+AsyncRequest previewRequest) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Game.UI.ScreenCaptureHelper+AsyncRequest previewRequest);
```

- `private SaveSimulationData(Colossal.Serialization.Entities.Context context, System.IO.Stream stream) : System.Threading.Tasks.Task<System.String[]>`  

```csharp
private System.Threading.Tasks.Task<System.String[]> SaveSimulationData(Colossal.Serialization.Entities.Context context, System.IO.Stream stream);
```

- `private SetInitialEngagementScreenActive() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task SetInitialEngagementScreenActive();
```

- `private static SetNativeStackTrace() : System.Void`  

```csharp
private static System.Void SetNativeStackTrace();
```

- `public SetScreenActive<T>() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SetScreenActive<T>();
```

- `private static SetupCustomAssetTypes() : System.Void`  

```csharp
private static System.Void SetupCustomAssetTypes();
```

- `private static SetWindowsTitle() : System.Void`  

```csharp
private static System.Void SetWindowsTitle();
```

- `private static SetWindowText(System.IntPtr hWnd, System.String lpString) : System.Boolean`  

```csharp
private static System.Boolean SetWindowText(System.IntPtr hWnd, System.String lpString);
```

- `private ShowFallbackUI(System.Exception ex) : System.Void`  

```csharp
private System.Void ShowFallbackUI(System.Exception ex);
```

- `private SubscribeToGdkUserEvents() : System.Void`  

```csharp
private System.Void SubscribeToGdkUserEvents();
```

- `public TakeScreenshot() : System.Void`  

```csharp
public System.Void TakeScreenshot();
```

- `private TelemetryReady() : System.Void`  

```csharp
private System.Void TelemetryReady();
```

- `private TerminateGame() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task TerminateGame();
```

- `private TryCatchUnhandledExceptions() : System.Void`  

```csharp
private System.Void TryCatchUnhandledExceptions();
```

- `public UnregisterUpdater(System.Guid guid) : System.Boolean`  

```csharp
public System.Boolean UnregisterUpdater(System.Guid guid);
```

- `private Update() : System.Void`  

```csharp
private System.Void Update();
```

- `private UpdatePlatforms() : System.Void`  

```csharp
private System.Void UpdatePlatforms();
```

- `private UpdateUI() : System.Void`  

```csharp
private System.Void UpdateUI();
```

- `private UpdateUpdaters() : System.Void`  

```csharp
private System.Void UpdateUpdaters();
```

- `private UpdateWorld() : System.Void`  

```csharp
private System.Void UpdateWorld();
```

- `public WaitForReadyState() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> WaitForReadyState();
```

- `private WantsToQuit() : System.Boolean`  

```csharp
private System.Boolean WantsToQuit();
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


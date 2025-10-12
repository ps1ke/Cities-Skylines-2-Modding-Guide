# Game.SceneFlow.GameManager

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Threading.ICoroutineHost`  

## Fields

- `private System.String[] <cmdLine>k__BackingField`  
- `private Game.SceneFlow.GameManager+Configuration m_Configuration`  
- `private System.String m_AdditionalCommandLineToggles`  
- `private Game.GameMode <gameMode>k__BackingField`  
- `private Game.Settings.SharedSettings <settings>k__BackingField`  
- `private Game.Modding.ModManager m_ModManager`  
- `private System.Threading.CancellationTokenSource m_Cts`  
- `private readonly System.Threading.CancellationTokenSource m_QuitRequested`  
- `private readonly System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_WorldReadySource`  
- `public UnityEngine.GameObject[] m_SettingsDependantObjects`  
- `private System.Int32 m_MainThreadId`  
- `private Game.SceneFlow.GameManager+State m_State`  
- `private Game.SceneFlow.OverlayScreen m_InitialEngagementScreen`  
- `private System.Boolean m_IsEngagementStarted`  
- `private Game.SceneFlow.GameManager+EventGameSaveLoad onGameSaveLoad`  
- `private Game.SceneFlow.GameManager+EventGamePreload onGamePreload`  
- `private Game.SceneFlow.GameManager+EventGamePreload onGameLoadingComplete`  
- `private Game.SceneFlow.GameManager+EventCallback onWorldReady`  
- `private System.Boolean m_StartUpTelemetryFired`  
- `private System.String m_UILocation`  
- `private Colossal.UI.UIManager m_UIManager`  
- `private Colossal.UI.UIInputSystem m_UIInputSystem`  
- `private Colossal.Localization.LocalizationManager <localizationManager>k__BackingField`  
- `private Game.SceneFlow.UserInterface <userInterface>k__BackingField`  
- `private readonly System.Collections.Concurrent.ConcurrentDictionary<System.Guid, System.Func<System.Boolean>> m_Updaters`  
- `private Game.UI.Thumbnails.ThumbnailCache <thumbnailCache>k__BackingField`  
- `private UnityEngine.LayerMask m_DefaultCullingMask`  
- `private UnityEngine.LayerMask m_DefaultVolumeLayerMask`  
- `private Game.Debug.ConsoleWindow m_Console`  
- `private Unity.Entities.World m_World`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.Serialization.LoadGameSystem m_DeserializationSystem`  
- `private Game.Serialization.SaveGameSystem m_SerializationSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private static Colossal.Logging.ILog log`  
- `private static Game.SceneFlow.GameManager <instance>k__BackingField`  
- `private static System.String s_ModdingRuntime`  
- `public static const System.String kInMainMenuState`  
- `public static const System.String kInGameState`  
- `public static const System.String kInEditorState`  
- `private static const System.String kBootTask`  

## Properties

- `public System.String[] cmdLine { get; private set }`  
- `public Game.SceneFlow.GameManager+Configuration configuration { get }`  
- `public static Game.SceneFlow.GameManager instance { get; private set }`  
- `public System.Boolean isMainThread { get }`  
- `public Game.GameMode gameMode { get; private set }`  
- `public System.Boolean isGameLoading { get }`  
- `public Game.Settings.SharedSettings settings { get; private set }`  
- `public Game.Modding.ModManager modManager { get }`  
- `public System.Threading.CancellationToken terminationToken { get }`  
- `public Game.SceneFlow.GameManager+State state { get }`  
- `public System.Boolean shouldUpdateManager { get }`  
- `public System.Boolean shouldUpdateWorld { get }`  
- `public static Colossal.UI.UIInputSystem UIInputSystem { get }`  
- `public Colossal.Localization.LocalizationManager localizationManager { get; private set }`  
- `public Game.SceneFlow.UserInterface userInterface { get; private set }`  
- `public Game.UI.Thumbnails.ThumbnailCache thumbnailCache { get; private set }`  

## Constructors

- `public GameManager()`  

## Methods

- `internal static <HandleUserFolderVersion>g__DeleteSettings|177_0(System.String settingsPath) : System.Void`  
- `private <Initialize>b__54_1() : System.Threading.Tasks.Task`  
- `private <Initialize>b__54_2() : System.Threading.Tasks.Task`  
- `private <ParseOptions>b__12_0(System.String option) : System.Void`  
- `private <ParseOptions>b__12_1(System.String option) : System.Void`  
- `private <ParseOptions>b__12_10(System.String option) : System.Void`  
- `private <ParseOptions>b__12_11(System.String option) : System.Void`  
- `private <ParseOptions>b__12_12(System.String option) : System.Void`  
- `private <ParseOptions>b__12_13(System.String option) : System.Void`  
- `private <ParseOptions>b__12_14(System.String option) : System.Void`  
- `private <ParseOptions>b__12_15(System.String option) : System.Void`  
- `private <ParseOptions>b__12_16(System.String option) : System.Void`  
- `private <ParseOptions>b__12_3(System.String option) : System.Void`  
- `private <ParseOptions>b__12_4(System.String option) : System.Void`  
- `private <ParseOptions>b__12_5(System.String option) : System.Void`  
- `private <ParseOptions>b__12_6(System.String option) : System.Void`  
- `private <ParseOptions>b__12_7(System.String option) : System.Void`  
- `private <ParseOptions>b__12_8(System.String option) : System.Void`  
- `private <ParseOptions>b__12_9(System.String option) : System.Void`  
- `private <RegisterPdxSdk>b__105_10(System.String localeId) : System.String`  
- `private <RegisterPdxSdk>b__105_16(Colossal.IO.AssetDatabase.UIModuleAsset asset, System.Boolean isInActivePlayset) : System.Void`  
- `private <RegisterPdxSdk>b__105_17(Colossal.IO.AssetDatabase.ExecutableAsset asset, System.Boolean isInActivePlayset) : System.Void`  
- `private <RegisterPdxSdk>b__105_2(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remaining) : System.Void`  
- `private <RegisterPdxSdk>b__105_6(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlcs) : System.Void`  
- `private <RegisterPdxSdk>g__OnActivePlaysetChanged|105_13() : System.Void`  
- `private <RegisterPdxSdk>g__OnAssetChanged|105_14(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `private <SaveSimulationData>b__89_0(Unity.Entities.Entity x) : System.String`  
- `private <ShowFallbackUI>b__124_1() : System.Boolean`  
- `internal static <SubscribeToGdkUserEvents>g__RegisterDb|108_2() : System.Threading.Tasks.Task`  
- `internal static <SubscribeToGdkUserEvents>g__UnregisterDb|108_1() : System.Threading.Tasks.Task`  
- `private <WaitForReadyState>b__57_0() : System.Void`  
- `public ArePrerequisitesMet(System.String[] contentPrerequisites) : System.Boolean`  
- `public ArePrerequisitesMet<T>(Colossal.IO.AssetDatabase.Metadata<T> meta) : System.Boolean`  
- `private AutoLoad(Colossal.IO.AssetDatabase.IAssetData asset) : System.Threading.Tasks.Task<System.Boolean>`  
- `private AutoLoad(Colossal.Hash128 guid) : System.Threading.Tasks.Task<System.Boolean>`  
- `private Awake() : System.Void`  
- `private CaptureScreenshot() : System.Collections.IEnumerator`  
- `private CheckCapabilities() : System.Threading.Tasks.Task`  
- `private CheckValidity() : System.Boolean`  
- `private CleanupMemory() : System.Void`  
- `private CreateSystems() : System.Void`  
- `private CreateUISystems() : System.Void`  
- `private CreateWorld() : System.Void`  
- `private DestroyWorld() : System.Void`  
- `private static DetectModdingRuntime() : System.Void`  
- `private static DetectModdingRuntimeName() : System.String`  
- `private DisableCameraRendering() : System.Void`  
- `private DisposePlatforms() : System.Threading.Tasks.Task`  
- `private DisposeThumbnails() : System.Void`  
- `private EnableCameraRendering() : System.Void`  
- `private EnableMemoryLeaksDetection() : System.Void`  
- `private EnableSettingsDependantObjects() : System.Void`  
- `private static FindWindow(System.String strClassName, System.String strWindowName) : System.IntPtr`  
- `public FocusChanged(System.Boolean hasFocus) : System.Void`  
- `private Game.Threading.ICoroutineHost.StartCoroutine(System.Collections.IEnumerator routine) : UnityEngine.Coroutine`  
- `public GetAvailablePrerequisitesNames() : System.String[]`  
- `private static GetDefaultBacktraceAttributes() : System.Collections.Generic.Dictionary<System.String, System.String>`  
- `private GetSessionGuid(Colossal.Serialization.Entities.Purpose purpose, System.Guid existingGuid) : System.Guid`  
- `private GetStdoutCaptureMode(System.String option) : Game.SceneFlow.GameManager+Configuration+StdoutCaptureMode`  
- `public static GetSystemInfoString() : System.String`  
- `public static GetVersionsInfo() : System.String`  
- `private static GetWindowText(System.IntPtr hWnd, System.Text.StringBuilder lpString, System.Int32 nMaxCount) : System.Int32`  
- `private HandleConfiguration() : System.Boolean`  
- `private HandleDeviceAssociationLost() : System.Void`  
- `private HandleDeviceDisconnected() : System.Void`  
- `private HandleDevicePaired() : System.Void`  
- `private HandleUserFolderVersion() : System.Void`  
- `private HandleUserUpdated(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  
- `private InitConsole() : System.Void`  
- `private Initialize() : System.Void`  
- `private InitializeLocalization() : System.Void`  
- `private InitializeModManager(System.Boolean ignoreParadox = False) : System.Void`  
- `private InitializePlatformManager() : System.Threading.Tasks.Task`  
- `private InitializeThumbnails() : System.Void`  
- `private InitializeUI() : System.Threading.Tasks.Task`  
- `private LateUpdate() : System.Void`  
- `private LateUpdateWorld() : System.Void`  
- `private static ListHarmonyPatches() : System.Void`  
- `private Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.AsyncReadDescriptor descriptor, Colossal.Hash128 instigatorGuid, System.Guid sessionGuid) : System.Threading.Tasks.Task<System.Boolean>`  
- `public Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.IO.AssetDatabase.IAssetData asset = null) : System.Threading.Tasks.Task<System.Boolean>`  
- `public Load(Game.GameMode mode, Colossal.Serialization.Entities.Purpose purpose, Colossal.Hash128 guid) : System.Threading.Tasks.Task<System.Boolean>`  
- `private LoadAssetLibraryAsync() : System.Threading.Tasks.Task<Game.SceneFlow.AssetLibrary>`  
- `private LoadPrefabs() : System.Void`  
- `private LoadSimulationData(Colossal.Serialization.Entities.Context context, Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor) : System.Threading.Tasks.Task`  
- `private LoadUnityPrefabs() : System.Threading.Tasks.Task`  
- `public MainMenu() : System.Threading.Tasks.Task<System.Boolean>`  
- `private static MaskArguments(System.String[] cmdLine) : System.String[]`  
- `private static MergeAdditionalCommandLineArguments(System.String[] cmdLineArgs, System.String additionalCmdLine) : System.String[]`  
- `private NotifyProgress(System.String identifier, System.Int32 progress) : System.Void`  
- `private OnDestroy() : System.Void`  
- `private OnGUI() : System.Void`  
- `private OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `private ParseOptions() : System.Void`  
- `private PostUpdateWorld() : System.Void`  
- `private PreparePersistentStorage() : System.Threading.Tasks.Task`  
- `private static PrintIndividualPatches(Colossal.Logging.ILog moddingLog, System.String patchType, System.Collections.Generic.IEnumerable<System.Object> patches, Game.SceneFlow.GameManager+LocalTypeCache typeCache) : System.Void`  
- `private static PrintPatchDetails(Colossal.Logging.ILog moddingLog, System.Object patchInfo, System.Type patchInfoType, Game.SceneFlow.GameManager+LocalTypeCache typeCache) : System.Void`  
- `public static QuitGame() : System.Void`  
- `public RegisterCancellationOnQuit(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Boolean stateOnCancel) : System.Void`  
- `private RegisterDeviceAndUserListeners() : System.Void`  
- `private RegisterPdxSdk() : System.Threading.Tasks.Task`  
- `public RegisterUpdater(System.Action action) : System.Guid`  
- `public RegisterUpdater(System.Func<System.Boolean> func) : System.Guid`  
- `private ReleaseConsole() : System.Void`  
- `private ReleaseUI() : System.Void`  
- `private ReportBootProgress(System.Single progress) : System.Void`  
- `public RunOnMainThread(System.Action action) : System.Void`  
- `public Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, UnityEngine.Texture savePreview) : System.Threading.Tasks.Task<System.Boolean>`  
- `public Save(System.String saveName, Game.Assets.SaveInfo meta, Colossal.IO.AssetDatabase.ILocalAssetDatabase database, Game.UI.ScreenCaptureHelper+AsyncRequest previewRequest) : System.Threading.Tasks.Task<System.Boolean>`  
- `private SaveSimulationData(Colossal.Serialization.Entities.Context context, System.IO.Stream stream) : System.Threading.Tasks.Task<System.String[]>`  
- `private SetInitialEngagementScreenActive() : System.Threading.Tasks.Task`  
- `private static SetNativeStackTrace() : System.Void`  
- `public SetScreenActive<T>() : System.Threading.Tasks.Task`  
- `private static SetupCustomAssetTypes() : System.Void`  
- `private static SetWindowsTitle() : System.Void`  
- `private static SetWindowText(System.IntPtr hWnd, System.String lpString) : System.Boolean`  
- `private ShowFallbackUI(System.Exception ex) : System.Void`  
- `private SubscribeToGdkUserEvents() : System.Void`  
- `public TakeScreenshot() : System.Void`  
- `private TelemetryReady() : System.Void`  
- `private TerminateGame() : System.Threading.Tasks.Task`  
- `private TryCatchUnhandledExceptions() : System.Void`  
- `public UnregisterUpdater(System.Guid guid) : System.Boolean`  
- `private Update() : System.Void`  
- `private UpdatePlatforms() : System.Void`  
- `private UpdateUI() : System.Void`  
- `private UpdateUpdaters() : System.Void`  
- `private UpdateWorld() : System.Void`  
- `public WaitForReadyState() : System.Threading.Tasks.Task<System.Boolean>`  
- `private WantsToQuit() : System.Boolean`  

## Events

- `onGameSaveLoad` : `Game.SceneFlow.GameManager+EventGameSaveLoad`  
- `onGamePreload` : `Game.SceneFlow.GameManager+EventGamePreload`  
- `onGameLoadingComplete` : `Game.SceneFlow.GameManager+EventGamePreload`  
- `onWorldReady` : `Game.SceneFlow.GameManager+EventCallback`  

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


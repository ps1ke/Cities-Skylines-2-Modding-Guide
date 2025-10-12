# Colossal.PSI.Common.PlatformManager

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`, `Colossal.PSI.Common.IAppStateSupport`, `Colossal.PSI.Common.IPlatformSupport`, `Colossal.PSI.Common.IDeviceAssociationSupport`, `Colossal.PSI.Common.IDlcSupport`, `Colossal.PSI.Common.IModSupport`, `Colossal.PSI.Common.IModsUploadSupport`, `Colossal.PSI.Common.IOverlaySupport`, `Colossal.PSI.Common.IRemoteStorageSupport`, `Colossal.PSI.Common.IRichPresenceSupport`, `Colossal.PSI.Common.IScreenCaptureSupport`, `Colossal.PSI.Common.ITelemetrySupport`, `Colossal.PSI.Common.ITransferSupport`, `Colossal.PSI.Common.IUserSupport`, `Colossal.PSI.Common.IVirtualKeyboardSupport`  

## Fields

- `private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated`  
- `private System.Boolean m_AchievementsEnabled`  
- `private System.Threading.Tasks.Task m_InitializeAchievements`  
- `private Colossal.PSI.Common.OnAppStateChanged onAppStateChanged`  
- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  
- `private Colossal.PSI.Common.PlatformRegisteredHandler onPlatformRegistered`  
- `private Colossal.PSI.Common.OnConnectivityStatusChanged onConnectivityStatusChanged`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformServiceIntegration> m_PSIs`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformSupport> m_PlatformManagers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> m_RemoteStorages`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> m_UserBackends`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> m_ModsBackends`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITelemetrySupport> m_TelemetryBackends`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> m_AchievementsBackends`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRichPresenceSupport> m_RichPresenceHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> m_VirtualKeyboardHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> m_OverlayHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> m_TransferManagers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> m_DeviceAssociationHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDlcSupport> m_DlcBackends`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> m_AppStateHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> m_ScreenCaptureHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModsUploadSupport> m_ModsUploadHandlers`  
- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue`  
- `private Colossal.PSI.Common.IPlatformSupport m_PrincipalPlatform`  
- `private Colossal.PSI.Common.IUserSupport m_PrincipalUserBackend`  
- `private Colossal.PSI.Common.IAchievementsSupport m_PrincipalAchievementsBackend`  
- `private Colossal.PSI.Common.IVirtualKeyboardSupport m_PrincipalVirtualKeyboardHandler`  
- `private Colossal.PSI.Common.IOverlaySupport m_PrincipalOverlayHandler`  
- `private Colossal.PSI.Common.IDeviceAssociationSupport m_PrincipalDeviceAssociationHandler`  
- `private Colossal.PSI.Common.IRemoteStorageSupport m_PrincipalRemoteStorage`  
- `private Colossal.PSI.Common.IAppStateSupport m_PrincipalAppStateHandler`  
- `private Colossal.PSI.Common.IScreenCaptureSupport m_PrincipalScreenCaptureHandler`  
- `private Colossal.PSI.Common.IModsUploadSupport m_PrincipalModsUploadHandler`  
- `private Colossal.PSI.Common.ITelemetrySupport m_PrincipalTelemetryHandler`  
- `private System.Boolean m_IsInitialized`  
- `private Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler onDeviceAssociationChanged`  
- `private Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged`  
- `private Colossal.PSI.Common.ModEventHandler onModDownloadStarted`  
- `private Colossal.PSI.Common.ModEventHandler onModDownloadCompleted`  
- `private Colossal.PSI.Common.ModEventHandler onModDownloadFailed`  
- `private Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted`  
- `private Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress`  
- `private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.Func<System.String>> m_Keys`  
- `private System.Boolean allowScreenshot`  
- `private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing`  
- `private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated`  
- `private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed`  
- `private static Colossal.Logging.ILog log`  
- `private static Colossal.PSI.Common.PlatformManager s_Instance`  
- `private static readonly System.Byte[] kEmpty`  
- `private static const System.String kUserData`  

## Properties

- `public System.Boolean achievementsEnabled { get; set }`  
- `public static Colossal.PSI.Common.PlatformManager instance { get }`  
- `public System.String name { get }`  
- `public System.Boolean isInitialized { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformSupport> platformManagers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRemoteStorageSupport> remoteStorages { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IUserSupport> userBackends { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IModSupport> modsBackends { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITelemetrySupport> telemetryBackends { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAchievementsSupport> achievementsBackends { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRichPresenceSupport> richPresenceHandlers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IVirtualKeyboardSupport> virtualKeyboardHandlers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IOverlaySupport> overlayHandlers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITransferSupport> transferManagers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDeviceAssociationSupport> deviceAssociationHandlers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDlcSupport> dlcBackends { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAppStateSupport> appStateHandlers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IScreenCaptureSupport> screenCaptureHandlers { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformServiceIntegration> platformServiceIntegrations { get }`  
- `public System.String principalPlatformName { get }`  
- `public System.Boolean hasConnectivity { get }`  
- `public System.Int32 dlcCount { get }`  
- `public System.Boolean isOverlaySupported { get }`  
- `public System.Boolean isExternallyControlled { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Func<System.String>> richPresenceKeys { get }`  
- `public System.Boolean requiresEngagement { get }`  
- `public System.Boolean isUserSignedIn { get }`  
- `public System.String userName { get }`  
- `public System.Boolean supportsUserSwitching { get }`  
- `public System.Boolean supportsUserSection { get }`  
- `public System.String userSpecificPath { get }`  
- `public System.Boolean hasUgcPrivilege { get }`  
- `public System.Boolean passThroughVKeyboard { get }`  

## Constructors

- `private PlatformManager()`  

## Methods

- `private <ForwardAchievementCallbacks>b__8_0(Colossal.PSI.Common.IAchievementsSupport p, Colossal.PSI.Common.AchievementId achievementId) : System.Void`  
- `private <ForwardAppStateCallbacks>b__20_0(Colossal.PSI.Common.IPlatformServiceIntegration p, Colossal.PSI.Common.AppState text) : System.Void`  
- `private <ForwardDeviceAssociationCallbacks>b__137_0(Colossal.PSI.Common.IDeviceAssociationSupport support, Colossal.PSI.Common.DeviceAssociationChange change) : System.Void`  
- `private <ForwardModCallbacks>b__165_0(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status) : System.Void`  
- `private <ForwardModCallbacks>b__165_1(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod) : System.Void`  
- `private <ForwardModCallbacks>b__165_2(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod) : System.Void`  
- `private <ForwardModCallbacks>b__165_3(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod) : System.Void`  
- `private <ForwardModCallbacks>b__165_4(Colossal.PSI.Common.IModSupport support) : System.Void`  
- `private <ForwardModCallbacks>b__165_5(Colossal.PSI.Common.IModSupport support, System.Int32 mod, Colossal.PSI.Common.TransferStatus transfer) : System.Void`  
- `private <ForwardOverlayCallbacks>b__175_0(Colossal.PSI.Common.IOverlaySupport support, System.Boolean active) : System.Void`  
- `private <ForwardPlatformServiceIntegrationCallbacks>b__119_0(Colossal.PSI.Common.IPlatformServiceIntegration p) : System.Void`  
- `private <ForwardTransferCallbacks>b__204_0(Colossal.PSI.Common.ITransferSupport i, Colossal.PSI.Common.TransferStatus s) : System.Void`  
- `private <ForwardUserCallbacks>b__223_0(Colossal.PSI.Common.IUserSupport support, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  
- `private <ForwardVirtualKeyboardCallbacks>b__243_0(Colossal.PSI.Common.IVirtualKeyboardSupport p, System.String text) : System.Void`  
- `public AssociateDevice(UnityEngine.InputSystem.InputDevice device) : System.Threading.Tasks.Task<System.Boolean>`  
- `public ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  
- `public ClearRichPresence() : System.Threading.Tasks.Task`  
- `private ClearRichPresenceKeys() : System.Void`  
- `private CloudDelete(System.String path) : System.Void`  
- `private CloudLoad(System.String path, System.Byte[] value = null) : System.Boolean`  
- `private CloudStore(System.String path, System.Byte[] value = null) : System.Void`  
- `public ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config) : System.Void`  
- `public CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  
- `public Delete(System.String containerName, System.String fileName) : System.Boolean`  
- `public DisableSharing() : System.Void`  
- `public DismissVirtualKeyboard() : System.Void`  
- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public EnableSharing() : System.Void`  
- `public EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  
- `public EnumerateDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  
- `public EnumerateLocalDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  
- `public Exists(System.String containerName, System.String fileName) : System.Boolean`  
- `private ForwardAchievementCallbacks(Colossal.PSI.Common.IAchievementsSupport psi) : System.Void`  
- `private ForwardAppStateCallbacks(Colossal.PSI.Common.IAppStateSupport psi) : System.Void`  
- `private ForwardDeviceAssociationCallbacks(Colossal.PSI.Common.IDeviceAssociationSupport psi) : System.Void`  
- `private ForwardModCallbacks(Colossal.PSI.Common.IModSupport psi) : System.Void`  
- `private ForwardOverlayCallbacks(Colossal.PSI.Common.IOverlaySupport psi) : System.Void`  
- `private ForwardPlatformServiceIntegrationCallbacks(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `private ForwardTransferCallbacks(Colossal.PSI.Common.ITransferSupport psi) : System.Void`  
- `private ForwardUserCallbacks(Colossal.PSI.Common.IUserSupport psi) : System.Void`  
- `private ForwardVirtualKeyboardCallbacks(Colossal.PSI.Common.IVirtualKeyboardSupport psi) : System.Void`  
- `private FsDelete(System.String path) : System.Void`  
- `private FsLoad(System.String path, System.Byte[] value = null) : System.Boolean`  
- `private FsStore(System.String path, System.Byte[] value = null) : System.Void`  
- `public GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  
- `public GetAvatar(Colossal.PSI.Common.AvatarSize size) : System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>>`  
- `public GetDlcId(System.String name) : Colossal.PSI.Common.DlcId`  
- `public GetDlcName(Colossal.PSI.Common.DlcId dlc) : System.String`  
- `public GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  
- `private GetLocalPath(System.String key, System.String& hashKey) : System.Boolean`  
- `public GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available) : System.Void`  
- `public GetPSI<T>(System.String psiName) : T`  
- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  
- `public GetTelemetryConsentChoice() : System.Boolean`  
- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public IsAnyCloudSupported() : System.Boolean`  
- `public IsCloudSupported() : System.Boolean`  
- `public IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  
- `public IsDlcOwned(Colossal.PSI.Common.IDlc dlc) : System.Boolean`  
- `public IsDlcOwned(Colossal.PSI.Common.DlcId dlc) : System.Boolean`  
- `public IsPrincipalDeviceAssociationIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Boolean`  
- `public IsPrincipalOverlayIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Boolean`  
- `public IsPrincipalUserIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Boolean`  
- `public IsTelemetryConsentPresentable() : System.Boolean`  
- `public LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public ListMods() : System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>>`  
- `public LogVersion(System.Text.StringBuilder b) : System.Void`  
- `private OnInternetConnectionStatusChanged(System.Boolean connected) : System.Void`  
- `public Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  
- `public Read(System.String containerName, System.String fileName, System.Byte[]& data) : System.Int32`  
- `private RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, T& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> target, Colossal.PSI.Common.IAchievementsSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> target, Colossal.PSI.Common.IVirtualKeyboardSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> target, Colossal.PSI.Common.IUserSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> target, Colossal.PSI.Common.IOverlaySupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> target, Colossal.PSI.Common.IDeviceAssociationSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> target, Colossal.PSI.Common.IRemoteStorageSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> target, Colossal.PSI.Common.IAppStateSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> target, Colossal.PSI.Common.IScreenCaptureSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public RegisterPSI<T>(System.Func<T> psiConstructor, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public RegisterRichPresenceKey(System.String key, System.Func<System.String> text) : System.Void`  
- `public ResetAchievements() : System.Void`  
- `public SendTelemetry<T>(System.String eventName, T payload) : System.Void`  
- `public SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  
- `public SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset = 0, System.Int32 verticalInset = 0) : System.Void`  
- `public SetRichPresence(System.String key) : System.Void`  
- `public SetTelemetryConsentChoice(System.Boolean allowed) : System.Threading.Tasks.Task<System.Boolean>`  
- `public ShowOverlay(Colossal.PSI.Common.Page page, System.String extra = null) : System.Void`  
- `public ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 charMax, System.String previous) : System.Boolean`  
- `public SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback) : System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags>`  
- `public SignOut() : System.Threading.Tasks.Task`  
- `public SignOutFromPlatforms() : System.Threading.Tasks.Task`  
- `public SyncTelemetryConsentChoice() : System.Void`  
- `public TakeScreenshot() : System.String`  
- `public ToggleScreenshotDisabled(System.Int32 millisecondsDelay) : System.Threading.Tasks.Task`  
- `public UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  
- `public Update() : System.Void`  
- `public UserDataDelete(System.String key) : System.Void`  
- `public UserDataLoad(System.String key, System.Byte[] value = null) : System.Boolean`  
- `public UserDataStore(System.String key, System.Byte[] value = null) : System.Void`  
- `public WaitForAchievements() : System.Threading.Tasks.Task`  
- `public Wipe() : System.Void`  
- `public Write(System.String containerName, System.String fileName, System.Byte[] data) : System.Boolean`  

## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  
- `onAppStateChanged` : `Colossal.PSI.Common.OnAppStateChanged`  
- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  
- `onPlatformRegistered` : `Colossal.PSI.Common.PlatformRegisteredHandler`  
- `onConnectivityStatusChanged` : `Colossal.PSI.Common.OnConnectivityStatusChanged`  
- `onDeviceAssociationChanged` : `Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler`  
- `onModSubscriptionChanged` : `Colossal.PSI.Common.ModSubscriptionEventHandler`  
- `onModDownloadStarted` : `Colossal.PSI.Common.ModEventHandler`  
- `onModDownloadCompleted` : `Colossal.PSI.Common.ModEventHandler`  
- `onModDownloadFailed` : `Colossal.PSI.Common.ModEventHandler`  
- `onModSyncCompleted` : `Colossal.PSI.Common.ModSyncEventHandler`  
- `onModInstallProgress` : `Colossal.PSI.Common.ModInstallProgressEventHandler`  
- `onOverlayStateChanged` : `Colossal.PSI.Common.OnOverlayStateChanged`  
- `onTransferOnGoing` : `Colossal.PSI.Common.TransferEventHandler`  
- `onUserUpdated` : `Colossal.PSI.Common.OnUserUpdatedEventHandler`  
- `onInputDismissed` : `Colossal.PSI.Common.InputDismissedEventHandler`  

## Nested types

- `Colossal.PSI.Common.PlatformManager+<>c`  
- `Colossal.PSI.Common.PlatformManager+<>c__DisplayClass103_0<T>`  
- `Colossal.PSI.Common.PlatformManager+<>c__DisplayClass118_0<T>`  
- `Colossal.PSI.Common.PlatformManager+<>c__DisplayClass121_0`  
- `Colossal.PSI.Common.PlatformManager+<>c__DisplayClass123_0`  
- `Colossal.PSI.Common.PlatformManager+<>c__DisplayClass124_0`  
- `Colossal.PSI.Common.PlatformManager+<>c__DisplayClass128_0`  
- `Colossal.PSI.Common.PlatformManager+<ClearRichPresence>d__191`  
- `Colossal.PSI.Common.PlatformManager+<Dispose>d__128`  
- `Colossal.PSI.Common.PlatformManager+<Initialize>d__121`  
- `Colossal.PSI.Common.PlatformManager+<RegisterPSI>d__118<T>`  
- `Colossal.PSI.Common.PlatformManager+<SetTelemetryConsentChoice>d__199`  
- `Colossal.PSI.Common.PlatformManager+<SignOut>d__130`  
- `Colossal.PSI.Common.PlatformManager+<SignOutFromPlatforms>d__129`  
- `Colossal.PSI.Common.PlatformManager+<ToggleScreenshotDisabled>d__195`  


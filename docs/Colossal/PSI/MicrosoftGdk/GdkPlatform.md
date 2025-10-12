# Colossal.PSI.MicrosoftGdk.GdkPlatform

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`, `Colossal.PSI.Common.IPlatformSupport`, `Colossal.PSI.Common.IDlcSupport`, `Colossal.PSI.Common.IOverlaySupport`, `Colossal.PSI.Common.IRemoteStorageSupport`, `Colossal.PSI.Common.IRichPresenceSupport`, `Colossal.PSI.Common.IUserSupport`, `Colossal.PSI.Common.IVirtualKeyboardSupport`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement> m_AchievementsMap`  
- `private readonly Colossal.PSI.Common.RateLimitedInvoke m_AchievementLimiter`  
- `private System.Threading.SemaphoreSlim m_AchievementSemaphore`  
- `private System.Threading.Tasks.Task m_AchievementInitialization`  
- `private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated`  
- `private System.Boolean m_IsInitialized`  
- `private System.UInt32 m_TitleId`  
- `private System.String m_Scid`  
- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.PSI.MicrosoftGdk.PackageInfo> m_InstalledContentPackageInfos`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.MicrosoftGdk.GdkDlc> m_DlcMap`  
- `private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged`  
- `private Unity.XGamingRuntime.XGameSaveProviderHandle m_GameSaveProviderHandle`  
- `private System.Boolean m_SyncOnDemand`  
- `private readonly Colossal.PSI.Common.RateLimitedInvoke m_RichPresenceLimiter`  
- `private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated`  
- `private Unity.XGamingRuntime.XUserChangeRegistrationToken m_UserCallbackRegistrationToken`  
- `private System.Boolean m_ChangingUser`  
- `private Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData m_ActiveUserData`  
- `private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed`  
- `private static readonly System.Byte[] kZeroStat`  
- `private static Colossal.Logging.ILog log`  
- `private static System.Collections.Generic.Dictionary<System.UInt32, System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String>> ErrorCodeToMessageIDAndText`  
- `private static const System.String kStatsContainerName`  

## Properties

- `public System.String name { get }`  
- `public System.Boolean isInitialized { get }`  
- `public System.Int32 dlcCount { get }`  
- `public System.Boolean isOverlaySupported { get }`  
- `public System.Boolean isExternallyControlled { get }`  
- `public System.Boolean requiresEngagement { get }`  
- `public System.Boolean isUserSignedIn { get }`  
- `public System.String userName { get }`  
- `public System.Boolean supportsUserSwitching { get }`  
- `public System.Boolean supportsUserSection { get }`  
- `public System.String userSpecificPath { get }`  
- `public System.Boolean hasUgcPrivilege { get }`  
- `public System.Boolean passThroughVKeyboard { get }`  

## Constructors

- `public GdkPlatform(System.String scid)`  

## Methods

- `private <RemapAchievements>b__23_0(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.AchievementAttribute attribute, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData metadata) : System.Void`  
- `private <RemapDLCs>g__RemapAttribute|60_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String storeId) : System.Void`  
- `private <ShowOverlay>b__82_0(System.Int32 hresult) : System.Void`  
- `private AcquireLicense(Colossal.PSI.MicrosoftGdk.GdkDlc dlc) : System.Threading.Tasks.Task`  
- `private AcquireLicenses() : System.Threading.Tasks.Task`  
- `public ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  
- `public ClearRichPresence() : System.Threading.Tasks.Task`  
- `public ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config) : System.Void`  
- `public CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  
- `public Delete(System.String containerName, System.String blobName) : System.Boolean`  
- `public DisableSharing() : System.Void`  
- `public DismissVirtualKeyboard() : System.Void`  
- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private DisposeDlcLicenses() : System.Void`  
- `private DisposeRemoteStorage() : System.Threading.Tasks.Task`  
- `private DisposeUser() : System.Void`  
- `public EnableSharing() : System.Void`  
- `public EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  
- `public EnumerateDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  
- `public Exists(System.String containerName, System.String blobName) : System.Boolean`  
- `public Exists(System.String containerName, System.String blobName, System.DateTime& lastModified) : System.Boolean`  
- `public GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  
- `public GetAchievementFromXboxLive(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.String achievementId) : System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievement>`  
- `private GetAchievements(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData) : System.Threading.Tasks.Task<System.Collections.Generic.List<Unity.XGamingRuntime.XblAchievement>>`  
- `private GetAchievementsFromPage(Unity.XGamingRuntime.XblAchievementsResultHandle handle, System.Int32 page) : Unity.XGamingRuntime.XblAchievement[]`  
- `private GetAchievementsFromXboxLive() : System.Threading.Tasks.Task`  
- `public GetAvatar(Colossal.PSI.Common.AvatarSize size) : System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>>`  
- `public GetData(System.Collections.Generic.IEnumerable<System.String> containerPrefixes, System.Collections.Generic.IEnumerable<System.String> blobPrefixes) : System.ValueTuple<System.Collections.Generic.IReadOnlyList<Colossal.PSI.MicrosoftGdk.GdkPlatform+Container>, System.Int32>`  
- `public GetDlcName(Colossal.PSI.Common.DlcId dlcId) : System.String`  
- `public GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  
- `private static GetErrorCodeAndMessage(System.Int32 hresult) : System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String>`  
- `private GetNextPage(Unity.XGamingRuntime.XblAchievementsResultHandle previous) : System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievementsResultHandle>`  
- `public GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available) : System.Void`  
- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  
- `public GetQuotaAsync() : System.Threading.Tasks.Task<System.ValueTuple<System.Int64, System.Int64>>`  
- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  
- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public InitializeAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private InitializeRemoteStorage() : System.Threading.Tasks.Task<System.Boolean>`  
- `private InitializeStats() : System.Threading.Tasks.Task`  
- `private InputTypeToXGameUiTextEntryInputScope(Colossal.PSI.Common.InputType inputType) : Unity.XGamingRuntime.XGameUiTextEntryInputScope`  
- `public IsCloudSupported() : System.Boolean`  
- `private IsCurrentActiveUser(Unity.XGamingRuntime.XUserHandle userHandle) : System.Boolean`  
- `public IsDlcOwned(Colossal.PSI.Common.DlcId dlcId) : System.Boolean`  
- `private static IsWarning(Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID id, System.Boolean& passAsSuccess) : System.Boolean`  
- `public LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.Collections.Generic.IEnumerable<System.String> blobPrefixes) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo>`  
- `private ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo>`  
- `private ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String blobPrefix) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo>`  
- `private ListContainers(System.Collections.Generic.IEnumerable<System.String> containerPrefixes) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo>`  
- `private ListContainers() : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo>`  
- `private ListContainers(System.String containerPrefix) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo>`  
- `public LogDlcStatus() : System.Void`  
- `public LogUserData(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData) : System.Void`  
- `public LogVersion(System.Text.StringBuilder b) : System.Void`  
- `private MountDlcs() : System.Threading.Tasks.Task`  
- `private PopulateUserDataFromHandle(Unity.XGamingRuntime.XUserHandle handle, Unity.XGamingRuntime.XUserPrivilege requestedPrivilege) : System.Boolean`  
- `private ProcessLicense(Unity.XGamingRuntime.XStoreLicense license, Colossal.PSI.MicrosoftGdk.GdkDlc dlc) : System.Void`  
- `private QueryStoreProductsAsync(System.String[] storeIds, Unity.XGamingRuntime.XStoreProductKind productKind, System.String[] filters = null) : System.Threading.Tasks.Task<Unity.XGamingRuntime.XStoreProduct[]>`  
- `private QueryUpdates() : System.Threading.Tasks.Task<System.Object>`  
- `public Read(System.String containerName, System.String blobName, System.Byte[]& data) : System.Int32`  
- `private ReadAchievementsProgress(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement[] ids) : System.Threading.Tasks.Task<System.Int32[]>`  
- `private ReadBlobs<T>(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String[] blobNames) : System.Threading.Tasks.Task<T[]>`  
- `private ReadImage(System.Byte[] buffer, System.Int32 width, System.Int32 height) : System.Byte[]`  
- `private ReadStats(System.String[] blobNames) : System.Threading.Tasks.Task<System.Int32[]>`  
- `private RemapAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements) : System.Boolean`  
- `private RemapDLCs() : System.Boolean`  
- `public ResetAchievements() : System.Void`  
- `private ResetAchievementsAsync() : System.Void`  
- `private ResolveSignInIssuesWithUi(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.Action<System.Int32> callback) : System.Void`  
- `public SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  
- `public SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset = 0, System.Int32 verticalInset = 0) : System.Void`  
- `public SetRichPresence(System.String key) : System.Void`  
- `public ShowErrorDialog(System.UInt32 hresult) : System.Threading.Tasks.Task<System.Boolean>`  
- `public ShowErrorDialog(System.Int32 hresult) : System.Threading.Tasks.Task<System.Boolean>`  
- `public ShowOverlay(Colossal.PSI.Common.Page page, System.String extra = null) : System.Void`  
- `public ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous) : System.Boolean`  
- `public SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback) : System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags>`  
- `public SignOut() : System.Threading.Tasks.Task`  
- `private static Succeeded(System.Int32 hresult, System.String operationFriendlyName, Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID[] suppressMessages = null) : System.Boolean`  
- `private TryResolvePrivilege(Unity.XGamingRuntime.XUserPrivilege privilege) : System.Threading.Tasks.Task<System.Boolean>`  
- `public UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId) : System.Void`  
- `private UnlockAchievementAsync(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement) : System.Threading.Tasks.Task`  
- `private UnmountDlcs() : System.Void`  
- `public Update() : System.Void`  
- `public UpdateAchievementAsync(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Threading.Tasks.Task`  
- `private UpdateRichPresence(System.String key) : System.Void`  
- `protected UserChangeEventCallback(System.IntPtr context, Unity.XGamingRuntime.XUserLocalId userLocalId, Unity.XGamingRuntime.XUserChangeEvent eventType) : System.Void`  
- `public Wipe() : System.Void`  
- `private WipeStats() : System.Void`  
- `public Write(System.String containerName, System.String blobName, System.Byte[] data) : System.Boolean`  
- `private WriteStat(System.ValueTuple<System.String, System.Byte[]> stat) : System.Threading.Tasks.Task<System.Boolean>`  
- `private WriteStats(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Byte[]>> stats) : System.Threading.Tasks.Task<System.Boolean>`  
- `public XblCleanupAsync() : System.Threading.Tasks.Task<System.Boolean>`  

## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  
- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  
- `onOverlayStateChanged` : `Colossal.PSI.Common.OnOverlayStateChanged`  
- `onUserUpdated` : `Colossal.PSI.Common.OnUserUpdatedEventHandler`  
- `onInputDismissed` : `Colossal.PSI.Common.InputDismissedEventHandler`  

## Nested types

- `Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+Container`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass104_0<T>`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass105_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass106_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass109_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass114_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass114_1`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass115_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass115_1`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass138_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass140_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass140_1`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass141_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass147_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass14_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass154_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass15_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass22_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass24_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass24_1`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass24_2`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass26_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass28_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass46_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass59_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass62_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass62_1`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass62_2`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass62_3`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass63_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass67_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass75_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass89_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass90_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<>c__DisplayClass95_0`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<AcquireLicenses>d__61`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<ClearRichPresence>d__115`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<Dispose>d__47`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<GetAchievementFromXboxLive>d__15`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<GetAchievements>d__26`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<GetAchievementsFromXboxLive>d__24`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<GetNextPage>d__28`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<Initialize>d__44`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<InitializeAchievements>d__17`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<InitializeStats>d__16`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<LateInitialize>d__18`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<ReadAchievementsProgress>d__25`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<ReadStats>d__107`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<ResetAchievementsAsync>d__20`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<SignOut>d__143`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<UnlockAchievementAsync>d__22`  
- `Colossal.PSI.MicrosoftGdk.GdkPlatform+<UpdateAchievementAsync>d__14`  


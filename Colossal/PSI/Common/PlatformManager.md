# Colossal.PSI.Common.PlatformManager

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`, `Colossal.PSI.Common.IAppStateSupport`, `Colossal.PSI.Common.IPlatformSupport`, `Colossal.PSI.Common.IDeviceAssociationSupport`, `Colossal.PSI.Common.IDlcSupport`, `Colossal.PSI.Common.IModSupport`, `Colossal.PSI.Common.IModsUploadSupport`, `Colossal.PSI.Common.IOverlaySupport`, `Colossal.PSI.Common.IRemoteStorageSupport`, `Colossal.PSI.Common.IRichPresenceSupport`, `Colossal.PSI.Common.IScreenCaptureSupport`, `Colossal.PSI.Common.ITelemetrySupport`, `Colossal.PSI.Common.ITransferSupport`, `Colossal.PSI.Common.IUserSupport`, `Colossal.PSI.Common.IVirtualKeyboardSupport`  

## Code

```csharp
public class PlatformManager : Colossal.PSI.Common.IAchievementsSupport, Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync, Colossal.PSI.Common.IAppStateSupport, Colossal.PSI.Common.IPlatformSupport, Colossal.PSI.Common.IDeviceAssociationSupport, Colossal.PSI.Common.IDlcSupport, Colossal.PSI.Common.IModSupport, Colossal.PSI.Common.IModsUploadSupport, Colossal.PSI.Common.IOverlaySupport, Colossal.PSI.Common.IRemoteStorageSupport, Colossal.PSI.Common.IRichPresenceSupport, Colossal.PSI.Common.IScreenCaptureSupport, Colossal.PSI.Common.ITelemetrySupport, Colossal.PSI.Common.ITransferSupport, Colossal.PSI.Common.IUserSupport, Colossal.PSI.Common.IVirtualKeyboardSupport
{
    private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
    private System.Boolean m_AchievementsEnabled;
    private System.Threading.Tasks.Task m_InitializeAchievements;
    private Colossal.PSI.Common.OnAppStateChanged onAppStateChanged;
    private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
    private Colossal.PSI.Common.PlatformRegisteredHandler onPlatformRegistered;
    private Colossal.PSI.Common.OnConnectivityStatusChanged onConnectivityStatusChanged;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformServiceIntegration> m_PSIs;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformSupport> m_PlatformManagers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> m_RemoteStorages;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> m_UserBackends;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> m_ModsBackends;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITelemetrySupport> m_TelemetryBackends;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> m_AchievementsBackends;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRichPresenceSupport> m_RichPresenceHandlers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> m_VirtualKeyboardHandlers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> m_OverlayHandlers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> m_TransferManagers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> m_DeviceAssociationHandlers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDlcSupport> m_DlcBackends;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> m_AppStateHandlers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> m_ScreenCaptureHandlers;
    private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModsUploadSupport> m_ModsUploadHandlers;
    private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue;
    private Colossal.PSI.Common.IPlatformSupport m_PrincipalPlatform;
    private Colossal.PSI.Common.IUserSupport m_PrincipalUserBackend;
    private Colossal.PSI.Common.IAchievementsSupport m_PrincipalAchievementsBackend;
    private Colossal.PSI.Common.IVirtualKeyboardSupport m_PrincipalVirtualKeyboardHandler;
    private Colossal.PSI.Common.IOverlaySupport m_PrincipalOverlayHandler;
    private Colossal.PSI.Common.IDeviceAssociationSupport m_PrincipalDeviceAssociationHandler;
    private Colossal.PSI.Common.IRemoteStorageSupport m_PrincipalRemoteStorage;
    private Colossal.PSI.Common.IAppStateSupport m_PrincipalAppStateHandler;
    private Colossal.PSI.Common.IScreenCaptureSupport m_PrincipalScreenCaptureHandler;
    private Colossal.PSI.Common.IModsUploadSupport m_PrincipalModsUploadHandler;
    private Colossal.PSI.Common.ITelemetrySupport m_PrincipalTelemetryHandler;
    private System.Boolean m_IsInitialized;
    private Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler onDeviceAssociationChanged;
    private Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged;
    private Colossal.PSI.Common.ModEventHandler onModDownloadStarted;
    private Colossal.PSI.Common.ModEventHandler onModDownloadCompleted;
    private Colossal.PSI.Common.ModEventHandler onModDownloadFailed;
    private Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted;
    private Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress;
    private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Func<System.String>> m_Keys;
    private System.Boolean allowScreenshot;
    private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
    private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated;
    private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed;
    private static Colossal.Logging.ILog log;
    private static Colossal.PSI.Common.PlatformManager s_Instance;
    private static readonly System.Byte[] kEmpty;
    private static const System.String kUserData;

    public System.Boolean achievementsEnabled { get; set; }
    public static Colossal.PSI.Common.PlatformManager instance { get; }
    public System.String name { get; }
    public System.Boolean isInitialized { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformSupport> platformManagers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRemoteStorageSupport> remoteStorages { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IUserSupport> userBackends { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IModSupport> modsBackends { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITelemetrySupport> telemetryBackends { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAchievementsSupport> achievementsBackends { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRichPresenceSupport> richPresenceHandlers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IVirtualKeyboardSupport> virtualKeyboardHandlers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IOverlaySupport> overlayHandlers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITransferSupport> transferManagers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDeviceAssociationSupport> deviceAssociationHandlers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDlcSupport> dlcBackends { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAppStateSupport> appStateHandlers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IScreenCaptureSupport> screenCaptureHandlers { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformServiceIntegration> platformServiceIntegrations { get; }
    public System.String principalPlatformName { get; }
    public System.Boolean hasConnectivity { get; }
    public System.Int32 dlcCount { get; }
    public System.Boolean isOverlaySupported { get; }
    public System.Boolean isExternallyControlled { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Func<System.String>> richPresenceKeys { get; }
    public System.Boolean requiresEngagement { get; }
    public System.Boolean isUserSignedIn { get; }
    public System.String userName { get; }
    public System.Boolean supportsUserSwitching { get; }
    public System.Boolean supportsUserSection { get; }
    public System.String userSpecificPath { get; }
    public System.Boolean hasUgcPrivilege { get; }
    public System.Boolean passThroughVKeyboard { get; }

    private PlatformManager();

    private System.Void <ForwardAchievementCallbacks>b__8_0(Colossal.PSI.Common.IAchievementsSupport p, Colossal.PSI.Common.AchievementId achievementId);
    private System.Void <ForwardAppStateCallbacks>b__20_0(Colossal.PSI.Common.IPlatformServiceIntegration p, Colossal.PSI.Common.AppState text);
    private System.Void <ForwardDeviceAssociationCallbacks>b__137_0(Colossal.PSI.Common.IDeviceAssociationSupport support, Colossal.PSI.Common.DeviceAssociationChange change);
    private System.Void <ForwardModCallbacks>b__165_0(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status);
    private System.Void <ForwardModCallbacks>b__165_1(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod);
    private System.Void <ForwardModCallbacks>b__165_2(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod);
    private System.Void <ForwardModCallbacks>b__165_3(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod);
    private System.Void <ForwardModCallbacks>b__165_4(Colossal.PSI.Common.IModSupport support);
    private System.Void <ForwardModCallbacks>b__165_5(Colossal.PSI.Common.IModSupport support, System.Int32 mod, Colossal.PSI.Common.TransferStatus transfer);
    private System.Void <ForwardOverlayCallbacks>b__175_0(Colossal.PSI.Common.IOverlaySupport support, System.Boolean active);
    private System.Void <ForwardPlatformServiceIntegrationCallbacks>b__119_0(Colossal.PSI.Common.IPlatformServiceIntegration p);
    private System.Void <ForwardTransferCallbacks>b__204_0(Colossal.PSI.Common.ITransferSupport i, Colossal.PSI.Common.TransferStatus s);
    private System.Void <ForwardUserCallbacks>b__223_0(Colossal.PSI.Common.IUserSupport support, Colossal.PSI.Common.UserChangedFlags flags);
    private System.Void <ForwardVirtualKeyboardCallbacks>b__243_0(Colossal.PSI.Common.IVirtualKeyboardSupport p, System.String text);
    public System.Threading.Tasks.Task<System.Boolean> AssociateDevice(UnityEngine.InputSystem.InputDevice device);
    public System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
    public System.Threading.Tasks.Task ClearRichPresence();
    private System.Void ClearRichPresenceKeys();
    private System.Void CloudDelete(System.String path);
    private System.Boolean CloudLoad(System.String path, System.Byte[] value);
    private System.Void CloudStore(System.String path, System.Byte[] value);
    public System.Void ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config);
    public System.Int32 CountAchievements(System.Boolean onlyAchieved);
    public System.Boolean Delete(System.String containerName, System.String fileName);
    public System.Void DisableSharing();
    public System.Void DismissVirtualKeyboard();
    public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
    public System.Void EnableSharing();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateLocalDLCs();
    public System.Boolean Exists(System.String containerName, System.String fileName);
    private System.Void ForwardAchievementCallbacks(Colossal.PSI.Common.IAchievementsSupport psi);
    private System.Void ForwardAppStateCallbacks(Colossal.PSI.Common.IAppStateSupport psi);
    private System.Void ForwardDeviceAssociationCallbacks(Colossal.PSI.Common.IDeviceAssociationSupport psi);
    private System.Void ForwardModCallbacks(Colossal.PSI.Common.IModSupport psi);
    private System.Void ForwardOverlayCallbacks(Colossal.PSI.Common.IOverlaySupport psi);
    private System.Void ForwardPlatformServiceIntegrationCallbacks(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Void ForwardTransferCallbacks(Colossal.PSI.Common.ITransferSupport psi);
    private System.Void ForwardUserCallbacks(Colossal.PSI.Common.IUserSupport psi);
    private System.Void ForwardVirtualKeyboardCallbacks(Colossal.PSI.Common.IVirtualKeyboardSupport psi);
    private System.Void FsDelete(System.String path);
    private System.Boolean FsLoad(System.String path, System.Byte[] value);
    private System.Void FsStore(System.String path, System.Byte[] value);
    public System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
    public System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>> GetAvatar(Colossal.PSI.Common.AvatarSize size);
    public Colossal.PSI.Common.DlcId GetDlcId(System.String name);
    public System.String GetDlcName(Colossal.PSI.Common.DlcId dlc);
    public System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
    private System.Boolean GetLocalPath(System.String key, System.String& hashKey);
    public System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
    public T GetPSI<T>(System.String psiName);
    public System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public System.Boolean GetTelemetryConsentChoice();
    public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
    public System.Boolean IsAnyCloudSupported();
    public System.Boolean IsCloudSupported();
    public System.Boolean IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device);
    public System.Boolean IsDlcOwned(Colossal.PSI.Common.IDlc dlc);
    public System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlc);
    public System.Boolean IsPrincipalDeviceAssociationIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    public System.Boolean IsPrincipalOverlayIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    public System.Boolean IsPrincipalUserIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    public System.Boolean IsTelemetryConsentPresentable();
    public System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListMods();
    public System.Void LogVersion(System.Text.StringBuilder b);
    private System.Void OnInternetConnectionStatusChanged(System.Boolean connected);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Int32 Read(System.String containerName, System.String fileName, System.Byte[]& data);
    private System.Threading.Tasks.Task RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, T& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> target, Colossal.PSI.Common.IAchievementsSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> target, Colossal.PSI.Common.IVirtualKeyboardSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> target, Colossal.PSI.Common.IUserSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> target, Colossal.PSI.Common.IOverlaySupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> target, Colossal.PSI.Common.IDeviceAssociationSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> target, Colossal.PSI.Common.IRemoteStorageSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> target, Colossal.PSI.Common.IAppStateSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> target, Colossal.PSI.Common.IScreenCaptureSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task RegisterPSI<T>(System.Func<T> psiConstructor, System.Threading.CancellationToken token);
    public System.Void RegisterRichPresenceKey(System.String key, System.Func<System.String> text);
    public System.Void ResetAchievements();
    public System.Void SendTelemetry<T>(System.String eventName, T payload);
    public System.Void SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
    public System.Void SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset, System.Int32 verticalInset);
    public System.Void SetRichPresence(System.String key);
    public System.Threading.Tasks.Task<System.Boolean> SetTelemetryConsentChoice(System.Boolean allowed);
    public System.Void ShowOverlay(Colossal.PSI.Common.Page page, System.String extra);
    public System.Boolean ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 charMax, System.String previous);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags> SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback);
    public System.Threading.Tasks.Task SignOut();
    public System.Threading.Tasks.Task SignOutFromPlatforms();
    public System.Void SyncTelemetryConsentChoice();
    public System.String TakeScreenshot();
    public System.Threading.Tasks.Task ToggleScreenshotDisabled(System.Int32 millisecondsDelay);
    public System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID);
    public System.Void Update();
    public System.Void UserDataDelete(System.String key);
    public System.Boolean UserDataLoad(System.String key, System.Byte[] value);
    public System.Void UserDataStore(System.String key, System.Byte[] value);
    public System.Threading.Tasks.Task WaitForAchievements();
    public System.Void Wipe();
    public System.Boolean Write(System.String containerName, System.String fileName, System.Byte[] data);
}
```


## Fields

- `private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated`  

```csharp
private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```

- `private System.Boolean m_AchievementsEnabled`  

```csharp
private System.Boolean m_AchievementsEnabled;
```

- `private System.Threading.Tasks.Task m_InitializeAchievements`  

```csharp
private System.Threading.Tasks.Task m_InitializeAchievements;
```

- `private Colossal.PSI.Common.OnAppStateChanged onAppStateChanged`  

```csharp
private Colossal.PSI.Common.OnAppStateChanged onAppStateChanged;
```

- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  

```csharp
private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `private Colossal.PSI.Common.PlatformRegisteredHandler onPlatformRegistered`  

```csharp
private Colossal.PSI.Common.PlatformRegisteredHandler onPlatformRegistered;
```

- `private Colossal.PSI.Common.OnConnectivityStatusChanged onConnectivityStatusChanged`  

```csharp
private Colossal.PSI.Common.OnConnectivityStatusChanged onConnectivityStatusChanged;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformServiceIntegration> m_PSIs`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformServiceIntegration> m_PSIs;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformSupport> m_PlatformManagers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IPlatformSupport> m_PlatformManagers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> m_RemoteStorages`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> m_RemoteStorages;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> m_UserBackends`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> m_UserBackends;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> m_ModsBackends`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> m_ModsBackends;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITelemetrySupport> m_TelemetryBackends`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITelemetrySupport> m_TelemetryBackends;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> m_AchievementsBackends`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> m_AchievementsBackends;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRichPresenceSupport> m_RichPresenceHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRichPresenceSupport> m_RichPresenceHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> m_VirtualKeyboardHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> m_VirtualKeyboardHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> m_OverlayHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> m_OverlayHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> m_TransferManagers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> m_TransferManagers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> m_DeviceAssociationHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> m_DeviceAssociationHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDlcSupport> m_DlcBackends`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDlcSupport> m_DlcBackends;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> m_AppStateHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> m_AppStateHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> m_ScreenCaptureHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> m_ScreenCaptureHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModsUploadSupport> m_ModsUploadHandlers`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModsUploadSupport> m_ModsUploadHandlers;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue;
```

- `private Colossal.PSI.Common.IPlatformSupport m_PrincipalPlatform`  

```csharp
private Colossal.PSI.Common.IPlatformSupport m_PrincipalPlatform;
```

- `private Colossal.PSI.Common.IUserSupport m_PrincipalUserBackend`  

```csharp
private Colossal.PSI.Common.IUserSupport m_PrincipalUserBackend;
```

- `private Colossal.PSI.Common.IAchievementsSupport m_PrincipalAchievementsBackend`  

```csharp
private Colossal.PSI.Common.IAchievementsSupport m_PrincipalAchievementsBackend;
```

- `private Colossal.PSI.Common.IVirtualKeyboardSupport m_PrincipalVirtualKeyboardHandler`  

```csharp
private Colossal.PSI.Common.IVirtualKeyboardSupport m_PrincipalVirtualKeyboardHandler;
```

- `private Colossal.PSI.Common.IOverlaySupport m_PrincipalOverlayHandler`  

```csharp
private Colossal.PSI.Common.IOverlaySupport m_PrincipalOverlayHandler;
```

- `private Colossal.PSI.Common.IDeviceAssociationSupport m_PrincipalDeviceAssociationHandler`  

```csharp
private Colossal.PSI.Common.IDeviceAssociationSupport m_PrincipalDeviceAssociationHandler;
```

- `private Colossal.PSI.Common.IRemoteStorageSupport m_PrincipalRemoteStorage`  

```csharp
private Colossal.PSI.Common.IRemoteStorageSupport m_PrincipalRemoteStorage;
```

- `private Colossal.PSI.Common.IAppStateSupport m_PrincipalAppStateHandler`  

```csharp
private Colossal.PSI.Common.IAppStateSupport m_PrincipalAppStateHandler;
```

- `private Colossal.PSI.Common.IScreenCaptureSupport m_PrincipalScreenCaptureHandler`  

```csharp
private Colossal.PSI.Common.IScreenCaptureSupport m_PrincipalScreenCaptureHandler;
```

- `private Colossal.PSI.Common.IModsUploadSupport m_PrincipalModsUploadHandler`  

```csharp
private Colossal.PSI.Common.IModsUploadSupport m_PrincipalModsUploadHandler;
```

- `private Colossal.PSI.Common.ITelemetrySupport m_PrincipalTelemetryHandler`  

```csharp
private Colossal.PSI.Common.ITelemetrySupport m_PrincipalTelemetryHandler;
```

- `private System.Boolean m_IsInitialized`  

```csharp
private System.Boolean m_IsInitialized;
```

- `private Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler onDeviceAssociationChanged`  

```csharp
private Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler onDeviceAssociationChanged;
```

- `private Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged`  

```csharp
private Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged;
```

- `private Colossal.PSI.Common.ModEventHandler onModDownloadStarted`  

```csharp
private Colossal.PSI.Common.ModEventHandler onModDownloadStarted;
```

- `private Colossal.PSI.Common.ModEventHandler onModDownloadCompleted`  

```csharp
private Colossal.PSI.Common.ModEventHandler onModDownloadCompleted;
```

- `private Colossal.PSI.Common.ModEventHandler onModDownloadFailed`  

```csharp
private Colossal.PSI.Common.ModEventHandler onModDownloadFailed;
```

- `private Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted`  

```csharp
private Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted;
```

- `private Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress`  

```csharp
private Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress;
```

- `private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged`  

```csharp
private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Func<System.String>> m_Keys`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Func<System.String>> m_Keys;
```

- `private System.Boolean allowScreenshot`  

```csharp
private System.Boolean allowScreenshot;
```

- `private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing`  

```csharp
private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
```

- `private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated`  

```csharp
private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated;
```

- `private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed`  

```csharp
private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static Colossal.PSI.Common.PlatformManager s_Instance`  

```csharp
private static Colossal.PSI.Common.PlatformManager s_Instance;
```

- `private static readonly System.Byte[] kEmpty`  

```csharp
private static readonly System.Byte[] kEmpty;
```

- `private static const System.String kUserData`  

```csharp
private static const System.String kUserData;
```


## Properties

- `public System.Boolean achievementsEnabled { get; set }`  

```csharp
public System.Boolean achievementsEnabled { get; set; }
```

- `public static Colossal.PSI.Common.PlatformManager instance { get }`  

```csharp
public static Colossal.PSI.Common.PlatformManager instance { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformSupport> platformManagers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformSupport> platformManagers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRemoteStorageSupport> remoteStorages { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRemoteStorageSupport> remoteStorages { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IUserSupport> userBackends { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IUserSupport> userBackends { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IModSupport> modsBackends { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IModSupport> modsBackends { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITelemetrySupport> telemetryBackends { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITelemetrySupport> telemetryBackends { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAchievementsSupport> achievementsBackends { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAchievementsSupport> achievementsBackends { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRichPresenceSupport> richPresenceHandlers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IRichPresenceSupport> richPresenceHandlers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IVirtualKeyboardSupport> virtualKeyboardHandlers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IVirtualKeyboardSupport> virtualKeyboardHandlers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IOverlaySupport> overlayHandlers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IOverlaySupport> overlayHandlers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITransferSupport> transferManagers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.ITransferSupport> transferManagers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDeviceAssociationSupport> deviceAssociationHandlers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDeviceAssociationSupport> deviceAssociationHandlers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDlcSupport> dlcBackends { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IDlcSupport> dlcBackends { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAppStateSupport> appStateHandlers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IAppStateSupport> appStateHandlers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IScreenCaptureSupport> screenCaptureHandlers { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IScreenCaptureSupport> screenCaptureHandlers { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformServiceIntegration> platformServiceIntegrations { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.IPlatformServiceIntegration> platformServiceIntegrations { get; }
```

- `public System.String principalPlatformName { get }`  

```csharp
public System.String principalPlatformName { get; }
```

- `public System.Boolean hasConnectivity { get }`  

```csharp
public System.Boolean hasConnectivity { get; }
```

- `public System.Int32 dlcCount { get }`  

```csharp
public System.Int32 dlcCount { get; }
```

- `public System.Boolean isOverlaySupported { get }`  

```csharp
public System.Boolean isOverlaySupported { get; }
```

- `public System.Boolean isExternallyControlled { get }`  

```csharp
public System.Boolean isExternallyControlled { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Func<System.String>> richPresenceKeys { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Func<System.String>> richPresenceKeys { get; }
```

- `public System.Boolean requiresEngagement { get }`  

```csharp
public System.Boolean requiresEngagement { get; }
```

- `public System.Boolean isUserSignedIn { get }`  

```csharp
public System.Boolean isUserSignedIn { get; }
```

- `public System.String userName { get }`  

```csharp
public System.String userName { get; }
```

- `public System.Boolean supportsUserSwitching { get }`  

```csharp
public System.Boolean supportsUserSwitching { get; }
```

- `public System.Boolean supportsUserSection { get }`  

```csharp
public System.Boolean supportsUserSection { get; }
```

- `public System.String userSpecificPath { get }`  

```csharp
public System.String userSpecificPath { get; }
```

- `public System.Boolean hasUgcPrivilege { get }`  

```csharp
public System.Boolean hasUgcPrivilege { get; }
```

- `public System.Boolean passThroughVKeyboard { get }`  

```csharp
public System.Boolean passThroughVKeyboard { get; }
```


## Constructors

- `private PlatformManager()`  

```csharp
private PlatformManager();
```


## Methods

- `private <ForwardAchievementCallbacks>b__8_0(Colossal.PSI.Common.IAchievementsSupport p, Colossal.PSI.Common.AchievementId achievementId) : System.Void`  

```csharp
private System.Void <ForwardAchievementCallbacks>b__8_0(Colossal.PSI.Common.IAchievementsSupport p, Colossal.PSI.Common.AchievementId achievementId);
```

- `private <ForwardAppStateCallbacks>b__20_0(Colossal.PSI.Common.IPlatformServiceIntegration p, Colossal.PSI.Common.AppState text) : System.Void`  

```csharp
private System.Void <ForwardAppStateCallbacks>b__20_0(Colossal.PSI.Common.IPlatformServiceIntegration p, Colossal.PSI.Common.AppState text);
```

- `private <ForwardDeviceAssociationCallbacks>b__137_0(Colossal.PSI.Common.IDeviceAssociationSupport support, Colossal.PSI.Common.DeviceAssociationChange change) : System.Void`  

```csharp
private System.Void <ForwardDeviceAssociationCallbacks>b__137_0(Colossal.PSI.Common.IDeviceAssociationSupport support, Colossal.PSI.Common.DeviceAssociationChange change);
```

- `private <ForwardModCallbacks>b__165_0(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status) : System.Void`  

```csharp
private System.Void <ForwardModCallbacks>b__165_0(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod, Colossal.PSI.Common.ModSubscriptionStatus status);
```

- `private <ForwardModCallbacks>b__165_1(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private System.Void <ForwardModCallbacks>b__165_1(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod);
```

- `private <ForwardModCallbacks>b__165_2(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private System.Void <ForwardModCallbacks>b__165_2(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod);
```

- `private <ForwardModCallbacks>b__165_3(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod) : System.Void`  

```csharp
private System.Void <ForwardModCallbacks>b__165_3(Colossal.PSI.Common.IModSupport support, Colossal.PSI.Common.Mod mod);
```

- `private <ForwardModCallbacks>b__165_4(Colossal.PSI.Common.IModSupport support) : System.Void`  

```csharp
private System.Void <ForwardModCallbacks>b__165_4(Colossal.PSI.Common.IModSupport support);
```

- `private <ForwardModCallbacks>b__165_5(Colossal.PSI.Common.IModSupport support, System.Int32 mod, Colossal.PSI.Common.TransferStatus transfer) : System.Void`  

```csharp
private System.Void <ForwardModCallbacks>b__165_5(Colossal.PSI.Common.IModSupport support, System.Int32 mod, Colossal.PSI.Common.TransferStatus transfer);
```

- `private <ForwardOverlayCallbacks>b__175_0(Colossal.PSI.Common.IOverlaySupport support, System.Boolean active) : System.Void`  

```csharp
private System.Void <ForwardOverlayCallbacks>b__175_0(Colossal.PSI.Common.IOverlaySupport support, System.Boolean active);
```

- `private <ForwardPlatformServiceIntegrationCallbacks>b__119_0(Colossal.PSI.Common.IPlatformServiceIntegration p) : System.Void`  

```csharp
private System.Void <ForwardPlatformServiceIntegrationCallbacks>b__119_0(Colossal.PSI.Common.IPlatformServiceIntegration p);
```

- `private <ForwardTransferCallbacks>b__204_0(Colossal.PSI.Common.ITransferSupport i, Colossal.PSI.Common.TransferStatus s) : System.Void`  

```csharp
private System.Void <ForwardTransferCallbacks>b__204_0(Colossal.PSI.Common.ITransferSupport i, Colossal.PSI.Common.TransferStatus s);
```

- `private <ForwardUserCallbacks>b__223_0(Colossal.PSI.Common.IUserSupport support, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  

```csharp
private System.Void <ForwardUserCallbacks>b__223_0(Colossal.PSI.Common.IUserSupport support, Colossal.PSI.Common.UserChangedFlags flags);
```

- `private <ForwardVirtualKeyboardCallbacks>b__243_0(Colossal.PSI.Common.IVirtualKeyboardSupport p, System.String text) : System.Void`  

```csharp
private System.Void <ForwardVirtualKeyboardCallbacks>b__243_0(Colossal.PSI.Common.IVirtualKeyboardSupport p, System.String text);
```

- `public AssociateDevice(UnityEngine.InputSystem.InputDevice device) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> AssociateDevice(UnityEngine.InputSystem.InputDevice device);
```

- `public ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  

```csharp
public System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
```

- `public ClearRichPresence() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task ClearRichPresence();
```

- `private ClearRichPresenceKeys() : System.Void`  

```csharp
private System.Void ClearRichPresenceKeys();
```

- `private CloudDelete(System.String path) : System.Void`  

```csharp
private System.Void CloudDelete(System.String path);
```

- `private CloudLoad(System.String path, System.Byte[] value = null) : System.Boolean`  

```csharp
private System.Boolean CloudLoad(System.String path, System.Byte[] value);
```

- `private CloudStore(System.String path, System.Byte[] value = null) : System.Void`  

```csharp
private System.Void CloudStore(System.String path, System.Byte[] value);
```

- `public ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config) : System.Void`  

```csharp
public System.Void ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config);
```

- `public CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  

```csharp
public System.Int32 CountAchievements(System.Boolean onlyAchieved);
```

- `public Delete(System.String containerName, System.String fileName) : System.Boolean`  

```csharp
public System.Boolean Delete(System.String containerName, System.String fileName);
```

- `public DisableSharing() : System.Void`  

```csharp
public System.Void DisableSharing();
```

- `public DismissVirtualKeyboard() : System.Void`  

```csharp
public System.Void DismissVirtualKeyboard();
```

- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
```

- `public EnableSharing() : System.Void`  

```csharp
public System.Void EnableSharing();
```

- `public EnumerateAchievements() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
```

- `public EnumerateDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
```

- `public EnumerateLocalDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateLocalDLCs();
```

- `public Exists(System.String containerName, System.String fileName) : System.Boolean`  

```csharp
public System.Boolean Exists(System.String containerName, System.String fileName);
```

- `private ForwardAchievementCallbacks(Colossal.PSI.Common.IAchievementsSupport psi) : System.Void`  

```csharp
private System.Void ForwardAchievementCallbacks(Colossal.PSI.Common.IAchievementsSupport psi);
```

- `private ForwardAppStateCallbacks(Colossal.PSI.Common.IAppStateSupport psi) : System.Void`  

```csharp
private System.Void ForwardAppStateCallbacks(Colossal.PSI.Common.IAppStateSupport psi);
```

- `private ForwardDeviceAssociationCallbacks(Colossal.PSI.Common.IDeviceAssociationSupport psi) : System.Void`  

```csharp
private System.Void ForwardDeviceAssociationCallbacks(Colossal.PSI.Common.IDeviceAssociationSupport psi);
```

- `private ForwardModCallbacks(Colossal.PSI.Common.IModSupport psi) : System.Void`  

```csharp
private System.Void ForwardModCallbacks(Colossal.PSI.Common.IModSupport psi);
```

- `private ForwardOverlayCallbacks(Colossal.PSI.Common.IOverlaySupport psi) : System.Void`  

```csharp
private System.Void ForwardOverlayCallbacks(Colossal.PSI.Common.IOverlaySupport psi);
```

- `private ForwardPlatformServiceIntegrationCallbacks(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void ForwardPlatformServiceIntegrationCallbacks(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private ForwardTransferCallbacks(Colossal.PSI.Common.ITransferSupport psi) : System.Void`  

```csharp
private System.Void ForwardTransferCallbacks(Colossal.PSI.Common.ITransferSupport psi);
```

- `private ForwardUserCallbacks(Colossal.PSI.Common.IUserSupport psi) : System.Void`  

```csharp
private System.Void ForwardUserCallbacks(Colossal.PSI.Common.IUserSupport psi);
```

- `private ForwardVirtualKeyboardCallbacks(Colossal.PSI.Common.IVirtualKeyboardSupport psi) : System.Void`  

```csharp
private System.Void ForwardVirtualKeyboardCallbacks(Colossal.PSI.Common.IVirtualKeyboardSupport psi);
```

- `private FsDelete(System.String path) : System.Void`  

```csharp
private System.Void FsDelete(System.String path);
```

- `private FsLoad(System.String path, System.Byte[] value = null) : System.Boolean`  

```csharp
private System.Boolean FsLoad(System.String path, System.Byte[] value);
```

- `private FsStore(System.String path, System.Byte[] value = null) : System.Void`  

```csharp
private System.Void FsStore(System.String path, System.Byte[] value);
```

- `public GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  

```csharp
public System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
```

- `public GetAvatar(Colossal.PSI.Common.AvatarSize size) : System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>> GetAvatar(Colossal.PSI.Common.AvatarSize size);
```

- `public GetDlcId(System.String name) : Colossal.PSI.Common.DlcId`  

```csharp
public Colossal.PSI.Common.DlcId GetDlcId(System.String name);
```

- `public GetDlcName(Colossal.PSI.Common.DlcId dlc) : System.String`  

```csharp
public System.String GetDlcName(Colossal.PSI.Common.DlcId dlc);
```

- `public GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  

```csharp
public System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
```

- `private GetLocalPath(System.String key, System.String& hashKey) : System.Boolean`  

```csharp
private System.Boolean GetLocalPath(System.String key, System.String& hashKey);
```

- `public GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available) : System.Void`  

```csharp
public System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
```

- `public GetPSI<T>(System.String psiName) : T`  

```csharp
public T GetPSI<T>(System.String psiName);
```

- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  

```csharp
public System.ValueTuple<System.Int64, System.Int64> GetQuota();
```

- `public GetTelemetryConsentChoice() : System.Boolean`  

```csharp
public System.Boolean GetTelemetryConsentChoice();
```

- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
```

- `public IsAnyCloudSupported() : System.Boolean`  

```csharp
public System.Boolean IsAnyCloudSupported();
```

- `public IsCloudSupported() : System.Boolean`  

```csharp
public System.Boolean IsCloudSupported();
```

- `public IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  

```csharp
public System.Boolean IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device);
```

- `public IsDlcOwned(Colossal.PSI.Common.IDlc dlc) : System.Boolean`  

```csharp
public System.Boolean IsDlcOwned(Colossal.PSI.Common.IDlc dlc);
```

- `public IsDlcOwned(Colossal.PSI.Common.DlcId dlc) : System.Boolean`  

```csharp
public System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlc);
```

- `public IsPrincipalDeviceAssociationIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Boolean`  

```csharp
public System.Boolean IsPrincipalDeviceAssociationIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public IsPrincipalOverlayIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Boolean`  

```csharp
public System.Boolean IsPrincipalOverlayIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public IsPrincipalUserIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Boolean`  

```csharp
public System.Boolean IsPrincipalUserIntegration(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public IsTelemetryConsentPresentable() : System.Boolean`  

```csharp
public System.Boolean IsTelemetryConsentPresentable();
```

- `public LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
```

- `public ListMods() : System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListMods();
```

- `public LogVersion(System.Text.StringBuilder b) : System.Void`  

```csharp
public System.Void LogVersion(System.Text.StringBuilder b);
```

- `private OnInternetConnectionStatusChanged(System.Boolean connected) : System.Void`  

```csharp
private System.Void OnInternetConnectionStatusChanged(System.Boolean connected);
```

- `public Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public Read(System.String containerName, System.String fileName, System.Byte[]& data) : System.Int32`  

```csharp
public System.Int32 Read(System.String containerName, System.String fileName, System.Byte[]& data);
```

- `private RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, T& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI<T>(System.Collections.Concurrent.ConcurrentStack<T> target, T& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> target, Colossal.PSI.Common.IAchievementsSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAchievementsSupport> target, Colossal.PSI.Common.IAchievementsSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> target, Colossal.PSI.Common.IVirtualKeyboardSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IVirtualKeyboardSupport> target, Colossal.PSI.Common.IVirtualKeyboardSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IModSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> target, Colossal.PSI.Common.IUserSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IUserSupport> target, Colossal.PSI.Common.IUserSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> target, Colossal.PSI.Common.IOverlaySupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IOverlaySupport> target, Colossal.PSI.Common.IOverlaySupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.ITransferSupport> target, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> target, Colossal.PSI.Common.IDeviceAssociationSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IDeviceAssociationSupport> target, Colossal.PSI.Common.IDeviceAssociationSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> target, Colossal.PSI.Common.IRemoteStorageSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IRemoteStorageSupport> target, Colossal.PSI.Common.IRemoteStorageSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> target, Colossal.PSI.Common.IAppStateSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IAppStateSupport> target, Colossal.PSI.Common.IAppStateSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `private RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> target, Colossal.PSI.Common.IScreenCaptureSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task RegisterPSI(System.Collections.Concurrent.ConcurrentStack<Colossal.PSI.Common.IScreenCaptureSupport> target, Colossal.PSI.Common.IScreenCaptureSupport& principal, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `public RegisterPSI<T>(System.Func<T> psiConstructor, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task RegisterPSI<T>(System.Func<T> psiConstructor, System.Threading.CancellationToken token);
```

- `public RegisterRichPresenceKey(System.String key, System.Func<System.String> text) : System.Void`  

```csharp
public System.Void RegisterRichPresenceKey(System.String key, System.Func<System.String> text);
```

- `public ResetAchievements() : System.Void`  

```csharp
public System.Void ResetAchievements();
```

- `public SendTelemetry<T>(System.String eventName, T payload) : System.Void`  

```csharp
public System.Void SendTelemetry<T>(System.String eventName, T payload);
```

- `public SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public System.Void SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
```

- `public SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset = 0, System.Int32 verticalInset = 0) : System.Void`  

```csharp
public System.Void SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset, System.Int32 verticalInset);
```

- `public SetRichPresence(System.String key) : System.Void`  

```csharp
public System.Void SetRichPresence(System.String key);
```

- `public SetTelemetryConsentChoice(System.Boolean allowed) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> SetTelemetryConsentChoice(System.Boolean allowed);
```

- `public ShowOverlay(Colossal.PSI.Common.Page page, System.String extra = null) : System.Void`  

```csharp
public System.Void ShowOverlay(Colossal.PSI.Common.Page page, System.String extra);
```

- `public ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 charMax, System.String previous) : System.Boolean`  

```csharp
public System.Boolean ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 charMax, System.String previous);
```

- `public SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback) : System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags> SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback);
```

- `public SignOut() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SignOut();
```

- `public SignOutFromPlatforms() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SignOutFromPlatforms();
```

- `public SyncTelemetryConsentChoice() : System.Void`  

```csharp
public System.Void SyncTelemetryConsentChoice();
```

- `public TakeScreenshot() : System.String`  

```csharp
public System.String TakeScreenshot();
```

- `public ToggleScreenshotDisabled(System.Int32 millisecondsDelay) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task ToggleScreenshotDisabled(System.Int32 millisecondsDelay);
```

- `public UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  

```csharp
public System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementID);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `public UserDataDelete(System.String key) : System.Void`  

```csharp
public System.Void UserDataDelete(System.String key);
```

- `public UserDataLoad(System.String key, System.Byte[] value = null) : System.Boolean`  

```csharp
public System.Boolean UserDataLoad(System.String key, System.Byte[] value);
```

- `public UserDataStore(System.String key, System.Byte[] value = null) : System.Void`  

```csharp
public System.Void UserDataStore(System.String key, System.Byte[] value);
```

- `public WaitForAchievements() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task WaitForAchievements();
```

- `public Wipe() : System.Void`  

```csharp
public System.Void Wipe();
```

- `public Write(System.String containerName, System.String fileName, System.Byte[] data) : System.Boolean`  

```csharp
public System.Boolean Write(System.String containerName, System.String fileName, System.Byte[] data);
```


## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  

```csharp
public event Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```

- `onAppStateChanged` : `Colossal.PSI.Common.OnAppStateChanged`  

```csharp
public event Colossal.PSI.Common.OnAppStateChanged onAppStateChanged;
```

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `onPlatformRegistered` : `Colossal.PSI.Common.PlatformRegisteredHandler`  

```csharp
public event Colossal.PSI.Common.PlatformRegisteredHandler onPlatformRegistered;
```

- `onConnectivityStatusChanged` : `Colossal.PSI.Common.OnConnectivityStatusChanged`  

```csharp
public event Colossal.PSI.Common.OnConnectivityStatusChanged onConnectivityStatusChanged;
```

- `onDeviceAssociationChanged` : `Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler onDeviceAssociationChanged;
```

- `onModSubscriptionChanged` : `Colossal.PSI.Common.ModSubscriptionEventHandler`  

```csharp
public event Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged;
```

- `onModDownloadStarted` : `Colossal.PSI.Common.ModEventHandler`  

```csharp
public event Colossal.PSI.Common.ModEventHandler onModDownloadStarted;
```

- `onModDownloadCompleted` : `Colossal.PSI.Common.ModEventHandler`  

```csharp
public event Colossal.PSI.Common.ModEventHandler onModDownloadCompleted;
```

- `onModDownloadFailed` : `Colossal.PSI.Common.ModEventHandler`  

```csharp
public event Colossal.PSI.Common.ModEventHandler onModDownloadFailed;
```

- `onModSyncCompleted` : `Colossal.PSI.Common.ModSyncEventHandler`  

```csharp
public event Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted;
```

- `onModInstallProgress` : `Colossal.PSI.Common.ModInstallProgressEventHandler`  

```csharp
public event Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress;
```

- `onOverlayStateChanged` : `Colossal.PSI.Common.OnOverlayStateChanged`  

```csharp
public event Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
```

- `onTransferOnGoing` : `Colossal.PSI.Common.TransferEventHandler`  

```csharp
public event Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
```

- `onUserUpdated` : `Colossal.PSI.Common.OnUserUpdatedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated;
```

- `onInputDismissed` : `Colossal.PSI.Common.InputDismissedEventHandler`  

```csharp
public event Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed;
```


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


# Colossal.PSI.MicrosoftGdk.GdkPlatform

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`, `Colossal.PSI.Common.IPlatformSupport`, `Colossal.PSI.Common.IDlcSupport`, `Colossal.PSI.Common.IOverlaySupport`, `Colossal.PSI.Common.IRemoteStorageSupport`, `Colossal.PSI.Common.IRichPresenceSupport`, `Colossal.PSI.Common.IUserSupport`, `Colossal.PSI.Common.IVirtualKeyboardSupport`  

## Code

```csharp
public class GdkPlatform : Colossal.PSI.Common.IAchievementsSupport, Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync, Colossal.PSI.Common.IPlatformSupport, Colossal.PSI.Common.IDlcSupport, Colossal.PSI.Common.IOverlaySupport, Colossal.PSI.Common.IRemoteStorageSupport, Colossal.PSI.Common.IRichPresenceSupport, Colossal.PSI.Common.IUserSupport, Colossal.PSI.Common.IVirtualKeyboardSupport
{
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement> m_AchievementsMap;
    private readonly Colossal.PSI.Common.RateLimitedInvoke m_AchievementLimiter;
    private System.Threading.SemaphoreSlim m_AchievementSemaphore;
    private System.Threading.Tasks.Task m_AchievementInitialization;
    private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
    private System.Boolean m_IsInitialized;
    private System.UInt32 m_TitleId;
    private System.String m_Scid;
    private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.PSI.MicrosoftGdk.PackageInfo> m_InstalledContentPackageInfos;
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.MicrosoftGdk.GdkDlc> m_DlcMap;
    private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
    private Unity.XGamingRuntime.XGameSaveProviderHandle m_GameSaveProviderHandle;
    private System.Boolean m_SyncOnDemand;
    private readonly Colossal.PSI.Common.RateLimitedInvoke m_RichPresenceLimiter;
    private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated;
    private Unity.XGamingRuntime.XUserChangeRegistrationToken m_UserCallbackRegistrationToken;
    private System.Boolean m_ChangingUser;
    private Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData m_ActiveUserData;
    private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed;
    private static readonly System.Byte[] kZeroStat;
    private static Colossal.Logging.ILog log;
    private static System.Collections.Generic.Dictionary<System.UInt32, System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String>> ErrorCodeToMessageIDAndText;
    private static const System.String kStatsContainerName;

    public System.String name { get; }
    public System.Boolean isInitialized { get; }
    public System.Int32 dlcCount { get; }
    public System.Boolean isOverlaySupported { get; }
    public System.Boolean isExternallyControlled { get; }
    public System.Boolean requiresEngagement { get; }
    public System.Boolean isUserSignedIn { get; }
    public System.String userName { get; }
    public System.Boolean supportsUserSwitching { get; }
    public System.Boolean supportsUserSection { get; }
    public System.String userSpecificPath { get; }
    public System.Boolean hasUgcPrivilege { get; }
    public System.Boolean passThroughVKeyboard { get; }

    public GdkPlatform(System.String scid);

    private System.Void <RemapAchievements>b__23_0(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.AchievementAttribute attribute, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData metadata);
    private System.Void <RemapDLCs>g__RemapAttribute|60_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String storeId);
    private System.Void <ShowOverlay>b__82_0(System.Int32 hresult);
    private System.Threading.Tasks.Task AcquireLicense(Colossal.PSI.MicrosoftGdk.GdkDlc dlc);
    private System.Threading.Tasks.Task AcquireLicenses();
    public System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
    public System.Threading.Tasks.Task ClearRichPresence();
    public System.Void ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config);
    public System.Int32 CountAchievements(System.Boolean onlyAchieved);
    public System.Boolean Delete(System.String containerName, System.String blobName);
    public System.Void DisableSharing();
    public System.Void DismissVirtualKeyboard();
    public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
    private System.Void DisposeDlcLicenses();
    private System.Threading.Tasks.Task DisposeRemoteStorage();
    private System.Void DisposeUser();
    public System.Void EnableSharing();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IAchievement> EnumerateAchievements();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
    public System.Boolean Exists(System.String containerName, System.String blobName);
    public System.Boolean Exists(System.String containerName, System.String blobName, System.DateTime& lastModified);
    public System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
    public System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievement> GetAchievementFromXboxLive(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.String achievementId);
    private System.Threading.Tasks.Task<System.Collections.Generic.List<Unity.XGamingRuntime.XblAchievement>> GetAchievements(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData);
    private Unity.XGamingRuntime.XblAchievement[] GetAchievementsFromPage(Unity.XGamingRuntime.XblAchievementsResultHandle handle, System.Int32 page);
    private System.Threading.Tasks.Task GetAchievementsFromXboxLive();
    public System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>> GetAvatar(Colossal.PSI.Common.AvatarSize size);
    public System.ValueTuple<System.Collections.Generic.IReadOnlyList<Colossal.PSI.MicrosoftGdk.GdkPlatform+Container>, System.Int32> GetData(System.Collections.Generic.IEnumerable<System.String> containerPrefixes, System.Collections.Generic.IEnumerable<System.String> blobPrefixes);
    public System.String GetDlcName(Colossal.PSI.Common.DlcId dlcId);
    public System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
    private static System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String> GetErrorCodeAndMessage(System.Int32 hresult);
    private System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievementsResultHandle> GetNextPage(Unity.XGamingRuntime.XblAchievementsResultHandle previous);
    public System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
    public System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public System.Threading.Tasks.Task<System.ValueTuple<System.Int64, System.Int64>> GetQuotaAsync();
    public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task InitializeAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Boolean> InitializeRemoteStorage();
    private System.Threading.Tasks.Task InitializeStats();
    private Unity.XGamingRuntime.XGameUiTextEntryInputScope InputTypeToXGameUiTextEntryInputScope(Colossal.PSI.Common.InputType inputType);
    public System.Boolean IsCloudSupported();
    private System.Boolean IsCurrentActiveUser(Unity.XGamingRuntime.XUserHandle userHandle);
    public System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlcId);
    private static System.Boolean IsWarning(Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID id, System.Boolean& passAsSuccess);
    public System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
    private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo> ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.Collections.Generic.IEnumerable<System.String> blobPrefixes);
    private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo> ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle);
    private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo> ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String blobPrefix);
    private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo> ListContainers(System.Collections.Generic.IEnumerable<System.String> containerPrefixes);
    private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo> ListContainers();
    private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo> ListContainers(System.String containerPrefix);
    public System.Void LogDlcStatus();
    public System.Void LogUserData(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData);
    public System.Void LogVersion(System.Text.StringBuilder b);
    private System.Threading.Tasks.Task MountDlcs();
    private System.Boolean PopulateUserDataFromHandle(Unity.XGamingRuntime.XUserHandle handle, Unity.XGamingRuntime.XUserPrivilege requestedPrivilege);
    private System.Void ProcessLicense(Unity.XGamingRuntime.XStoreLicense license, Colossal.PSI.MicrosoftGdk.GdkDlc dlc);
    private System.Threading.Tasks.Task<Unity.XGamingRuntime.XStoreProduct[]> QueryStoreProductsAsync(System.String[] storeIds, Unity.XGamingRuntime.XStoreProductKind productKind, System.String[] filters);
    private System.Threading.Tasks.Task<System.Object> QueryUpdates();
    public System.Int32 Read(System.String containerName, System.String blobName, System.Byte[]& data);
    private System.Threading.Tasks.Task<System.Int32[]> ReadAchievementsProgress(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement[] ids);
    private System.Threading.Tasks.Task<T[]> ReadBlobs<T>(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String[] blobNames);
    private System.Byte[] ReadImage(System.Byte[] buffer, System.Int32 width, System.Int32 height);
    private System.Threading.Tasks.Task<System.Int32[]> ReadStats(System.String[] blobNames);
    private System.Boolean RemapAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements);
    private System.Boolean RemapDLCs();
    public System.Void ResetAchievements();
    private System.Void ResetAchievementsAsync();
    private System.Void ResolveSignInIssuesWithUi(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.Action<System.Int32> callback);
    public System.Void SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
    public System.Void SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset, System.Int32 verticalInset);
    public System.Void SetRichPresence(System.String key);
    public System.Threading.Tasks.Task<System.Boolean> ShowErrorDialog(System.UInt32 hresult);
    public System.Threading.Tasks.Task<System.Boolean> ShowErrorDialog(System.Int32 hresult);
    public System.Void ShowOverlay(Colossal.PSI.Common.Page page, System.String extra);
    public System.Boolean ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags> SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback);
    public System.Threading.Tasks.Task SignOut();
    private static System.Boolean Succeeded(System.Int32 hresult, System.String operationFriendlyName, Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID[] suppressMessages);
    private System.Threading.Tasks.Task<System.Boolean> TryResolvePrivilege(Unity.XGamingRuntime.XUserPrivilege privilege);
    public System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId);
    private System.Threading.Tasks.Task UnlockAchievementAsync(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement);
    private System.Void UnmountDlcs();
    public System.Void Update();
    public System.Threading.Tasks.Task UpdateAchievementAsync(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement, System.Int32 value, Colossal.PSI.Common.IndicateType type);
    private System.Void UpdateRichPresence(System.String key);
    protected System.Void UserChangeEventCallback(System.IntPtr context, Unity.XGamingRuntime.XUserLocalId userLocalId, Unity.XGamingRuntime.XUserChangeEvent eventType);
    public System.Void Wipe();
    private System.Void WipeStats();
    public System.Boolean Write(System.String containerName, System.String blobName, System.Byte[] data);
    private System.Threading.Tasks.Task<System.Boolean> WriteStat(System.ValueTuple<System.String, System.Byte[]> stat);
    private System.Threading.Tasks.Task<System.Boolean> WriteStats(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Byte[]>> stats);
    public System.Threading.Tasks.Task<System.Boolean> XblCleanupAsync();
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement> m_AchievementsMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement> m_AchievementsMap;
```

- `private readonly Colossal.PSI.Common.RateLimitedInvoke m_AchievementLimiter`  

```csharp
private readonly Colossal.PSI.Common.RateLimitedInvoke m_AchievementLimiter;
```

- `private System.Threading.SemaphoreSlim m_AchievementSemaphore`  

```csharp
private System.Threading.SemaphoreSlim m_AchievementSemaphore;
```

- `private System.Threading.Tasks.Task m_AchievementInitialization`  

```csharp
private System.Threading.Tasks.Task m_AchievementInitialization;
```

- `private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated`  

```csharp
private Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```

- `private System.Boolean m_IsInitialized`  

```csharp
private System.Boolean m_IsInitialized;
```

- `private System.UInt32 m_TitleId`  

```csharp
private System.UInt32 m_TitleId;
```

- `private System.String m_Scid`  

```csharp
private System.String m_Scid;
```

- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  

```csharp
private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.PSI.MicrosoftGdk.PackageInfo> m_InstalledContentPackageInfos`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.PSI.MicrosoftGdk.PackageInfo> m_InstalledContentPackageInfos;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.MicrosoftGdk.GdkDlc> m_DlcMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.MicrosoftGdk.GdkDlc> m_DlcMap;
```

- `private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged`  

```csharp
private Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
```

- `private Unity.XGamingRuntime.XGameSaveProviderHandle m_GameSaveProviderHandle`  

```csharp
private Unity.XGamingRuntime.XGameSaveProviderHandle m_GameSaveProviderHandle;
```

- `private System.Boolean m_SyncOnDemand`  

```csharp
private System.Boolean m_SyncOnDemand;
```

- `private readonly Colossal.PSI.Common.RateLimitedInvoke m_RichPresenceLimiter`  

```csharp
private readonly Colossal.PSI.Common.RateLimitedInvoke m_RichPresenceLimiter;
```

- `private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated`  

```csharp
private Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated;
```

- `private Unity.XGamingRuntime.XUserChangeRegistrationToken m_UserCallbackRegistrationToken`  

```csharp
private Unity.XGamingRuntime.XUserChangeRegistrationToken m_UserCallbackRegistrationToken;
```

- `private System.Boolean m_ChangingUser`  

```csharp
private System.Boolean m_ChangingUser;
```

- `private Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData m_ActiveUserData`  

```csharp
private Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData m_ActiveUserData;
```

- `private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed`  

```csharp
private Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed;
```

- `private static readonly System.Byte[] kZeroStat`  

```csharp
private static readonly System.Byte[] kZeroStat;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static System.Collections.Generic.Dictionary<System.UInt32, System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String>> ErrorCodeToMessageIDAndText`  

```csharp
private static System.Collections.Generic.Dictionary<System.UInt32, System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String>> ErrorCodeToMessageIDAndText;
```

- `private static const System.String kStatsContainerName`  

```csharp
private static const System.String kStatsContainerName;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
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

- `public GdkPlatform(System.String scid)`  

```csharp
public GdkPlatform(System.String scid);
```


## Methods

- `private <RemapAchievements>b__23_0(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.AchievementAttribute attribute, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData metadata) : System.Void`  

```csharp
private System.Void <RemapAchievements>b__23_0(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.AchievementAttribute attribute, Colossal.PSI.MicrosoftGdk.GdkAchievementsMetaData metadata);
```

- `private <RemapDLCs>g__RemapAttribute|60_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String storeId) : System.Void`  

```csharp
private System.Void <RemapDLCs>g__RemapAttribute|60_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String storeId);
```

- `private <ShowOverlay>b__82_0(System.Int32 hresult) : System.Void`  

```csharp
private System.Void <ShowOverlay>b__82_0(System.Int32 hresult);
```

- `private AcquireLicense(Colossal.PSI.MicrosoftGdk.GdkDlc dlc) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task AcquireLicense(Colossal.PSI.MicrosoftGdk.GdkDlc dlc);
```

- `private AcquireLicenses() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task AcquireLicenses();
```

- `public ClearAchievement(Colossal.PSI.Common.AchievementId achievementID) : System.Void`  

```csharp
public System.Void ClearAchievement(Colossal.PSI.Common.AchievementId achievementID);
```

- `public ClearRichPresence() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task ClearRichPresence();
```

- `public ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config) : System.Void`  

```csharp
public System.Void ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config);
```

- `public CountAchievements(System.Boolean onlyAchieved = False) : System.Int32`  

```csharp
public System.Int32 CountAchievements(System.Boolean onlyAchieved);
```

- `public Delete(System.String containerName, System.String blobName) : System.Boolean`  

```csharp
public System.Boolean Delete(System.String containerName, System.String blobName);
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

- `private DisposeDlcLicenses() : System.Void`  

```csharp
private System.Void DisposeDlcLicenses();
```

- `private DisposeRemoteStorage() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task DisposeRemoteStorage();
```

- `private DisposeUser() : System.Void`  

```csharp
private System.Void DisposeUser();
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

- `public Exists(System.String containerName, System.String blobName) : System.Boolean`  

```csharp
public System.Boolean Exists(System.String containerName, System.String blobName);
```

- `public Exists(System.String containerName, System.String blobName, System.DateTime& lastModified) : System.Boolean`  

```csharp
public System.Boolean Exists(System.String containerName, System.String blobName, System.DateTime& lastModified);
```

- `public GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement) : System.Boolean`  

```csharp
public System.Boolean GetAchievement(Colossal.PSI.Common.AchievementId id, Colossal.PSI.Common.IAchievement& achievement);
```

- `public GetAchievementFromXboxLive(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.String achievementId) : System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievement>`  

```csharp
public System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievement> GetAchievementFromXboxLive(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.String achievementId);
```

- `private GetAchievements(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData) : System.Threading.Tasks.Task<System.Collections.Generic.List<Unity.XGamingRuntime.XblAchievement>>`  

```csharp
private System.Threading.Tasks.Task<System.Collections.Generic.List<Unity.XGamingRuntime.XblAchievement>> GetAchievements(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData);
```

- `private GetAchievementsFromPage(Unity.XGamingRuntime.XblAchievementsResultHandle handle, System.Int32 page) : Unity.XGamingRuntime.XblAchievement[]`  

```csharp
private Unity.XGamingRuntime.XblAchievement[] GetAchievementsFromPage(Unity.XGamingRuntime.XblAchievementsResultHandle handle, System.Int32 page);
```

- `private GetAchievementsFromXboxLive() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task GetAchievementsFromXboxLive();
```

- `public GetAvatar(Colossal.PSI.Common.AvatarSize size) : System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>> GetAvatar(Colossal.PSI.Common.AvatarSize size);
```

- `public GetData(System.Collections.Generic.IEnumerable<System.String> containerPrefixes, System.Collections.Generic.IEnumerable<System.String> blobPrefixes) : System.ValueTuple<System.Collections.Generic.IReadOnlyList<Colossal.PSI.MicrosoftGdk.GdkPlatform+Container>, System.Int32>`  

```csharp
public System.ValueTuple<System.Collections.Generic.IReadOnlyList<Colossal.PSI.MicrosoftGdk.GdkPlatform+Container>, System.Int32> GetData(System.Collections.Generic.IEnumerable<System.String> containerPrefixes, System.Collections.Generic.IEnumerable<System.String> blobPrefixes);
```

- `public GetDlcName(Colossal.PSI.Common.DlcId dlcId) : System.String`  

```csharp
public System.String GetDlcName(Colossal.PSI.Common.DlcId dlcId);
```

- `public GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  

```csharp
public System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
```

- `private static GetErrorCodeAndMessage(System.Int32 hresult) : System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String>`  

```csharp
private static System.ValueTuple<Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID, System.String> GetErrorCodeAndMessage(System.Int32 hresult);
```

- `private GetNextPage(Unity.XGamingRuntime.XblAchievementsResultHandle previous) : System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievementsResultHandle>`  

```csharp
private System.Threading.Tasks.Task<Unity.XGamingRuntime.XblAchievementsResultHandle> GetNextPage(Unity.XGamingRuntime.XblAchievementsResultHandle previous);
```

- `public GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available) : System.Void`  

```csharp
public System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
```

- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  

```csharp
public System.ValueTuple<System.Int64, System.Int64> GetQuota();
```

- `public GetQuotaAsync() : System.Threading.Tasks.Task<System.ValueTuple<System.Int64, System.Int64>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.Int64, System.Int64>> GetQuotaAsync();
```

- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId achievementId, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Void`  

```csharp
public System.Void IndicateAchievementProgress(Colossal.PSI.Common.AchievementId[] achievementID, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
```

- `public InitializeAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task InitializeAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
```

- `private InitializeRemoteStorage() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> InitializeRemoteStorage();
```

- `private InitializeStats() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task InitializeStats();
```

- `private InputTypeToXGameUiTextEntryInputScope(Colossal.PSI.Common.InputType inputType) : Unity.XGamingRuntime.XGameUiTextEntryInputScope`  

```csharp
private Unity.XGamingRuntime.XGameUiTextEntryInputScope InputTypeToXGameUiTextEntryInputScope(Colossal.PSI.Common.InputType inputType);
```

- `public IsCloudSupported() : System.Boolean`  

```csharp
public System.Boolean IsCloudSupported();
```

- `private IsCurrentActiveUser(Unity.XGamingRuntime.XUserHandle userHandle) : System.Boolean`  

```csharp
private System.Boolean IsCurrentActiveUser(Unity.XGamingRuntime.XUserHandle userHandle);
```

- `public IsDlcOwned(Colossal.PSI.Common.DlcId dlcId) : System.Boolean`  

```csharp
public System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlcId);
```

- `private static IsWarning(Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID id, System.Boolean& passAsSuccess) : System.Boolean`  

```csharp
private static System.Boolean IsWarning(Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID id, System.Boolean& passAsSuccess);
```

- `public LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task LateInitialize(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements, System.Threading.CancellationToken token);
```

- `private ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.Collections.Generic.IEnumerable<System.String> blobPrefixes) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo>`  

```csharp
private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo> ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.Collections.Generic.IEnumerable<System.String> blobPrefixes);
```

- `private ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo>`  

```csharp
private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo> ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle);
```

- `private ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String blobPrefix) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo>`  

```csharp
private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveBlobInfo> ListBlobs(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String blobPrefix);
```

- `private ListContainers(System.Collections.Generic.IEnumerable<System.String> containerPrefixes) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo>`  

```csharp
private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo> ListContainers(System.Collections.Generic.IEnumerable<System.String> containerPrefixes);
```

- `private ListContainers() : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo>`  

```csharp
private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo> ListContainers();
```

- `private ListContainers(System.String containerPrefix) : System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo>`  

```csharp
private System.Collections.Generic.IReadOnlyList<Unity.XGamingRuntime.XGameSaveContainerInfo> ListContainers(System.String containerPrefix);
```

- `public LogDlcStatus() : System.Void`  

```csharp
public System.Void LogDlcStatus();
```

- `public LogUserData(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData) : System.Void`  

```csharp
public System.Void LogUserData(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData);
```

- `public LogVersion(System.Text.StringBuilder b) : System.Void`  

```csharp
public System.Void LogVersion(System.Text.StringBuilder b);
```

- `private MountDlcs() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task MountDlcs();
```

- `private PopulateUserDataFromHandle(Unity.XGamingRuntime.XUserHandle handle, Unity.XGamingRuntime.XUserPrivilege requestedPrivilege) : System.Boolean`  

```csharp
private System.Boolean PopulateUserDataFromHandle(Unity.XGamingRuntime.XUserHandle handle, Unity.XGamingRuntime.XUserPrivilege requestedPrivilege);
```

- `private ProcessLicense(Unity.XGamingRuntime.XStoreLicense license, Colossal.PSI.MicrosoftGdk.GdkDlc dlc) : System.Void`  

```csharp
private System.Void ProcessLicense(Unity.XGamingRuntime.XStoreLicense license, Colossal.PSI.MicrosoftGdk.GdkDlc dlc);
```

- `private QueryStoreProductsAsync(System.String[] storeIds, Unity.XGamingRuntime.XStoreProductKind productKind, System.String[] filters = null) : System.Threading.Tasks.Task<Unity.XGamingRuntime.XStoreProduct[]>`  

```csharp
private System.Threading.Tasks.Task<Unity.XGamingRuntime.XStoreProduct[]> QueryStoreProductsAsync(System.String[] storeIds, Unity.XGamingRuntime.XStoreProductKind productKind, System.String[] filters);
```

- `private QueryUpdates() : System.Threading.Tasks.Task<System.Object>`  

```csharp
private System.Threading.Tasks.Task<System.Object> QueryUpdates();
```

- `public Read(System.String containerName, System.String blobName, System.Byte[]& data) : System.Int32`  

```csharp
public System.Int32 Read(System.String containerName, System.String blobName, System.Byte[]& data);
```

- `private ReadAchievementsProgress(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement[] ids) : System.Threading.Tasks.Task<System.Int32[]>`  

```csharp
private System.Threading.Tasks.Task<System.Int32[]> ReadAchievementsProgress(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement[] ids);
```

- `private ReadBlobs<T>(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String[] blobNames) : System.Threading.Tasks.Task<T[]>`  

```csharp
private System.Threading.Tasks.Task<T[]> ReadBlobs<T>(Unity.XGamingRuntime.XGameSaveContainerHandle containerHandle, System.String[] blobNames);
```

- `private ReadImage(System.Byte[] buffer, System.Int32 width, System.Int32 height) : System.Byte[]`  

```csharp
private System.Byte[] ReadImage(System.Byte[] buffer, System.Int32 width, System.Int32 height);
```

- `private ReadStats(System.String[] blobNames) : System.Threading.Tasks.Task<System.Int32[]>`  

```csharp
private System.Threading.Tasks.Task<System.Int32[]> ReadStats(System.String[] blobNames);
```

- `private RemapAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements) : System.Boolean`  

```csharp
private System.Boolean RemapAchievements(System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, Colossal.PSI.Common.AchievementAttribute> achievements);
```

- `private RemapDLCs() : System.Boolean`  

```csharp
private System.Boolean RemapDLCs();
```

- `public ResetAchievements() : System.Void`  

```csharp
public System.Void ResetAchievements();
```

- `private ResetAchievementsAsync() : System.Void`  

```csharp
private System.Void ResetAchievementsAsync();
```

- `private ResolveSignInIssuesWithUi(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.Action<System.Int32> callback) : System.Void`  

```csharp
private System.Void ResolveSignInIssuesWithUi(Colossal.PSI.MicrosoftGdk.GdkPlatform+UserData userData, System.Action<System.Int32> callback);
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

- `public ShowErrorDialog(System.UInt32 hresult) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> ShowErrorDialog(System.UInt32 hresult);
```

- `public ShowErrorDialog(System.Int32 hresult) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> ShowErrorDialog(System.Int32 hresult);
```

- `public ShowOverlay(Colossal.PSI.Common.Page page, System.String extra = null) : System.Void`  

```csharp
public System.Void ShowOverlay(Colossal.PSI.Common.Page page, System.String extra);
```

- `public ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous) : System.Boolean`  

```csharp
public System.Boolean ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous);
```

- `public SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback) : System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags> SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback);
```

- `public SignOut() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SignOut();
```

- `private static Succeeded(System.Int32 hresult, System.String operationFriendlyName, Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID[] suppressMessages = null) : System.Boolean`  

```csharp
private static System.Boolean Succeeded(System.Int32 hresult, System.String operationFriendlyName, Colossal.PSI.MicrosoftGdk.GdkPlatform+ErrorID[] suppressMessages);
```

- `private TryResolvePrivilege(Unity.XGamingRuntime.XUserPrivilege privilege) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> TryResolvePrivilege(Unity.XGamingRuntime.XUserPrivilege privilege);
```

- `public UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId) : System.Void`  

```csharp
public System.Void UnlockAchievement(Colossal.PSI.Common.AchievementId achievementId);
```

- `private UnlockAchievementAsync(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task UnlockAchievementAsync(Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement);
```

- `private UnmountDlcs() : System.Void`  

```csharp
private System.Void UnmountDlcs();
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `public UpdateAchievementAsync(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement, System.Int32 value = 1, Colossal.PSI.Common.IndicateType type = Absolute) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task UpdateAchievementAsync(Colossal.PSI.Common.AchievementId achievementId, Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement gdkAchievement, System.Int32 value, Colossal.PSI.Common.IndicateType type);
```

- `private UpdateRichPresence(System.String key) : System.Void`  

```csharp
private System.Void UpdateRichPresence(System.String key);
```

- `protected UserChangeEventCallback(System.IntPtr context, Unity.XGamingRuntime.XUserLocalId userLocalId, Unity.XGamingRuntime.XUserChangeEvent eventType) : System.Void`  

```csharp
protected System.Void UserChangeEventCallback(System.IntPtr context, Unity.XGamingRuntime.XUserLocalId userLocalId, Unity.XGamingRuntime.XUserChangeEvent eventType);
```

- `public Wipe() : System.Void`  

```csharp
public System.Void Wipe();
```

- `private WipeStats() : System.Void`  

```csharp
private System.Void WipeStats();
```

- `public Write(System.String containerName, System.String blobName, System.Byte[] data) : System.Boolean`  

```csharp
public System.Boolean Write(System.String containerName, System.String blobName, System.Byte[] data);
```

- `private WriteStat(System.ValueTuple<System.String, System.Byte[]> stat) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> WriteStat(System.ValueTuple<System.String, System.Byte[]> stat);
```

- `private WriteStats(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Byte[]>> stats) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> WriteStats(System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, System.Byte[]>> stats);
```

- `public XblCleanupAsync() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> XblCleanupAsync();
```


## Events

- `onAchievementUpdated` : `Colossal.PSI.Common.AchievementUpdatedEventHandler`  

```csharp
public event Colossal.PSI.Common.AchievementUpdatedEventHandler onAchievementUpdated;
```

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `onOverlayStateChanged` : `Colossal.PSI.Common.OnOverlayStateChanged`  

```csharp
public event Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
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


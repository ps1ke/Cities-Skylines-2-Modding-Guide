# Colossal.PSI.PdxSdk.PdxSdkPlatform

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IPlatformSupport<Colossal.PSI.PdxSdk.PdxSdkConfiguration>`, `Colossal.PSI.Common.IPlatformSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`, `Colossal.PSI.Common.IDlcSupport`, `Colossal.PSI.Common.IModSupport`, `Colossal.PSI.Common.IModsUploadSupport`, `Colossal.PSI.Common.IRemoteStorageSupport`, `Colossal.PSI.Common.ITelemetrySupport`, `Colossal.PSI.Common.ITransferSupport`, `Colossal.PSI.PdxSdk.IModsUISupport`  

## Code

```csharp
public class PdxSdkPlatform : Colossal.PSI.Common.IPlatformSupport<Colossal.PSI.PdxSdk.PdxSdkConfiguration>, Colossal.PSI.Common.IPlatformSupport, Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync, Colossal.PSI.Common.IDlcSupport, Colossal.PSI.Common.IModSupport, Colossal.PSI.Common.IModsUploadSupport, Colossal.PSI.Common.IRemoteStorageSupport, Colossal.PSI.Common.ITelemetrySupport, Colossal.PSI.Common.ITransferSupport, Colossal.PSI.PdxSdk.IModsUISupport
{
    private Colossal.PSI.PdxSdk.OnLoggedInEventHandler onLoggedIn;
    private Colossal.PSI.PdxSdk.OnLoggedOutEventHandler onLoggedOut;
    private System.Action onNoLogin;
    private Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler onLegalDocumentStatusChanged;
    private System.Collections.Generic.List<Colossal.PSI.PdxSdk.LegalDocument> m_RequiredExtraDocuments;
    private System.String m_SessionToken;
    private System.String m_AccountUserId;
    private Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler onAccountLinkChanged;
    private Colossal.PSI.Common.AccountLinkState m_AccountLinkState;
    private Colossal.PSI.Common.AccountLinkMismatch m_AccountLinkMismatch;
    private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
    private Colossal.PSI.PdxSdk.PdxSdkConfiguration m_Configuration;
    private System.Boolean m_IsInitialized;
    private System.Boolean m_RegisteredForEvents;
    private PDX.SDK.Contracts.IContext m_SDKContext;
    private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue;
    private System.Func<System.String, System.String> <translationHandler>k__BackingField;
    private Colossal.PSI.PdxSdk.ContentUnlockedEventHandler onContentUnlocked;
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.PdxSdk.ParadoxDlc> m_DlcMap;
    private Colossal.PSI.Common.ModSubscriptionEventHandler onModSubscriptionChanged;
    private Colossal.PSI.Common.ModEventHandler onModDownloadStarted;
    private Colossal.PSI.Common.ModEventHandler onModDownloadCompleted;
    private Colossal.PSI.Common.ModEventHandler onModDownloadFailed;
    private Colossal.PSI.Common.ModSyncEventHandler onModSyncCompleted;
    private Colossal.PSI.Common.ModInstallProgressEventHandler onModInstallProgress;
    private System.Action onDataSyncConflict;
    private System.Action<Colossal.PSI.Common.Mod, System.Boolean> onModStatusChanged;
    private System.Action onActivePlaysetChanged;
    private System.Guid m_DownloadStartedSubscription;
    private System.Guid m_DownloadCompleteSubscription;
    private System.Guid m_ModSubscribedSubscription;
    private System.Guid m_ModUnsubscribedSubscription;
    private System.Guid m_TransferStatusUpdatedSubscription;
    private System.Guid m_InstallProgressSubscription;
    private System.Guid m_ModDownloadFailedSubscription;
    private System.Guid m_ModSyncStatusChangedSubscription;
    private System.Guid m_LoadStatusChangedSubscription;
    private System.Boolean m_SyncOngoing;
    private System.Boolean m_ReloadMods;
    private System.Boolean m_IsTelemetryConsentPresentable;
    private System.Boolean m_TelemetryConsentChoice;
    private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
    private System.Boolean m_IsRunning;
    private System.Collections.Generic.HashSet<System.String> m_CompletedTransfers;
    private PDX.ModsUI.ModsUIView m_ModsUIView;
    private Colossal.PSI.PdxSdk.IPdxModsUI m_PdxModsUI;
    private System.Boolean m_OnGoingPleaseWait;
    private System.Action onModsUIOpened;
    private System.Action onModsUIClosed;
    public static Colossal.Logging.ILog log;
    private static const System.String kWrongUserNameOrPassword;
    private static const System.String kDlcPDXAccountText;
    private static const System.Int32 kPollingInterval;

    public System.Boolean hasEverLoggedIn { get; private set; }
    public System.Boolean hasSessionToken { get; }
    public System.Boolean cachedLoggedIn { get; }
    public Colossal.PSI.Common.AccountLinkState accountLinkState { get; set; }
    public Colossal.PSI.Common.AccountLinkMismatch AccountLinkMismatch { get; }
    public Colossal.PSI.Common.AccountLinkProvider accountLinkProvider { get; }
    private PDX.SDK.Contracts.Credential.ICredential thirdPartyCredentials { private get; }
    public System.String name { get; }
    public System.Boolean isInitialized { get; }
    private System.Func<System.String, System.String> translationHandler { private get; set; }
    public System.Int32 dlcCount { get; }
    public System.String modsRootPath { get; }
    public System.Collections.Generic.KeyValuePair<System.String, System.Collections.Generic.HashSet<System.String>> uiHost { get; }
    public System.Boolean isExternallyControlled { get; }
    public System.Boolean isModsUIActive { get; }
    private System.Boolean onGoingPleaseWait { private get; private set; }

    public PdxSdkPlatform(Colossal.PSI.PdxSdk.PdxSdkConfiguration configuration);

    private System.Void <Configure>b__84_0(System.String option);
    private System.Void <CreateModsUI>b__244_0(System.Object e, System.EventArgs a);
    private System.Void <CreateModsUI>b__244_1(System.Object e, System.EventArgs a);
    private System.Void <CreateModsUI>b__244_2(System.Object e, System.EventArgs a);
    private System.Void <InitializeTelemetryConsent>b__216_0(System.String _, System.String _, System.String _, Colossal.PSI.Common.AccountLinkState _, System.Boolean _);
    private System.Void <InitializeTelemetryConsent>b__216_1(System.String _);
    private System.Void <InitializeTelemetryConsent>b__216_2(Colossal.PSI.PdxSdk.LegalDocument _, System.Int32 _);
    private System.Boolean <ListUnviewedDocuments>b__30_0(PDX.SDK.Contracts.Service.Legal.Models.Document doc);
    private System.Void <RemapDLCs>b__108_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String[] metadata);
    private System.Boolean <set_onGoingPleaseWait>b__233_0();
    private System.Void AfterLogout();
    public System.Void ChangeLanguage(System.String localeId);
    public System.Void ChangeModsUILanguage(System.String localeId);
    private System.Void CheckAccountLinkStatus(PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult thirdParty);
    private System.Threading.Tasks.Task CheckEntitlements(System.Boolean firstLogin);
    public System.Void Configure(Colossal.PSI.PdxSdk.PdxSdkConfiguration configuration);
    private Colossal.PSI.Common.Mod CreateMod(PDX.SDK.Contracts.Service.Mods.Models.IMod mod);
    public System.Void CreateModsUI();
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> CreateParadoxAccount(System.String username, System.String password, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth, System.Boolean marketingPermissions);
    public System.Void DeactivateActivePlayset();
    public System.Boolean Delete(System.String containerName, System.String fileName);
    public System.Threading.Tasks.Task DeleteRemote(System.String remotePath);
    public System.Void DestroyModsUI();
    public System.Void DisableSharing();
    public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>> Download(System.String relativePath, System.String remotePath);
    public System.Threading.Tasks.Task<System.Boolean> EnableModInActivePlayset(System.Int32 modId, System.Boolean enable);
    public System.Void EnableSharing();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
    public System.Boolean Exists(System.String containerName, System.String fileName);
    private System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.GetDetailsResult> GetAccountDetailsAndNotifyLoggedIn();
    private PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider GetAccountLinkProvider();
    private System.String GetConfirmLabel(PDX.SDK.Contracts.Service.Legal.Models.Document document);
    public System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Models.ModCreator> GetCreatorProfile();
    public System.Threading.Tasks.Task<System.Collections.Generic.List<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry>> GetData();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo> GetDetails(Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo);
    public System.String GetDlcName(Colossal.PSI.Common.DlcId dlc);
    public System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
    public System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>> GetLocalData(System.Int32 id);
    private PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform GetModPlatform();
    public System.Threading.Tasks.Task<System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod>> GetModsInActivePlayset();
    public System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
    public System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+SocialProfile> GetSocialProfile();
    public System.Threading.Tasks.Task<System.ValueTuple<Colossal.PSI.Common.IModsUploadSupport+ModTag[], Colossal.PSI.Common.IModsUploadSupport+DLCTag[]>> GetTags();
    public System.Boolean GetTelemetryConsentChoice();
    public System.Boolean HasLocalChanges();
    public System.Void HidePleaseWait();
    public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
    private System.Void InitializeTelemetryConsent();
    public System.Boolean IsCloudSupported();
    public System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlc);
    private System.Boolean IsExtraDocumentViewed(System.String title, System.String type);
    private System.Threading.Tasks.Task<System.Boolean> IsLoggedIn();
    public System.Boolean IsTelemetryConsentPresentable();
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> LinkAccount();
    private System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> LinkAccount(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider accountLinkProvider);
    public System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListAllModsByMe(System.String[] filterTags, System.Int32 pageSize);
    public System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListMods();
    public System.Threading.Tasks.Task<System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document>> ListUnviewedDocuments();
    private System.Threading.Tasks.Task Login(System.Threading.CancellationToken cancellationToken);
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> Login(System.String username, System.String password, System.Threading.CancellationToken cancellationToken);
    private System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> LoginViaToken(System.String token, System.Threading.CancellationToken cancellationToken);
    public System.Threading.Tasks.Task Logout();
    public System.Void LogVersion(System.Text.StringBuilder b);
    public System.Threading.Tasks.Task<System.Boolean> MarkLegalDocumentAsViewed(Colossal.PSI.PdxSdk.LegalDocument document);
    public System.Threading.Tasks.Task<System.Boolean> MarkLegalDocumentAsViewed(System.String title, System.String type);
    private System.Void OnConnectivityStatusChanged(System.Boolean connected);
    private System.Void OnDownloadComplete(PDX.SDK.Contracts.Events.Mods.IModDownloadCompleted args);
    private System.Void OnDownloadStarted(PDX.SDK.Contracts.Events.Mods.IModDownloadStarted args);
    private System.Void OnInstallProgress(PDX.SDK.Contracts.Events.Download.IInstallProgressEvent args);
    private System.Void OnLoadStatusChanged(PDX.SDK.Contracts.Events.Mods.IModLoadStatusChanged args);
    private System.Void OnModDownloadFailed(PDX.SDK.Contracts.Events.Mods.IModDownloadFailed args);
    private System.Void OnModSubscribe(PDX.SDK.Contracts.Events.Mods.IModSubscribed args);
    private System.Void OnModSyncStatusChanged(PDX.SDK.Contracts.Events.Mods.IModSyncStatusChanged args);
    private System.Void OnModUnsubscribe(PDX.SDK.Contracts.Events.Mods.IModUnsubscribed args);
    private System.Void OnPrincipalPlatformUserChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags change);
    private System.Void OnShowLegalDocument(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> documents);
    private System.Void OnTransferUpdated(PDX.SDK.Contracts.Events.Download.ITransferStatusUpdated args);
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> OverwriteAccountLinks();
    private System.Void PollTransfersAsync();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> PublishWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Int32 Read(System.String containerName, System.String fileName, System.Byte[]& data);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> RegisterExistingWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    private System.Void RegisterModsCallbacks();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> RegisterWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    private System.Void ReleaseModsCallbacks();
    private System.Threading.Tasks.Task<System.Boolean> RemapDLCs();
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> ResetPassword(System.String email);
    private static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ExternalLink> SanitizeExternalLinks(System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links);
    private static System.Collections.Generic.List<System.String> SanitizeForumLink(System.String forumLink);
    private static System.String SanitizeUserModVersion(System.String userModVersion);
    public System.Void SendTelemetry<T>(System.String evtName, T evt);
    private System.Void SetExtraDocumentViewed(System.String title, System.String type);
    public System.Void SetPdxModsUI(Colossal.PSI.PdxSdk.IPdxModsUI pdxModsUI);
    public System.Threading.Tasks.Task<System.Boolean> SetTelemetryConsentChoice(System.Boolean allowed);
    public System.Threading.Tasks.Task SetThirdPartyAutoLoginAccepted(System.Boolean value, System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task ShowLegalDocuments();
    public System.Void ShowModDetail(System.Int32 id);
    public System.Void ShowModsUI();
    private System.Void ShowModsUI(System.Action<PDX.ModsUI.ModsUIView> showAction);
    public System.Void ShowModsUIProfilePage();
    public System.Void ShowPleaseWait(System.String title, System.String message);
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.LegalDocument> ShowPrivacyPolicy();
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.LegalDocument> ShowTermsOfUse();
    public System.Threading.Tasks.Task SignOut();
    private System.Void StartPollingTransfers();
    private System.Void StopPollingTransfers();
    public System.Threading.Tasks.Task<System.Boolean> SyncModConflict(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection direction);
    public System.Threading.Tasks.Task SyncMods(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection);
    public System.Void SyncTelemetryConsentChoice();
    private static System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.ModDependency> ToDependencies(Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency[] dependencies);
    private static System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.ModDependency> ToDependencies(System.String[] internalNames);
    private Colossal.PSI.Common.IModsUploadSupport+ModInfo ToModInfo(PDX.SDK.Contracts.Service.Mods.Models.Mod mod);
    private static PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform ToModPlatform(Colossal.Platform platform);
    private static PDX.SDK.Contracts.Service.Mods.Models.PublishWipData ToPublishData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    private static PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData ToPublishUpdateData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    private static PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData ToWIPData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> UnlinkThirdPartyAccount();
    private System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UnlinkThirdPartyAccount(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider accountLinkProvider);
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> UnregisterWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Void Update();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> UpdateExisting(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Void UpdateInputMode();
    public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> UpdateWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
    public System.Threading.Tasks.Task<System.String> Upload(System.String relativePath, System.String remotePath);
    public System.Void Wipe();
    public System.Boolean Write(System.String containerName, System.String fileName, System.Byte[] data);
}
```


## Fields

- `private Colossal.PSI.PdxSdk.OnLoggedInEventHandler onLoggedIn`  

```csharp
private Colossal.PSI.PdxSdk.OnLoggedInEventHandler onLoggedIn;
```

- `private Colossal.PSI.PdxSdk.OnLoggedOutEventHandler onLoggedOut`  

```csharp
private Colossal.PSI.PdxSdk.OnLoggedOutEventHandler onLoggedOut;
```

- `private System.Action onNoLogin`  

```csharp
private System.Action onNoLogin;
```

- `private Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler onLegalDocumentStatusChanged`  

```csharp
private Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler onLegalDocumentStatusChanged;
```

- `private System.Collections.Generic.List<Colossal.PSI.PdxSdk.LegalDocument> m_RequiredExtraDocuments`  

```csharp
private System.Collections.Generic.List<Colossal.PSI.PdxSdk.LegalDocument> m_RequiredExtraDocuments;
```

- `private System.String m_SessionToken`  

```csharp
private System.String m_SessionToken;
```

- `private System.String m_AccountUserId`  

```csharp
private System.String m_AccountUserId;
```

- `private Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler onAccountLinkChanged`  

```csharp
private Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler onAccountLinkChanged;
```

- `private Colossal.PSI.Common.AccountLinkState m_AccountLinkState`  

```csharp
private Colossal.PSI.Common.AccountLinkState m_AccountLinkState;
```

- `private Colossal.PSI.Common.AccountLinkMismatch m_AccountLinkMismatch`  

```csharp
private Colossal.PSI.Common.AccountLinkMismatch m_AccountLinkMismatch;
```

- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  

```csharp
private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `private Colossal.PSI.PdxSdk.PdxSdkConfiguration m_Configuration`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkConfiguration m_Configuration;
```

- `private System.Boolean m_IsInitialized`  

```csharp
private System.Boolean m_IsInitialized;
```

- `private System.Boolean m_RegisteredForEvents`  

```csharp
private System.Boolean m_RegisteredForEvents;
```

- `private PDX.SDK.Contracts.IContext m_SDKContext`  

```csharp
private PDX.SDK.Contracts.IContext m_SDKContext;
```

- `private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue`  

```csharp
private readonly System.Collections.Concurrent.ConcurrentQueue<System.Action> m_MainThreadActionQueue;
```

- `private System.Func<System.String, System.String> <translationHandler>k__BackingField`  

```csharp
private System.Func<System.String, System.String> <translationHandler>k__BackingField;
```

- `private Colossal.PSI.PdxSdk.ContentUnlockedEventHandler onContentUnlocked`  

```csharp
private Colossal.PSI.PdxSdk.ContentUnlockedEventHandler onContentUnlocked;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.PdxSdk.ParadoxDlc> m_DlcMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.PdxSdk.ParadoxDlc> m_DlcMap;
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

- `private System.Action onDataSyncConflict`  

```csharp
private System.Action onDataSyncConflict;
```

- `private System.Action<Colossal.PSI.Common.Mod, System.Boolean> onModStatusChanged`  

```csharp
private System.Action<Colossal.PSI.Common.Mod, System.Boolean> onModStatusChanged;
```

- `private System.Action onActivePlaysetChanged`  

```csharp
private System.Action onActivePlaysetChanged;
```

- `private System.Guid m_DownloadStartedSubscription`  

```csharp
private System.Guid m_DownloadStartedSubscription;
```

- `private System.Guid m_DownloadCompleteSubscription`  

```csharp
private System.Guid m_DownloadCompleteSubscription;
```

- `private System.Guid m_ModSubscribedSubscription`  

```csharp
private System.Guid m_ModSubscribedSubscription;
```

- `private System.Guid m_ModUnsubscribedSubscription`  

```csharp
private System.Guid m_ModUnsubscribedSubscription;
```

- `private System.Guid m_TransferStatusUpdatedSubscription`  

```csharp
private System.Guid m_TransferStatusUpdatedSubscription;
```

- `private System.Guid m_InstallProgressSubscription`  

```csharp
private System.Guid m_InstallProgressSubscription;
```

- `private System.Guid m_ModDownloadFailedSubscription`  

```csharp
private System.Guid m_ModDownloadFailedSubscription;
```

- `private System.Guid m_ModSyncStatusChangedSubscription`  

```csharp
private System.Guid m_ModSyncStatusChangedSubscription;
```

- `private System.Guid m_LoadStatusChangedSubscription`  

```csharp
private System.Guid m_LoadStatusChangedSubscription;
```

- `private System.Boolean m_SyncOngoing`  

```csharp
private System.Boolean m_SyncOngoing;
```

- `private System.Boolean m_ReloadMods`  

```csharp
private System.Boolean m_ReloadMods;
```

- `private System.Boolean m_IsTelemetryConsentPresentable`  

```csharp
private System.Boolean m_IsTelemetryConsentPresentable;
```

- `private System.Boolean m_TelemetryConsentChoice`  

```csharp
private System.Boolean m_TelemetryConsentChoice;
```

- `private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing`  

```csharp
private Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
```

- `private System.Boolean m_IsRunning`  

```csharp
private System.Boolean m_IsRunning;
```

- `private System.Collections.Generic.HashSet<System.String> m_CompletedTransfers`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_CompletedTransfers;
```

- `private PDX.ModsUI.ModsUIView m_ModsUIView`  

```csharp
private PDX.ModsUI.ModsUIView m_ModsUIView;
```

- `private Colossal.PSI.PdxSdk.IPdxModsUI m_PdxModsUI`  

```csharp
private Colossal.PSI.PdxSdk.IPdxModsUI m_PdxModsUI;
```

- `private System.Boolean m_OnGoingPleaseWait`  

```csharp
private System.Boolean m_OnGoingPleaseWait;
```

- `private System.Action onModsUIOpened`  

```csharp
private System.Action onModsUIOpened;
```

- `private System.Action onModsUIClosed`  

```csharp
private System.Action onModsUIClosed;
```

- `public static Colossal.Logging.ILog log`  

```csharp
public static Colossal.Logging.ILog log;
```

- `private static const System.String kWrongUserNameOrPassword`  

```csharp
private static const System.String kWrongUserNameOrPassword;
```

- `private static const System.String kDlcPDXAccountText`  

```csharp
private static const System.String kDlcPDXAccountText;
```

- `private static const System.Int32 kPollingInterval`  

```csharp
private static const System.Int32 kPollingInterval;
```


## Properties

- `public System.Boolean hasEverLoggedIn { get; private set }`  

```csharp
public System.Boolean hasEverLoggedIn { get; private set; }
```

- `public System.Boolean hasSessionToken { get }`  

```csharp
public System.Boolean hasSessionToken { get; }
```

- `public System.Boolean cachedLoggedIn { get }`  

```csharp
public System.Boolean cachedLoggedIn { get; }
```

- `public Colossal.PSI.Common.AccountLinkState accountLinkState { get; set }`  

```csharp
public Colossal.PSI.Common.AccountLinkState accountLinkState { get; set; }
```

- `public Colossal.PSI.Common.AccountLinkMismatch AccountLinkMismatch { get }`  

```csharp
public Colossal.PSI.Common.AccountLinkMismatch AccountLinkMismatch { get; }
```

- `public Colossal.PSI.Common.AccountLinkProvider accountLinkProvider { get }`  

```csharp
public Colossal.PSI.Common.AccountLinkProvider accountLinkProvider { get; }
```

- `private PDX.SDK.Contracts.Credential.ICredential thirdPartyCredentials { private get }`  

```csharp
private PDX.SDK.Contracts.Credential.ICredential thirdPartyCredentials { private get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```

- `private System.Func<System.String, System.String> translationHandler { private get; set }`  

```csharp
private System.Func<System.String, System.String> translationHandler { private get; set; }
```

- `public System.Int32 dlcCount { get }`  

```csharp
public System.Int32 dlcCount { get; }
```

- `public System.String modsRootPath { get }`  

```csharp
public System.String modsRootPath { get; }
```

- `public System.Collections.Generic.KeyValuePair<System.String, System.Collections.Generic.HashSet<System.String>> uiHost { get }`  

```csharp
public System.Collections.Generic.KeyValuePair<System.String, System.Collections.Generic.HashSet<System.String>> uiHost { get; }
```

- `public System.Boolean isExternallyControlled { get }`  

```csharp
public System.Boolean isExternallyControlled { get; }
```

- `public System.Boolean isModsUIActive { get }`  

```csharp
public System.Boolean isModsUIActive { get; }
```

- `private System.Boolean onGoingPleaseWait { private get; private set }`  

```csharp
private System.Boolean onGoingPleaseWait { private get; private set; }
```


## Constructors

- `public PdxSdkPlatform(Colossal.PSI.PdxSdk.PdxSdkConfiguration configuration)`  

```csharp
public PdxSdkPlatform(Colossal.PSI.PdxSdk.PdxSdkConfiguration configuration);
```


## Methods

- `private <Configure>b__84_0(System.String option) : System.Void`  

```csharp
private System.Void <Configure>b__84_0(System.String option);
```

- `private <CreateModsUI>b__244_0(System.Object e, System.EventArgs a) : System.Void`  

```csharp
private System.Void <CreateModsUI>b__244_0(System.Object e, System.EventArgs a);
```

- `private <CreateModsUI>b__244_1(System.Object e, System.EventArgs a) : System.Void`  

```csharp
private System.Void <CreateModsUI>b__244_1(System.Object e, System.EventArgs a);
```

- `private <CreateModsUI>b__244_2(System.Object e, System.EventArgs a) : System.Void`  

```csharp
private System.Void <CreateModsUI>b__244_2(System.Object e, System.EventArgs a);
```

- `private <InitializeTelemetryConsent>b__216_0(System.String _, System.String _, System.String _, Colossal.PSI.Common.AccountLinkState _, System.Boolean _) : System.Void`  

```csharp
private System.Void <InitializeTelemetryConsent>b__216_0(System.String _, System.String _, System.String _, Colossal.PSI.Common.AccountLinkState _, System.Boolean _);
```

- `private <InitializeTelemetryConsent>b__216_1(System.String _) : System.Void`  

```csharp
private System.Void <InitializeTelemetryConsent>b__216_1(System.String _);
```

- `private <InitializeTelemetryConsent>b__216_2(Colossal.PSI.PdxSdk.LegalDocument _, System.Int32 _) : System.Void`  

```csharp
private System.Void <InitializeTelemetryConsent>b__216_2(Colossal.PSI.PdxSdk.LegalDocument _, System.Int32 _);
```

- `private <ListUnviewedDocuments>b__30_0(PDX.SDK.Contracts.Service.Legal.Models.Document doc) : System.Boolean`  

```csharp
private System.Boolean <ListUnviewedDocuments>b__30_0(PDX.SDK.Contracts.Service.Legal.Models.Document doc);
```

- `private <RemapDLCs>b__108_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String[] metadata) : System.Void`  

```csharp
private System.Void <RemapDLCs>b__108_0(Colossal.PSI.Common.DlcId id, Colossal.PSI.Common.DlcAttribute attribute, System.String[] metadata);
```

- `private <set_onGoingPleaseWait>b__233_0() : System.Boolean`  

```csharp
private System.Boolean <set_onGoingPleaseWait>b__233_0();
```

- `private AfterLogout() : System.Void`  

```csharp
private System.Void AfterLogout();
```

- `public ChangeLanguage(System.String localeId) : System.Void`  

```csharp
public System.Void ChangeLanguage(System.String localeId);
```

- `public ChangeModsUILanguage(System.String localeId) : System.Void`  

```csharp
public System.Void ChangeModsUILanguage(System.String localeId);
```

- `private CheckAccountLinkStatus(PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult thirdParty) : System.Void`  

```csharp
private System.Void CheckAccountLinkStatus(PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult thirdParty);
```

- `private CheckEntitlements(System.Boolean firstLogin) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task CheckEntitlements(System.Boolean firstLogin);
```

- `public Configure(Colossal.PSI.PdxSdk.PdxSdkConfiguration configuration) : System.Void`  

```csharp
public System.Void Configure(Colossal.PSI.PdxSdk.PdxSdkConfiguration configuration);
```

- `private CreateMod(PDX.SDK.Contracts.Service.Mods.Models.IMod mod) : Colossal.PSI.Common.Mod`  

```csharp
private Colossal.PSI.Common.Mod CreateMod(PDX.SDK.Contracts.Service.Mods.Models.IMod mod);
```

- `public CreateModsUI() : System.Void`  

```csharp
public System.Void CreateModsUI();
```

- `public CreateParadoxAccount(System.String username, System.String password, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth, System.Boolean marketingPermissions) : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> CreateParadoxAccount(System.String username, System.String password, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth, System.Boolean marketingPermissions);
```

- `public DeactivateActivePlayset() : System.Void`  

```csharp
public System.Void DeactivateActivePlayset();
```

- `public Delete(System.String containerName, System.String fileName) : System.Boolean`  

```csharp
public System.Boolean Delete(System.String containerName, System.String fileName);
```

- `public DeleteRemote(System.String remotePath) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task DeleteRemote(System.String remotePath);
```

- `public DestroyModsUI() : System.Void`  

```csharp
public System.Void DestroyModsUI();
```

- `public DisableSharing() : System.Void`  

```csharp
public System.Void DisableSharing();
```

- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
```

- `public Download(System.String relativePath, System.String remotePath) : System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>> Download(System.String relativePath, System.String remotePath);
```

- `public EnableModInActivePlayset(System.Int32 modId, System.Boolean enable) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> EnableModInActivePlayset(System.Int32 modId, System.Boolean enable);
```

- `public EnableSharing() : System.Void`  

```csharp
public System.Void EnableSharing();
```

- `public EnumerateDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
```

- `public Exists(System.String containerName, System.String fileName) : System.Boolean`  

```csharp
public System.Boolean Exists(System.String containerName, System.String fileName);
```

- `private GetAccountDetailsAndNotifyLoggedIn() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.GetDetailsResult>`  

```csharp
private System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.GetDetailsResult> GetAccountDetailsAndNotifyLoggedIn();
```

- `private GetAccountLinkProvider() : PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider`  

```csharp
private PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider GetAccountLinkProvider();
```

- `private GetConfirmLabel(PDX.SDK.Contracts.Service.Legal.Models.Document document) : System.String`  

```csharp
private System.String GetConfirmLabel(PDX.SDK.Contracts.Service.Legal.Models.Document document);
```

- `public GetCreatorProfile() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Models.ModCreator>`  

```csharp
public System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Models.ModCreator> GetCreatorProfile();
```

- `public GetData() : System.Threading.Tasks.Task<System.Collections.Generic.List<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.List<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry>> GetData();
```

- `public GetDetails(Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModInfo> GetDetails(Colossal.PSI.Common.IModsUploadSupport+ModInfo modInfo);
```

- `public GetDlcName(Colossal.PSI.Common.DlcId dlc) : System.String`  

```csharp
public System.String GetDlcName(Colossal.PSI.Common.DlcId dlc);
```

- `public GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  

```csharp
public System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
```

- `public GetLocalData(System.Int32 id) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, Colossal.PSI.Common.IModsUploadSupport+ModLocalData>> GetLocalData(System.Int32 id);
```

- `private GetModPlatform() : PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform GetModPlatform();
```

- `public GetModsInActivePlayset() : System.Threading.Tasks.Task<System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod>> GetModsInActivePlayset();
```

- `public GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available) : System.Void`  

```csharp
public System.Void GetPersistentQuota(System.String path, System.Int64& total, System.Int64& available);
```

- `public GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  

```csharp
public System.ValueTuple<System.Int64, System.Int64> GetQuota();
```

- `public GetSocialProfile() : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+SocialProfile>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+SocialProfile> GetSocialProfile();
```

- `public GetTags() : System.Threading.Tasks.Task<System.ValueTuple<Colossal.PSI.Common.IModsUploadSupport+ModTag[], Colossal.PSI.Common.IModsUploadSupport+DLCTag[]>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<Colossal.PSI.Common.IModsUploadSupport+ModTag[], Colossal.PSI.Common.IModsUploadSupport+DLCTag[]>> GetTags();
```

- `public GetTelemetryConsentChoice() : System.Boolean`  

```csharp
public System.Boolean GetTelemetryConsentChoice();
```

- `public HasLocalChanges() : System.Boolean`  

```csharp
public System.Boolean HasLocalChanges();
```

- `public HidePleaseWait() : System.Void`  

```csharp
public System.Void HidePleaseWait();
```

- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
```

- `private InitializeTelemetryConsent() : System.Void`  

```csharp
private System.Void InitializeTelemetryConsent();
```

- `public IsCloudSupported() : System.Boolean`  

```csharp
public System.Boolean IsCloudSupported();
```

- `public IsDlcOwned(Colossal.PSI.Common.DlcId dlc) : System.Boolean`  

```csharp
public System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlc);
```

- `private IsExtraDocumentViewed(System.String title, System.String type) : System.Boolean`  

```csharp
private System.Boolean IsExtraDocumentViewed(System.String title, System.String type);
```

- `private IsLoggedIn() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> IsLoggedIn();
```

- `public IsTelemetryConsentPresentable() : System.Boolean`  

```csharp
public System.Boolean IsTelemetryConsentPresentable();
```

- `public LinkAccount() : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> LinkAccount();
```

- `private LinkAccount(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider accountLinkProvider) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
private System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> LinkAccount(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider accountLinkProvider);
```

- `public ListAllModsByMe(System.String[] filterTags = null, System.Int32 pageSize = 20) : System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListAllModsByMe(System.String[] filterTags, System.Int32 pageSize);
```

- `public ListMods() : System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ModInfo>> ListMods();
```

- `public ListUnviewedDocuments() : System.Threading.Tasks.Task<System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document>>`  

```csharp
public System.Threading.Tasks.Task<System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document>> ListUnviewedDocuments();
```

- `private Login(System.Threading.CancellationToken cancellationToken) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task Login(System.Threading.CancellationToken cancellationToken);
```

- `public Login(System.String username, System.String password, System.Threading.CancellationToken cancellationToken) : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> Login(System.String username, System.String password, System.Threading.CancellationToken cancellationToken);
```

- `private LoginViaToken(System.String token, System.Threading.CancellationToken cancellationToken) : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
private System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> LoginViaToken(System.String token, System.Threading.CancellationToken cancellationToken);
```

- `public Logout() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Logout();
```

- `public LogVersion(System.Text.StringBuilder b) : System.Void`  

```csharp
public System.Void LogVersion(System.Text.StringBuilder b);
```

- `public MarkLegalDocumentAsViewed(Colossal.PSI.PdxSdk.LegalDocument document) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> MarkLegalDocumentAsViewed(Colossal.PSI.PdxSdk.LegalDocument document);
```

- `public MarkLegalDocumentAsViewed(System.String title, System.String type) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> MarkLegalDocumentAsViewed(System.String title, System.String type);
```

- `private OnConnectivityStatusChanged(System.Boolean connected) : System.Void`  

```csharp
private System.Void OnConnectivityStatusChanged(System.Boolean connected);
```

- `private OnDownloadComplete(PDX.SDK.Contracts.Events.Mods.IModDownloadCompleted args) : System.Void`  

```csharp
private System.Void OnDownloadComplete(PDX.SDK.Contracts.Events.Mods.IModDownloadCompleted args);
```

- `private OnDownloadStarted(PDX.SDK.Contracts.Events.Mods.IModDownloadStarted args) : System.Void`  

```csharp
private System.Void OnDownloadStarted(PDX.SDK.Contracts.Events.Mods.IModDownloadStarted args);
```

- `private OnInstallProgress(PDX.SDK.Contracts.Events.Download.IInstallProgressEvent args) : System.Void`  

```csharp
private System.Void OnInstallProgress(PDX.SDK.Contracts.Events.Download.IInstallProgressEvent args);
```

- `private OnLoadStatusChanged(PDX.SDK.Contracts.Events.Mods.IModLoadStatusChanged args) : System.Void`  

```csharp
private System.Void OnLoadStatusChanged(PDX.SDK.Contracts.Events.Mods.IModLoadStatusChanged args);
```

- `private OnModDownloadFailed(PDX.SDK.Contracts.Events.Mods.IModDownloadFailed args) : System.Void`  

```csharp
private System.Void OnModDownloadFailed(PDX.SDK.Contracts.Events.Mods.IModDownloadFailed args);
```

- `private OnModSubscribe(PDX.SDK.Contracts.Events.Mods.IModSubscribed args) : System.Void`  

```csharp
private System.Void OnModSubscribe(PDX.SDK.Contracts.Events.Mods.IModSubscribed args);
```

- `private OnModSyncStatusChanged(PDX.SDK.Contracts.Events.Mods.IModSyncStatusChanged args) : System.Void`  

```csharp
private System.Void OnModSyncStatusChanged(PDX.SDK.Contracts.Events.Mods.IModSyncStatusChanged args);
```

- `private OnModUnsubscribe(PDX.SDK.Contracts.Events.Mods.IModUnsubscribed args) : System.Void`  

```csharp
private System.Void OnModUnsubscribe(PDX.SDK.Contracts.Events.Mods.IModUnsubscribed args);
```

- `private OnPrincipalPlatformUserChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags change) : System.Void`  

```csharp
private System.Void OnPrincipalPlatformUserChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.UserChangedFlags change);
```

- `private OnShowLegalDocument(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> documents) : System.Void`  

```csharp
private System.Void OnShowLegalDocument(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Legal.Models.Document> documents);
```

- `private OnTransferUpdated(PDX.SDK.Contracts.Events.Download.ITransferStatusUpdated args) : System.Void`  

```csharp
private System.Void OnTransferUpdated(PDX.SDK.Contracts.Events.Download.ITransferStatusUpdated args);
```

- `public OverwriteAccountLinks() : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> OverwriteAccountLinks();
```

- `private PollTransfersAsync() : System.Void`  

```csharp
private System.Void PollTransfersAsync();
```

- `public Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> Publish(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public PublishWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> PublishWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public Read(System.String containerName, System.String fileName, System.Byte[]& data) : System.Int32`  

```csharp
public System.Int32 Read(System.String containerName, System.String fileName, System.Byte[]& data);
```

- `public RegisterExistingWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> RegisterExistingWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `private RegisterModsCallbacks() : System.Void`  

```csharp
private System.Void RegisterModsCallbacks();
```

- `public RegisterWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> RegisterWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `private ReleaseModsCallbacks() : System.Void`  

```csharp
private System.Void ReleaseModsCallbacks();
```

- `private RemapDLCs() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> RemapDLCs();
```

- `public ResetPassword(System.String email) : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> ResetPassword(System.String email);
```

- `private static SanitizeExternalLinks(System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links) : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ExternalLink>`  

```csharp
private static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ExternalLink> SanitizeExternalLinks(System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links);
```

- `private static SanitizeForumLink(System.String forumLink) : System.Collections.Generic.List<System.String>`  

```csharp
private static System.Collections.Generic.List<System.String> SanitizeForumLink(System.String forumLink);
```

- `private static SanitizeUserModVersion(System.String userModVersion) : System.String`  

```csharp
private static System.String SanitizeUserModVersion(System.String userModVersion);
```

- `public SendTelemetry<T>(System.String evtName, T evt) : System.Void`  

```csharp
public System.Void SendTelemetry<T>(System.String evtName, T evt);
```

- `private SetExtraDocumentViewed(System.String title, System.String type) : System.Void`  

```csharp
private System.Void SetExtraDocumentViewed(System.String title, System.String type);
```

- `public SetPdxModsUI(Colossal.PSI.PdxSdk.IPdxModsUI pdxModsUI) : System.Void`  

```csharp
public System.Void SetPdxModsUI(Colossal.PSI.PdxSdk.IPdxModsUI pdxModsUI);
```

- `public SetTelemetryConsentChoice(System.Boolean allowed) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> SetTelemetryConsentChoice(System.Boolean allowed);
```

- `public SetThirdPartyAutoLoginAccepted(System.Boolean value, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SetThirdPartyAutoLoginAccepted(System.Boolean value, System.Threading.CancellationToken token);
```

- `private ShowLegalDocuments() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task ShowLegalDocuments();
```

- `public ShowModDetail(System.Int32 id) : System.Void`  

```csharp
public System.Void ShowModDetail(System.Int32 id);
```

- `public ShowModsUI() : System.Void`  

```csharp
public System.Void ShowModsUI();
```

- `private ShowModsUI(System.Action<PDX.ModsUI.ModsUIView> showAction) : System.Void`  

```csharp
private System.Void ShowModsUI(System.Action<PDX.ModsUI.ModsUIView> showAction);
```

- `public ShowModsUIProfilePage() : System.Void`  

```csharp
public System.Void ShowModsUIProfilePage();
```

- `public ShowPleaseWait(System.String title = , System.String message = ) : System.Void`  

```csharp
public System.Void ShowPleaseWait(System.String title, System.String message);
```

- `public ShowPrivacyPolicy() : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.LegalDocument>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.LegalDocument> ShowPrivacyPolicy();
```

- `public ShowTermsOfUse() : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.LegalDocument>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.LegalDocument> ShowTermsOfUse();
```

- `public SignOut() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SignOut();
```

- `private StartPollingTransfers() : System.Void`  

```csharp
private System.Void StartPollingTransfers();
```

- `private StopPollingTransfers() : System.Void`  

```csharp
private System.Void StopPollingTransfers();
```

- `public SyncModConflict(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection direction) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> SyncModConflict(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection direction);
```

- `public SyncMods(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection = Default) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SyncMods(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection);
```

- `public SyncTelemetryConsentChoice() : System.Void`  

```csharp
public System.Void SyncTelemetryConsentChoice();
```

- `private static ToDependencies(Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency[] dependencies) : System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.ModDependency>`  

```csharp
private static System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.ModDependency> ToDependencies(Colossal.PSI.Common.IModsUploadSupport+ModInfo+ModDependency[] dependencies);
```

- `private static ToDependencies(System.String[] internalNames) : System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.ModDependency>`  

```csharp
private static System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.ModDependency> ToDependencies(System.String[] internalNames);
```

- `private ToModInfo(PDX.SDK.Contracts.Service.Mods.Models.Mod mod) : Colossal.PSI.Common.IModsUploadSupport+ModInfo`  

```csharp
private Colossal.PSI.Common.IModsUploadSupport+ModInfo ToModInfo(PDX.SDK.Contracts.Service.Mods.Models.Mod mod);
```

- `private static ToModPlatform(Colossal.Platform platform) : PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform`  

```csharp
private static PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform ToModPlatform(Colossal.Platform platform);
```

- `private static ToPublishData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : PDX.SDK.Contracts.Service.Mods.Models.PublishWipData`  

```csharp
private static PDX.SDK.Contracts.Service.Mods.Models.PublishWipData ToPublishData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `private static ToPublishUpdateData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData`  

```csharp
private static PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData ToPublishUpdateData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `private static ToWIPData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData`  

```csharp
private static PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData ToWIPData(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public UnlinkThirdPartyAccount() : System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport> UnlinkThirdPartyAccount();
```

- `private UnlinkThirdPartyAccount(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider accountLinkProvider) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
private System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UnlinkThirdPartyAccount(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider accountLinkProvider);
```

- `public UnregisterWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> UnregisterWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `public UpdateExisting(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> UpdateExisting(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public UpdateInputMode() : System.Void`  

```csharp
public System.Void UpdateInputMode();
```

- `public UpdateWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod) : System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult>`  

```csharp
public System.Threading.Tasks.Task<Colossal.PSI.Common.IModsUploadSupport+ModOperationResult> UpdateWIP(Colossal.PSI.Common.IModsUploadSupport+ModInfo mod);
```

- `public Upload(System.String relativePath, System.String remotePath) : System.Threading.Tasks.Task<System.String>`  

```csharp
public System.Threading.Tasks.Task<System.String> Upload(System.String relativePath, System.String remotePath);
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

- `onLoggedIn` : `Colossal.PSI.PdxSdk.OnLoggedInEventHandler`  

```csharp
public event Colossal.PSI.PdxSdk.OnLoggedInEventHandler onLoggedIn;
```

- `onLoggedOut` : `Colossal.PSI.PdxSdk.OnLoggedOutEventHandler`  

```csharp
public event Colossal.PSI.PdxSdk.OnLoggedOutEventHandler onLoggedOut;
```

- `onNoLogin` : `System.Action`  

```csharp
public event System.Action onNoLogin;
```

- `onLegalDocumentStatusChanged` : `Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler onLegalDocumentStatusChanged;
```

- `onAccountLinkChanged` : `Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler`  

```csharp
public event Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler onAccountLinkChanged;
```

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `onContentUnlocked` : `Colossal.PSI.PdxSdk.ContentUnlockedEventHandler`  

```csharp
public event Colossal.PSI.PdxSdk.ContentUnlockedEventHandler onContentUnlocked;
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

- `onDataSyncConflict` : `System.Action`  

```csharp
public event System.Action onDataSyncConflict;
```

- `onModStatusChanged` : `System.Action<Colossal.PSI.Common.Mod, System.Boolean>`  

```csharp
public event System.Action<Colossal.PSI.Common.Mod, System.Boolean> onModStatusChanged;
```

- `onActivePlaysetChanged` : `System.Action`  

```csharp
public event System.Action onActivePlaysetChanged;
```

- `onTransferOnGoing` : `Colossal.PSI.Common.TransferEventHandler`  

```csharp
public event Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
```

- `onModsUIOpened` : `System.Action`  

```csharp
public event System.Action onModsUIOpened;
```

- `onModsUIClosed` : `System.Action`  

```csharp
public event System.Action onModsUIClosed;
```


## Nested types

- `Colossal.PSI.PdxSdk.PdxSdkPlatform+RequestReport`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+Logger`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+ActiveModsResult`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+DLCTagHelper`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass107_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass151_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass152_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass153_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass154_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass155_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass163_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass179_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass184_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass242_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass26_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass27_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass29_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<>c__DisplayClass59_0`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ChangeLanguage>d__88`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<CheckEntitlements>d__107`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<CreateParadoxAccount>d__42`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<DeactivateActivePlayset>d__165`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<DeleteRemote>d__208`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Dispose>d__91`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Download>d__207`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<EnableModInActivePlayset>d__166`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetAccountDetailsAndNotifyLoggedIn>d__37`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetCreatorProfile>d__167`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetData>d__205`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetDetails>d__183`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetLocalData>d__184`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetModsInActivePlayset>d__164`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetSocialProfile>d__180`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<GetTags>d__178`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Initialize>d__89`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<IsLoggedIn>d__58`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<LinkAccount>d__60`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<LinkAccount>d__61`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ListAllModsByMe>d__179`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ListMods>d__182`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ListUnviewedDocuments>d__30`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Login>d__34`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Login>d__36`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<LoginViaToken>d__35`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Logout>d__38`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<MarkLegalDocumentAsViewed>d__28`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<MarkLegalDocumentAsViewed>d__29`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<OnDownloadComplete>d__154`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<OnDownloadStarted>d__153`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<OnModDownloadFailed>d__155`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<OnModSubscribe>d__151`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<OnModUnsubscribe>d__152`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<OverwriteAccountLinks>d__64`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<PollTransfersAsync>d__225`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Publish>d__172`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<PublishWIP>d__176`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<RegisterExistingWIP>d__175`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<RegisterWIP>d__174`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<RemapDLCs>d__108`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ResetPassword>d__40`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<SendTelemetry>d__211<T>`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<SetTelemetryConsentChoice>d__214`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ShowLegalDocuments>d__25`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ShowPrivacyPolicy>d__31`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ShowTermsOfUse>d__32`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<SignOut>d__90`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<SyncModConflict>d__160`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<SyncMods>d__159`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<SyncTelemetryConsentChoice>d__215`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<ToDependencies>d__192`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<UnlinkThirdPartyAccount>d__62`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<UnlinkThirdPartyAccount>d__63`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<UnregisterWIP>d__181`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<UpdateExisting>d__173`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<UpdateWIP>d__177`  
- `Colossal.PSI.PdxSdk.PdxSdkPlatform+<Upload>d__206`  


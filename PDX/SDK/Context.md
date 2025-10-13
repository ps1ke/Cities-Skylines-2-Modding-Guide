# PDX.SDK.Context

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.IContext`  

**Attributes:** `Preserve`  

## Code

```csharp
public class Context : PDX.SDK.Contracts.IContext
{
    private readonly PDX.SDK.Contracts.Service.Account.IAccountService <Account>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.DataStorage.IDataStorageService <DataStorage>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService <ThirdParty>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.Legal.ILegalService <Legal>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService <Loyalty>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.Profile.IProfileService <Profile>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.Telemetry.ITelemetryService <Telemetry>k__BackingField;
    private readonly PDX.SDK.Contracts.Service.Inventory.IInventoryService <Inventory>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.IModsService _modsService;
    private readonly PDX.SDK.Contracts.Events.IEventHub <Events>k__BackingField;
    private readonly System.String <Namespace>k__BackingField;
    private readonly PDX.SDK.Contracts.Enums.Platform <Platform>k__BackingField;
    private readonly System.DateTime <SessionStart>k__BackingField;
    private System.Threading.SynchronizationContext <MainThreadSynchronizationContext>k__BackingField;
    private PDX.SDK.Network.HTTP <HTTP>k__BackingField;
    private PDX.SDK.Internal.Util.FileIO <FileIO>k__BackingField;
    private readonly PDX.SDK.Internal.Cache.StateCache <StateCache>k__BackingField;
    private PDX.SDK.Contracts.Logging.ILogger <Logger>k__BackingField;
    private System.String <TelemetryUserIdType>k__BackingField;
    private System.String <PseudonymizedId>k__BackingField;
    private System.String <ApplicationSessionId>k__BackingField;
    private System.String <MachineUId>k__BackingField;
    private System.String <MachineGeneratedUId>k__BackingField;
    private PDX.SDK.Internal.Credential.ICredentialFactory <CredentialFactory>k__BackingField;
    private PDX.SDK.Internal.Credential.IRequestBuilderCredentialBridge <RequestBuilderCredentialBridge>k__BackingField;
    private readonly PDX.SDK.Internal.Util.IPathFactory <PathFactory>k__BackingField;
    private readonly PDX.SDK.Internal.Util.ICancellationTokenRegister <CancellationTokenRegister>k__BackingField;
    private readonly External.TinyIoc.TinyIoCContainer <Container>k__BackingField;
    private readonly PDX.SDK.Contracts.Configuration.Config _config;
    private static PDX.SDK.Internal.Util.FileLocks <DiskFileLocks>k__BackingField;
    private static System.Object <StandardCallsLock>k__BackingField;
    private static const System.String SdkVersionTextFileName;

    public PDX.SDK.Contracts.Service.Account.IAccountService Account { get; }
    public PDX.SDK.Contracts.Service.DataStorage.IDataStorageService DataStorage { get; }
    public PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService ThirdParty { get; }
    public PDX.SDK.Contracts.Service.Legal.ILegalService Legal { get; }
    public PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService Loyalty { get; }
    public PDX.SDK.Contracts.Service.Profile.IProfileService Profile { get; }
    public PDX.SDK.Contracts.Service.Telemetry.ITelemetryService Telemetry { get; }
    public PDX.SDK.Contracts.Service.Inventory.IInventoryService Inventory { get; }
    public PDX.SDK.Contracts.Service.Mods.IModsService Mods { get; }
    public PDX.SDK.Contracts.Events.IEventHub Events { get; }
    public System.String Namespace { get; }
    public PDX.SDK.Contracts.Enums.Platform Platform { get; }
    public PDX.SDK.Contracts.Configuration.Config Config { get; }
    public System.DateTime SessionStart { get; }
    internal System.Threading.SynchronizationContext MainThreadSynchronizationContext { internal get; private set; }
    internal PDX.SDK.Network.HTTP HTTP { internal get; internal set; }
    internal PDX.SDK.Internal.Util.FileIO FileIO { internal get; internal set; }
    internal PDX.SDK.Internal.Cache.StateCache StateCache { internal get; }
    internal PDX.SDK.Contracts.Logging.ILogger Logger { internal get; private set; }
    internal System.String TelemetryUserIdType { internal get; internal set; }
    internal System.String PseudonymizedId { internal get; internal set; }
    internal System.String ApplicationSessionId { internal get; internal set; }
    internal System.String MachineUId { internal get; private set; }
    internal System.String MachineGeneratedUId { internal get; private set; }
    internal static PDX.SDK.Internal.Util.FileLocks DiskFileLocks { internal get; private set; }
    internal static System.Object StandardCallsLock { internal get; private set; }
    internal PDX.SDK.Internal.Credential.ICredentialFactory CredentialFactory { internal get; internal set; }
    internal PDX.SDK.Internal.Credential.IRequestBuilderCredentialBridge RequestBuilderCredentialBridge { internal get; internal set; }
    internal PDX.SDK.Internal.Util.IPathFactory PathFactory { internal get; }
    internal PDX.SDK.Internal.Util.ICancellationTokenRegister CancellationTokenRegister { internal get; }
    internal External.TinyIoc.TinyIoCContainer Container { internal get; }

    private Context(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config);

    private System.Void <Init>b__118_0();
    private System.Threading.Tasks.Task<System.Boolean> <SetMachineUid>b__127_0();
    internal System.Void CleanTempFileStorage();
    internal System.Threading.Tasks.Task CleanUpSyncedState();
    internal System.Threading.Tasks.Task ClearLoginSession(System.Boolean hardClear);
    private PDX.SDK.Internal.Service.Telemetry.TelemetryService ConstructTelemetryService();
    public static System.Threading.Tasks.Task<PDX.SDK.Contracts.IContext> Create(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config);
    private PDX.SDK.Network.HTTP CreateHttpClient();
    internal static PDX.SDK.Context CreateWithoutInit(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config);
    private System.Void DoPlatformSpecificInit();
    private System.String GenerateUUId();
    internal System.Threading.Tasks.Task<System.Boolean> GetLoggedIn();
    public static System.String[] GetMiscUtilStrings();
    internal System.String GetPlatform();
    public PDX.SDK.Contracts.Service.Generic.IStorageInformation GetStorageInformation();
    public System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers(System.Nullable<PDX.SDK.Contracts.Enums.ETransferType> transferType, System.Nullable<PDX.SDK.Contracts.Enums.ETransferState> state, System.Nullable<PDX.SDK.Contracts.Enums.ETransferServiceType> serviceType, System.String transferId);
    internal System.Threading.Tasks.Task Init();
    private System.Boolean InnerSetMachineUid();
    public System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
    private System.Threading.Tasks.Task OnConfigUpdated(PDX.SDK.Contracts.Configuration.Config cfg);
    private System.Void OnDefaultHeadersUpdated();
    private System.Void OnDiskIOUpdated();
    internal System.Threading.Tasks.Task SetLoggedIn(System.String userId, System.String sessionToken, System.String refreshToken, PDX.SDK.Contracts.Enums.TrustLevel trustLevel, System.String namespace, PDX.SDK.Contracts.Internal.FlowData flowData);
    private System.Threading.Tasks.Task<System.Boolean> SetMachineUid();
    internal System.Threading.Tasks.Task SetTelemetryData(System.String pseudonymizedId, System.String idType);
    private System.Threading.Tasks.Task SetTelemetryUUId();
    public System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Shutdown();
    public System.Threading.Tasks.Task UpdateConfig(PDX.SDK.Contracts.Configuration.Config cfg);
    private static System.Void ValidateConfig(PDX.SDK.Contracts.Configuration.Config config);
    private System.Threading.Tasks.Task WriteSDKInfoFile();
}
```


## Fields

- `private readonly PDX.SDK.Contracts.Service.Account.IAccountService <Account>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.Account.IAccountService <Account>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.DataStorage.IDataStorageService <DataStorage>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.DataStorage.IDataStorageService <DataStorage>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService <ThirdParty>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService <ThirdParty>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.Legal.ILegalService <Legal>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.Legal.ILegalService <Legal>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService <Loyalty>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService <Loyalty>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.Profile.IProfileService <Profile>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.Profile.IProfileService <Profile>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.Telemetry.ITelemetryService <Telemetry>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.Telemetry.ITelemetryService <Telemetry>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Service.Inventory.IInventoryService <Inventory>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Service.Inventory.IInventoryService <Inventory>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.IModsService _modsService`  

```csharp
private PDX.SDK.Contracts.Service.Mods.IModsService _modsService;
```

- `private readonly PDX.SDK.Contracts.Events.IEventHub <Events>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Events.IEventHub <Events>k__BackingField;
```

- `private readonly System.String <Namespace>k__BackingField`  

```csharp
private readonly System.String <Namespace>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Enums.Platform <Platform>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Enums.Platform <Platform>k__BackingField;
```

- `private readonly System.DateTime <SessionStart>k__BackingField`  

```csharp
private readonly System.DateTime <SessionStart>k__BackingField;
```

- `private System.Threading.SynchronizationContext <MainThreadSynchronizationContext>k__BackingField`  

```csharp
private System.Threading.SynchronizationContext <MainThreadSynchronizationContext>k__BackingField;
```

- `private PDX.SDK.Network.HTTP <HTTP>k__BackingField`  

```csharp
private PDX.SDK.Network.HTTP <HTTP>k__BackingField;
```

- `private PDX.SDK.Internal.Util.FileIO <FileIO>k__BackingField`  

```csharp
private PDX.SDK.Internal.Util.FileIO <FileIO>k__BackingField;
```

- `private readonly PDX.SDK.Internal.Cache.StateCache <StateCache>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Cache.StateCache <StateCache>k__BackingField;
```

- `private PDX.SDK.Contracts.Logging.ILogger <Logger>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Logging.ILogger <Logger>k__BackingField;
```

- `private System.String <TelemetryUserIdType>k__BackingField`  

```csharp
private System.String <TelemetryUserIdType>k__BackingField;
```

- `private System.String <PseudonymizedId>k__BackingField`  

```csharp
private System.String <PseudonymizedId>k__BackingField;
```

- `private System.String <ApplicationSessionId>k__BackingField`  

```csharp
private System.String <ApplicationSessionId>k__BackingField;
```

- `private System.String <MachineUId>k__BackingField`  

```csharp
private System.String <MachineUId>k__BackingField;
```

- `private System.String <MachineGeneratedUId>k__BackingField`  

```csharp
private System.String <MachineGeneratedUId>k__BackingField;
```

- `private PDX.SDK.Internal.Credential.ICredentialFactory <CredentialFactory>k__BackingField`  

```csharp
private PDX.SDK.Internal.Credential.ICredentialFactory <CredentialFactory>k__BackingField;
```

- `private PDX.SDK.Internal.Credential.IRequestBuilderCredentialBridge <RequestBuilderCredentialBridge>k__BackingField`  

```csharp
private PDX.SDK.Internal.Credential.IRequestBuilderCredentialBridge <RequestBuilderCredentialBridge>k__BackingField;
```

- `private readonly PDX.SDK.Internal.Util.IPathFactory <PathFactory>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Util.IPathFactory <PathFactory>k__BackingField;
```

- `private readonly PDX.SDK.Internal.Util.ICancellationTokenRegister <CancellationTokenRegister>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Util.ICancellationTokenRegister <CancellationTokenRegister>k__BackingField;
```

- `private readonly External.TinyIoc.TinyIoCContainer <Container>k__BackingField`  

```csharp
private readonly External.TinyIoc.TinyIoCContainer <Container>k__BackingField;
```

- `private readonly PDX.SDK.Contracts.Configuration.Config _config`  

```csharp
private readonly PDX.SDK.Contracts.Configuration.Config _config;
```

- `private static PDX.SDK.Internal.Util.FileLocks <DiskFileLocks>k__BackingField`  

```csharp
private static PDX.SDK.Internal.Util.FileLocks <DiskFileLocks>k__BackingField;
```

- `private static System.Object <StandardCallsLock>k__BackingField`  

```csharp
private static System.Object <StandardCallsLock>k__BackingField;
```

- `private static const System.String SdkVersionTextFileName`  

```csharp
private static const System.String SdkVersionTextFileName;
```


## Properties

- `public PDX.SDK.Contracts.Service.Account.IAccountService Account { get }`  

```csharp
public PDX.SDK.Contracts.Service.Account.IAccountService Account { get; }
```

- `public PDX.SDK.Contracts.Service.DataStorage.IDataStorageService DataStorage { get }`  

```csharp
public PDX.SDK.Contracts.Service.DataStorage.IDataStorageService DataStorage { get; }
```

- `public PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService ThirdParty { get }`  

```csharp
public PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService ThirdParty { get; }
```

- `public PDX.SDK.Contracts.Service.Legal.ILegalService Legal { get }`  

```csharp
public PDX.SDK.Contracts.Service.Legal.ILegalService Legal { get; }
```

- `public PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService Loyalty { get }`  

```csharp
public PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService Loyalty { get; }
```

- `public PDX.SDK.Contracts.Service.Profile.IProfileService Profile { get }`  

```csharp
public PDX.SDK.Contracts.Service.Profile.IProfileService Profile { get; }
```

- `public PDX.SDK.Contracts.Service.Telemetry.ITelemetryService Telemetry { get }`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.ITelemetryService Telemetry { get; }
```

- `public PDX.SDK.Contracts.Service.Inventory.IInventoryService Inventory { get }`  

```csharp
public PDX.SDK.Contracts.Service.Inventory.IInventoryService Inventory { get; }
```

- `public PDX.SDK.Contracts.Service.Mods.IModsService Mods { get }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.IModsService Mods { get; }
```

- `public PDX.SDK.Contracts.Events.IEventHub Events { get }`  

```csharp
public PDX.SDK.Contracts.Events.IEventHub Events { get; }
```

- `public System.String Namespace { get }`  

```csharp
public System.String Namespace { get; }
```

- `public PDX.SDK.Contracts.Enums.Platform Platform { get }`  

```csharp
public PDX.SDK.Contracts.Enums.Platform Platform { get; }
```

- `public PDX.SDK.Contracts.Configuration.Config Config { get }`  

```csharp
public PDX.SDK.Contracts.Configuration.Config Config { get; }
```

- `public System.DateTime SessionStart { get }`  

```csharp
public System.DateTime SessionStart { get; }
```

- `internal System.Threading.SynchronizationContext MainThreadSynchronizationContext { internal get; private set }`  

```csharp
internal System.Threading.SynchronizationContext MainThreadSynchronizationContext { internal get; private set; }
```

- `internal PDX.SDK.Network.HTTP HTTP { internal get; internal set }`  

```csharp
internal PDX.SDK.Network.HTTP HTTP { internal get; internal set; }
```

- `internal PDX.SDK.Internal.Util.FileIO FileIO { internal get; internal set }`  

```csharp
internal PDX.SDK.Internal.Util.FileIO FileIO { internal get; internal set; }
```

- `internal PDX.SDK.Internal.Cache.StateCache StateCache { internal get }`  

```csharp
internal PDX.SDK.Internal.Cache.StateCache StateCache { internal get; }
```

- `internal PDX.SDK.Contracts.Logging.ILogger Logger { internal get; private set }`  

```csharp
internal PDX.SDK.Contracts.Logging.ILogger Logger { internal get; private set; }
```

- `internal System.String TelemetryUserIdType { internal get; internal set }`  

```csharp
internal System.String TelemetryUserIdType { internal get; internal set; }
```

- `internal System.String PseudonymizedId { internal get; internal set }`  

```csharp
internal System.String PseudonymizedId { internal get; internal set; }
```

- `internal System.String ApplicationSessionId { internal get; internal set }`  

```csharp
internal System.String ApplicationSessionId { internal get; internal set; }
```

- `internal System.String MachineUId { internal get; private set }`  

```csharp
internal System.String MachineUId { internal get; private set; }
```

- `internal System.String MachineGeneratedUId { internal get; private set }`  

```csharp
internal System.String MachineGeneratedUId { internal get; private set; }
```

- `internal static PDX.SDK.Internal.Util.FileLocks DiskFileLocks { internal get; private set }`  

```csharp
internal static PDX.SDK.Internal.Util.FileLocks DiskFileLocks { internal get; private set; }
```

- `internal static System.Object StandardCallsLock { internal get; private set }`  

```csharp
internal static System.Object StandardCallsLock { internal get; private set; }
```

- `internal PDX.SDK.Internal.Credential.ICredentialFactory CredentialFactory { internal get; internal set }`  

```csharp
internal PDX.SDK.Internal.Credential.ICredentialFactory CredentialFactory { internal get; internal set; }
```

- `internal PDX.SDK.Internal.Credential.IRequestBuilderCredentialBridge RequestBuilderCredentialBridge { internal get; internal set }`  

```csharp
internal PDX.SDK.Internal.Credential.IRequestBuilderCredentialBridge RequestBuilderCredentialBridge { internal get; internal set; }
```

- `internal PDX.SDK.Internal.Util.IPathFactory PathFactory { internal get }`  

```csharp
internal PDX.SDK.Internal.Util.IPathFactory PathFactory { internal get; }
```

- `internal PDX.SDK.Internal.Util.ICancellationTokenRegister CancellationTokenRegister { internal get }`  

```csharp
internal PDX.SDK.Internal.Util.ICancellationTokenRegister CancellationTokenRegister { internal get; }
```

- `internal External.TinyIoc.TinyIoCContainer Container { internal get }`  

```csharp
internal External.TinyIoc.TinyIoCContainer Container { internal get; }
```


## Constructors

- `private Context(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config)`  

```csharp
private Context(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config);
```


## Methods

- `private <Init>b__118_0() : System.Void`  

```csharp
private System.Void <Init>b__118_0();
```

- `private <SetMachineUid>b__127_0() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> <SetMachineUid>b__127_0();
```

- `internal CleanTempFileStorage() : System.Void`  

```csharp
internal System.Void CleanTempFileStorage();
```

- `internal CleanUpSyncedState() : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task CleanUpSyncedState();
```

- `internal ClearLoginSession(System.Boolean hardClear = False) : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task ClearLoginSession(System.Boolean hardClear);
```

- `private ConstructTelemetryService() : PDX.SDK.Internal.Service.Telemetry.TelemetryService`  

```csharp
private PDX.SDK.Internal.Service.Telemetry.TelemetryService ConstructTelemetryService();
```

- `public static Create(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.IContext>`  

```csharp
public static System.Threading.Tasks.Task<PDX.SDK.Contracts.IContext> Create(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config);
```

- `private CreateHttpClient() : PDX.SDK.Network.HTTP`  

```csharp
private PDX.SDK.Network.HTTP CreateHttpClient();
```

- `internal static CreateWithoutInit(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config = null) : PDX.SDK.Context`  

```csharp
internal static PDX.SDK.Context CreateWithoutInit(PDX.SDK.Contracts.Enums.Platform platform, System.String namespace, PDX.SDK.Contracts.Configuration.Config config);
```

- `private DoPlatformSpecificInit() : System.Void`  

```csharp
private System.Void DoPlatformSpecificInit();
```

- `private GenerateUUId() : System.String`  

```csharp
private System.String GenerateUUId();
```

- `internal GetLoggedIn() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
internal System.Threading.Tasks.Task<System.Boolean> GetLoggedIn();
```

- `public static GetMiscUtilStrings() : System.String[]`  

```csharp
public static System.String[] GetMiscUtilStrings();
```

- `internal GetPlatform() : System.String`  

```csharp
internal System.String GetPlatform();
```

- `public GetStorageInformation() : PDX.SDK.Contracts.Service.Generic.IStorageInformation`  

```csharp
public PDX.SDK.Contracts.Service.Generic.IStorageInformation GetStorageInformation();
```

- `public GetTransfers(System.Nullable<PDX.SDK.Contracts.Enums.ETransferType> transferType = null, System.Nullable<PDX.SDK.Contracts.Enums.ETransferState> state = null, System.Nullable<PDX.SDK.Contracts.Enums.ETransferServiceType> serviceType = null, System.String transferId = null) : System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus>`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Network.ITransferStatus> GetTransfers(System.Nullable<PDX.SDK.Contracts.Enums.ETransferType> transferType, System.Nullable<PDX.SDK.Contracts.Enums.ETransferState> state, System.Nullable<PDX.SDK.Contracts.Enums.ETransferServiceType> serviceType, System.String transferId);
```

- `internal Init() : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task Init();
```

- `private InnerSetMachineUid() : System.Boolean`  

```csharp
private System.Boolean InnerSetMachineUid();
```

- `public Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel = L1_Debug, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
public System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `private OnConfigUpdated(PDX.SDK.Contracts.Configuration.Config cfg) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task OnConfigUpdated(PDX.SDK.Contracts.Configuration.Config cfg);
```

- `private OnDefaultHeadersUpdated() : System.Void`  

```csharp
private System.Void OnDefaultHeadersUpdated();
```

- `private OnDiskIOUpdated() : System.Void`  

```csharp
private System.Void OnDiskIOUpdated();
```

- `internal SetLoggedIn(System.String userId, System.String sessionToken, System.String refreshToken, PDX.SDK.Contracts.Enums.TrustLevel trustLevel, System.String namespace, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task SetLoggedIn(System.String userId, System.String sessionToken, System.String refreshToken, PDX.SDK.Contracts.Enums.TrustLevel trustLevel, System.String namespace, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `private SetMachineUid() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> SetMachineUid();
```

- `internal SetTelemetryData(System.String pseudonymizedId, System.String idType) : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task SetTelemetryData(System.String pseudonymizedId, System.String idType);
```

- `private SetTelemetryUUId() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task SetTelemetryUUId();
```

- `public Shutdown() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Shutdown();
```

- `public UpdateConfig(PDX.SDK.Contracts.Configuration.Config cfg) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task UpdateConfig(PDX.SDK.Contracts.Configuration.Config cfg);
```

- `private static ValidateConfig(PDX.SDK.Contracts.Configuration.Config config) : System.Void`  

```csharp
private static System.Void ValidateConfig(PDX.SDK.Contracts.Configuration.Config config);
```

- `private WriteSDKInfoFile() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task WriteSDKInfoFile();
```


## Nested types

- `PDX.SDK.Context+<CleanUpSyncedState>d__132`  
- `PDX.SDK.Context+<ClearLoginSession>d__121`  
- `PDX.SDK.Context+<Create>d__0`  
- `PDX.SDK.Context+<GetLoggedIn>d__48`  
- `PDX.SDK.Context+<Init>d__118`  
- `PDX.SDK.Context+<OnConfigUpdated>d__124`  
- `PDX.SDK.Context+<SetLoggedIn>d__120`  
- `PDX.SDK.Context+<SetMachineUid>d__127`  
- `PDX.SDK.Context+<SetTelemetryData>d__122`  
- `PDX.SDK.Context+<SetTelemetryUUId>d__129`  
- `PDX.SDK.Context+<Shutdown>d__115`  
- `PDX.SDK.Context+<UpdateConfig>d__113`  
- `PDX.SDK.Context+<WriteSDKInfoFile>d__130`  


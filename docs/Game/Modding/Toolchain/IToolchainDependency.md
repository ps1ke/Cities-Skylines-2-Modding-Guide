# Game.Modding.Toolchain.IToolchainDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** interface abstract public  


## Fields

- `public static const System.String CSII_PATHSET`  
- `public static const System.String CSII_INSTALLATIONPATH`  
- `public static const System.String CSII_USERDATAPATH`  
- `public static const System.String CSII_TOOLPATH`  
- `public static const System.String CSII_LOCALMODSPATH`  
- `public static const System.String CSII_UNITYMODPROJECTPATH`  
- `public static const System.String CSII_UNITYVERSION`  
- `public static const System.String CSII_ENTITIESVERSION`  
- `public static const System.String CSII_MODPOSTPROCESSORPATH`  
- `public static const System.String CSII_MODPUBLISHERPATH`  
- `public static const System.String CSII_MANAGEDPATH`  
- `public static const System.String CSII_PDXCACHEPATH`  
- `public static const System.String CSII_PDXMODSPATH`  
- `public static const System.String CSII_ASSEMBLYSEARCHPATH`  
- `public static const System.String CSII_MSCORLIBPATH`  
- `public static const System.String kEntitiesVersion`  

## Properties

- `protected static Colossal.Logging.ILog log { protected get }`  
- `public System.String name { get }`  
- `public Game.UI.Localization.LocalizedString localizedName { get }`  
- `public System.String version { get; protected set }`  
- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  
- `public System.Boolean needDownload { get; protected set }`  
- `public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set }`  
- `public System.Boolean confirmUninstallation { get }`  
- `public System.Boolean canBeInstalled { get }`  
- `public System.Boolean canBeUninstalled { get }`  
- `public System.String installationDirectory { get; set }`  
- `public System.Boolean canChangeInstallationDirectory { get }`  
- `public System.String icon { get }`  
- `public Game.Modding.Toolchain.DeploymentAction availableActions { get }`  
- `public System.Boolean installAvailable { get }`  
- `public System.Boolean uninstallAvailable { get }`  
- `public System.Boolean updateAvailable { get }`  
- `public Game.UI.Localization.LocalizedString description { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  
- `public System.Type[] dependsOnInstallation { get }`  
- `public System.Type[] dependsOnUninstallation { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  
- `public static System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> envVars { get }`  

## Methods

- `internal static <UpdateProcessEnvVarPathValue>g__Add|75_0(System.EnvironmentVariableTarget target, Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass75_0& ) : System.Void`  
- `public static CheckEnvVariables(Game.Modding.Toolchain.IToolchainDependency dependency, System.Boolean checkValue = False) : System.Boolean`  
- `public abstract Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public static GetDownloadSizeAsync(System.String url, System.Threading.CancellationToken token, System.Int32 timeout = 3000) : System.Threading.Tasks.Task<System.Int64>`  
- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public static GetLocalizedState(Game.Modding.Toolchain.IToolchainDependency+State state, System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  
- `public abstract GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public static GetUninstaller(System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName) : Microsoft.Win32.RegistryKey`  
- `public static GetUninstaller(System.String uninstallKeyName, System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName) : Microsoft.Win32.RegistryKey`  
- `public abstract Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public static InstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y) : System.Int32`  
- `public abstract IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public abstract IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public abstract NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public abstract Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public static Refresh(Game.Modding.Toolchain.IToolchainDependency dependency, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public abstract Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public static UninstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y) : System.Int32`  
- `public static UpdateProcessEnvVarPathValue() : System.Void`  

## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

## Nested types

- `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  
- `Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements`  
- `Game.Modding.Toolchain.IToolchainDependency+State`  
- `Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass65_0`  
- `Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass75_0`  
- `Game.Modding.Toolchain.IToolchainDependency+<GetDownloadSizeAsync>d__2`  
- `Game.Modding.Toolchain.IToolchainDependency+<Refresh>d__67`  


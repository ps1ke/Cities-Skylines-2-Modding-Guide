# Game.Modding.Toolchain.IToolchainDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IToolchainDependency
{
    public static const System.String CSII_PATHSET;
    public static const System.String CSII_INSTALLATIONPATH;
    public static const System.String CSII_USERDATAPATH;
    public static const System.String CSII_TOOLPATH;
    public static const System.String CSII_LOCALMODSPATH;
    public static const System.String CSII_UNITYMODPROJECTPATH;
    public static const System.String CSII_UNITYVERSION;
    public static const System.String CSII_ENTITIESVERSION;
    public static const System.String CSII_MODPOSTPROCESSORPATH;
    public static const System.String CSII_MODPUBLISHERPATH;
    public static const System.String CSII_MANAGEDPATH;
    public static const System.String CSII_PDXCACHEPATH;
    public static const System.String CSII_PDXMODSPATH;
    public static const System.String CSII_ASSEMBLYSEARCHPATH;
    public static const System.String CSII_MSCORLIBPATH;
    public static const System.String kEntitiesVersion;

    protected static Colossal.Logging.ILog log { protected get; }
    public System.String name { get; }
    public Game.UI.Localization.LocalizedString localizedName { get; }
    public System.String version { get; protected set; }
    public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
    public System.Boolean needDownload { get; protected set; }
    public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set; }
    public System.Boolean confirmUninstallation { get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public System.String icon { get; }
    public Game.Modding.Toolchain.DeploymentAction availableActions { get; }
    public System.Boolean installAvailable { get; }
    public System.Boolean uninstallAvailable { get; }
    public System.Boolean updateAvailable { get; }
    public Game.UI.Localization.LocalizedString description { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
    public static System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> envVars { get; }

    internal static System.Void <UpdateProcessEnvVarPathValue>g__Add|75_0(System.EnvironmentVariableTarget target, Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass75_0& );
    public static System.Boolean CheckEnvVariables(Game.Modding.Toolchain.IToolchainDependency dependency, System.Boolean checkValue);
    public abstract System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task<System.Int64> GetDownloadSizeAsync(System.String url, System.Threading.CancellationToken token, System.Int32 timeout);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public static Game.UI.Localization.LocalizedString GetLocalizedState(Game.Modding.Toolchain.IToolchainDependency+State state, System.Boolean includeProgress);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    public abstract System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public static Microsoft.Win32.RegistryKey GetUninstaller(System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName);
    public static Microsoft.Win32.RegistryKey GetUninstaller(System.String uninstallKeyName, System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName);
    public abstract System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public static System.Int32 InstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y);
    public abstract System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public abstract System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public abstract System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public abstract System.Threading.Tasks.Task Refresh(System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task Refresh(Game.Modding.Toolchain.IToolchainDependency dependency, System.Threading.CancellationToken token);
    public abstract System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
    public static System.Int32 UninstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y);
    public static System.Void UpdateProcessEnvVarPathValue();
}
```


## Fields

- `public static const System.String CSII_PATHSET`  

```csharp
public static const System.String CSII_PATHSET;
```

- `public static const System.String CSII_INSTALLATIONPATH`  

```csharp
public static const System.String CSII_INSTALLATIONPATH;
```

- `public static const System.String CSII_USERDATAPATH`  

```csharp
public static const System.String CSII_USERDATAPATH;
```

- `public static const System.String CSII_TOOLPATH`  

```csharp
public static const System.String CSII_TOOLPATH;
```

- `public static const System.String CSII_LOCALMODSPATH`  

```csharp
public static const System.String CSII_LOCALMODSPATH;
```

- `public static const System.String CSII_UNITYMODPROJECTPATH`  

```csharp
public static const System.String CSII_UNITYMODPROJECTPATH;
```

- `public static const System.String CSII_UNITYVERSION`  

```csharp
public static const System.String CSII_UNITYVERSION;
```

- `public static const System.String CSII_ENTITIESVERSION`  

```csharp
public static const System.String CSII_ENTITIESVERSION;
```

- `public static const System.String CSII_MODPOSTPROCESSORPATH`  

```csharp
public static const System.String CSII_MODPOSTPROCESSORPATH;
```

- `public static const System.String CSII_MODPUBLISHERPATH`  

```csharp
public static const System.String CSII_MODPUBLISHERPATH;
```

- `public static const System.String CSII_MANAGEDPATH`  

```csharp
public static const System.String CSII_MANAGEDPATH;
```

- `public static const System.String CSII_PDXCACHEPATH`  

```csharp
public static const System.String CSII_PDXCACHEPATH;
```

- `public static const System.String CSII_PDXMODSPATH`  

```csharp
public static const System.String CSII_PDXMODSPATH;
```

- `public static const System.String CSII_ASSEMBLYSEARCHPATH`  

```csharp
public static const System.String CSII_ASSEMBLYSEARCHPATH;
```

- `public static const System.String CSII_MSCORLIBPATH`  

```csharp
public static const System.String CSII_MSCORLIBPATH;
```

- `public static const System.String kEntitiesVersion`  

```csharp
public static const System.String kEntitiesVersion;
```


## Properties

- `protected static Colossal.Logging.ILog log { protected get }`  

```csharp
protected static Colossal.Logging.ILog log { protected get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Game.UI.Localization.LocalizedString localizedName { get }`  

```csharp
public Game.UI.Localization.LocalizedString localizedName { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```

- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  

```csharp
public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
```

- `public System.Boolean needDownload { get; protected set }`  

```csharp
public System.Boolean needDownload { get; protected set; }
```

- `public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set }`  

```csharp
public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set; }
```

- `public System.Boolean confirmUninstallation { get }`  

```csharp
public System.Boolean confirmUninstallation { get; }
```

- `public System.Boolean canBeInstalled { get }`  

```csharp
public System.Boolean canBeInstalled { get; }
```

- `public System.Boolean canBeUninstalled { get }`  

```csharp
public System.Boolean canBeUninstalled { get; }
```

- `public System.String installationDirectory { get; set }`  

```csharp
public System.String installationDirectory { get; set; }
```

- `public System.Boolean canChangeInstallationDirectory { get }`  

```csharp
public System.Boolean canChangeInstallationDirectory { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public Game.Modding.Toolchain.DeploymentAction availableActions { get }`  

```csharp
public Game.Modding.Toolchain.DeploymentAction availableActions { get; }
```

- `public System.Boolean installAvailable { get }`  

```csharp
public System.Boolean installAvailable { get; }
```

- `public System.Boolean uninstallAvailable { get }`  

```csharp
public System.Boolean uninstallAvailable { get; }
```

- `public System.Boolean updateAvailable { get }`  

```csharp
public System.Boolean updateAvailable { get; }
```

- `public Game.UI.Localization.LocalizedString description { get }`  

```csharp
public Game.UI.Localization.LocalizedString description { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```

- `public System.Type[] dependsOnInstallation { get }`  

```csharp
public System.Type[] dependsOnInstallation { get; }
```

- `public System.Type[] dependsOnUninstallation { get }`  

```csharp
public System.Type[] dependsOnUninstallation { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
```

- `public static System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> envVars { get }`  

```csharp
public static System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> envVars { get; }
```


## Methods

- `internal static <UpdateProcessEnvVarPathValue>g__Add|75_0(System.EnvironmentVariableTarget target, Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass75_0& ) : System.Void`  

```csharp
internal static System.Void <UpdateProcessEnvVarPathValue>g__Add|75_0(System.EnvironmentVariableTarget target, Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass75_0& );
```

- `public static CheckEnvVariables(Game.Modding.Toolchain.IToolchainDependency dependency, System.Boolean checkValue = False) : System.Boolean`  

```csharp
public static System.Boolean CheckEnvVariables(Game.Modding.Toolchain.IToolchainDependency dependency, System.Boolean checkValue);
```

- `public abstract Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
```

- `public static GetDownloadSizeAsync(System.String url, System.Threading.CancellationToken token, System.Int32 timeout = 3000) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
public static System.Threading.Tasks.Task<System.Int64> GetDownloadSizeAsync(System.String url, System.Threading.CancellationToken token, System.Int32 timeout);
```

- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
```

- `public static GetLocalizedState(Game.Modding.Toolchain.IToolchainDependency+State state, System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public static Game.UI.Localization.LocalizedString GetLocalizedState(Game.Modding.Toolchain.IToolchainDependency+State state, System.Boolean includeProgress);
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
```

- `public abstract GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
```

- `public static GetUninstaller(System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName) : Microsoft.Win32.RegistryKey`  

```csharp
public static Microsoft.Win32.RegistryKey GetUninstaller(System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName);
```

- `public static GetUninstaller(System.String uninstallKeyName, System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName) : Microsoft.Win32.RegistryKey`  

```csharp
public static Microsoft.Win32.RegistryKey GetUninstaller(System.String uninstallKeyName, System.Collections.Generic.Dictionary<System.String, System.String> check, System.String& keyName);
```

- `public abstract Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
```

- `public static InstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y) : System.Int32`  

```csharp
public static System.Int32 InstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y);
```

- `public abstract IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
```

- `public abstract IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
```

- `public abstract NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
```

- `public abstract Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Refresh(System.Threading.CancellationToken token);
```

- `public static Refresh(Game.Modding.Toolchain.IToolchainDependency dependency, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task Refresh(Game.Modding.Toolchain.IToolchainDependency dependency, System.Threading.CancellationToken token);
```

- `public abstract Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
```

- `public static UninstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y) : System.Int32`  

```csharp
public static System.Int32 UninstallSorting(Game.Modding.Toolchain.IToolchainDependency x, Game.Modding.Toolchain.IToolchainDependency y);
```

- `public static UpdateProcessEnvVarPathValue() : System.Void`  

```csharp
public static System.Void UpdateProcessEnvVarPathValue();
```


## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

```csharp
public event Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```


## Nested types

- `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  
- `Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements`  
- `Game.Modding.Toolchain.IToolchainDependency+State`  
- `Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass65_0`  
- `Game.Modding.Toolchain.IToolchainDependency+<>c__DisplayClass75_0`  
- `Game.Modding.Toolchain.IToolchainDependency+<GetDownloadSizeAsync>d__2`  
- `Game.Modding.Toolchain.IToolchainDependency+<Refresh>d__67`  


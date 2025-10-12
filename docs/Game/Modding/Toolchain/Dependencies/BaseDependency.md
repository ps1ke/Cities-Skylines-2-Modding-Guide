# Game.Modding.Toolchain.Dependencies.BaseDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private Game.Modding.Toolchain.IToolchainDependency+State m_State`  
- `private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress`  
- `private System.String <version>k__BackingField`  
- `private System.Boolean <needDownload>k__BackingField`  
- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField`  
- `private System.String <installationDirectory>k__BackingField`  

## Properties

- `public Game.UI.Localization.LocalizedString localizedName { get }`  
- `public System.String name { get }`  
- `public System.String version { get; protected set }`  
- `private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set }`  
- `public System.String icon { get }`  
- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  
- `public System.Boolean needDownload { get; protected set }`  
- `private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set }`  
- `public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set }`  
- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set }`  
- `public System.Boolean confirmUninstallation { get }`  
- `public System.Boolean canBeInstalled { get }`  
- `public System.Boolean canBeUninstalled { get }`  
- `public System.Boolean canChangeInstallationDirectory { get }`  
- `public System.String installationDirectory { get; set }`  
- `public Game.UI.Localization.LocalizedString description { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  
- `public System.Type[] dependsOnInstallation { get }`  
- `public System.Type[] dependsOnUninstallation { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  

## Constructors

- `protected BaseDependency()`  

## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `protected static Download(Game.Modding.Toolchain.Dependencies.BaseDependency dependency, System.Threading.CancellationToken token, System.String url, System.String pathOnDisk, System.String detail) : System.Threading.Tasks.Task`  
- `public virtual GetHashCode() : System.Int32`  
- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual ToString() : System.String`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.BaseDependency+<>c__DisplayClass72_0`  
- `Game.Modding.Toolchain.Dependencies.BaseDependency+<Download>d__72`  
- `Game.Modding.Toolchain.Dependencies.BaseDependency+<get_envVariables>d__67`  


# Game.Modding.Toolchain.Dependencies.MainDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress`  
- `private System.String <Game.Modding.Toolchain.IToolchainDependency.version>k__BackingField`  
- `private System.Boolean <Game.Modding.Toolchain.IToolchainDependency.needDownload>k__BackingField`  
- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <Game.Modding.Toolchain.IToolchainDependency.spaceRequirements>k__BackingField`  
- `private readonly System.Boolean <confirmUninstallation>k__BackingField`  
- `private readonly System.Boolean <canBeInstalled>k__BackingField`  
- `private readonly System.Boolean <canBeUninstalled>k__BackingField`  
- `private System.String <installationDirectory>k__BackingField`  
- `private readonly Game.UI.Localization.LocalizedString <installDescr>k__BackingField`  
- `private readonly Game.UI.Localization.LocalizedString <uninstallDescr>k__BackingField`  
- `private readonly Game.UI.Localization.LocalizedString <uninstallMessage>k__BackingField`  
- `private readonly System.Type[] <dependsOnInstallation>k__BackingField`  
- `private readonly System.Type[] <dependsOnUninstallation>k__BackingField`  

## Properties

- `public System.String name { get }`  
- `public Game.UI.Localization.LocalizedString localizedName { get }`  
- `public Game.Modding.Toolchain.DeploymentAction availableActions { get }`  
- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  
- `private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set }`  
- `private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set }`  
- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set }`  
- `private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get }`  
- `public System.String icon { get }`  
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

## Constructors

- `public MainDependency()`  

## Methods

- `public Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.MainDependency+<Game-Modding-Toolchain-IToolchainDependency-get_envVariables>d__27`  


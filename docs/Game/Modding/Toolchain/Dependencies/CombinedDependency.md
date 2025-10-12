# Game.Modding.Toolchain.Dependencies.CombinedDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private Game.Modding.Toolchain.IToolchainDependency+State m_State`  
- `private System.Version m_Version`  
- `private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress`  
- `private System.String <version>k__BackingField`  
- `private System.String <installationDirectory>k__BackingField`  
- `private System.Boolean <needDownload>k__BackingField`  
- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField`  

## Properties

- `public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get }`  
- `protected System.Boolean isAsync { protected get }`  
- `public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get }`  
- `public System.String name { get }`  
- `public Game.UI.Localization.LocalizedString localizedName { get }`  
- `public System.String version { get; protected set }`  
- `private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set }`  
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
- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  
- `public System.Boolean needDownload { get; protected set }`  
- `private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set }`  
- `public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set }`  
- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set }`  
- `private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get }`  
- `public System.Type[] dependsOnInstallation { get }`  
- `public System.Type[] dependsOnUninstallation { get }`  

## Constructors

- `protected CombinedDependency()`  

## Methods

- `public Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private GetCombinedResult(System.Threading.CancellationToken token, System.Func<Game.Modding.Toolchain.IToolchainDependency, System.Threading.CancellationToken, System.Threading.Tasks.Task<System.Boolean>> getTaskPredicate) : System.Threading.Tasks.Task<System.Boolean>`  
- `private GetCombinedResult(Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType combineType, System.Threading.CancellationToken token, System.Func<Game.Modding.Toolchain.IToolchainDependency, System.Threading.CancellationToken, System.Threading.Tasks.Task> getTaskPredicate) : System.Threading.Tasks.Task`  
- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<>c__DisplayClass68_0`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<>c__DisplayClass69_0`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<Game-Modding-Toolchain-IToolchainDependency-get_envVariables>d__63`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<GetCombinedResult>d__68`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<GetCombinedResult>d__69`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<Refresh>d__70`  


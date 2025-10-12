# Game.Modding.Toolchain.ToolchainDependencyManager

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency>`, `System.Collections.IEnumerable`  

## Fields

- `private System.Boolean <isInProgress>k__BackingField`  
- `private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged`  
- `private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies`  
- `public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State`  
- `public static readonly System.String kUserToolingPath`  
- `public static readonly System.String kGameToolingPath`  
- `public static readonly Colossal.Logging.ILog log`  
- `public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency`  
- `private static const System.String kToolchain`  
- `private static const System.String kInstallingToolchain`  
- `private static const System.String kUninstallingToolchain`  
- `private static const System.String kInstallingToolchainFailed`  
- `private static const System.String kUninstallingToolchainFailed`  
- `private static const System.String kInstalledKey`  
- `private static const System.String kInstalledValue`  

## Properties

- `public System.Boolean isInProgress { get; private set }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get }`  
- `public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set }`  
- `private static System.Boolean isInstalled { private get; private set }`  

## Constructors

- `public ToolchainDependencyManager()`  

## Methods

- `private <GetCurrentState>b__25_0() : System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState>`  
- `internal static <Install>g__ProcessException|33_1(System.Exception ex) : System.Void`  
- `internal static <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex) : System.Void`  
- `internal static <Install>g__SetFailedNotification|33_2() : System.Void`  
- `internal static <Uninstall>g__ProcessException|34_1(System.Exception ex) : System.Void`  
- `internal static <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex) : System.Void`  
- `internal static <Uninstall>g__SetFailedNotification|34_2() : System.Void`  
- `private static CheckFreeSpace(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> requirements, System.String& message) : System.Boolean`  
- `public GetCurrentState() : System.Threading.Tasks.Task<Game.Modding.Toolchain.ToolchainDependencyManager+State>`  
- `private GetDeploymentState(System.Threading.CancellationToken token, System.Boolean forceRefresh = False, System.Boolean throwException = True) : System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState>`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.Modding.Toolchain.IToolchainDependency>`  
- `public Install(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToInstall, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private static OpenOptions() : System.Void`  
- `public Register<T>() : System.Void`  
- `private SetProgress(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State dependencyState) : System.Void`  
- `private static ShowErrorDialog(Game.UI.Localization.LocalizedString message, System.Exception ex = null) : System.Void`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public Uninstall(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToUninstall, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Events

- `OnStateChanged` : `System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State>`  

## Nested types

- `Game.Modding.Toolchain.ToolchainDependencyManager+UserEnvironmentVariableManager`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+State`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<<GetCurrentState>b__25_0>d`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<>c`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<>c__DisplayClass34_0`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<>c__DisplayClass38_0`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<GetCurrentState>d__25`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<GetDeploymentState>d__38`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<Install>d__33`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<Uninstall>d__34`  


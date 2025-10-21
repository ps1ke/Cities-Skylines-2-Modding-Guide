# Game.Modding.Toolchain.ToolchainDependencyManager

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class ToolchainDependencyManager : System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency>, System.Collections.IEnumerable
{
    private System.Boolean <isInProgress>k__BackingField;
    private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged;
    private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies;
    public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State;
    public static readonly System.String kUserToolingPath;
    public static readonly System.String kGameToolingPath;
    public static readonly Colossal.Logging.ILog log;
    public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency;
    private static const System.String kToolchain;
    private static const System.String kInstallingToolchain;
    private static const System.String kUninstallingToolchain;
    private static const System.String kInstallingToolchainFailed;
    private static const System.String kUninstallingToolchainFailed;
    private static const System.String kInstalledKey;
    private static const System.String kInstalledValue;

    public System.Boolean isInProgress { get; private set; }
    public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
    public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set; }
    private static System.Boolean isInstalled { private get; private set; }

    public ToolchainDependencyManager();

    private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> <GetCurrentState>b__25_0();
    internal static System.Void <Install>g__ProcessException|33_1(System.Exception ex);
    internal static System.Void <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex);
    internal static System.Void <Install>g__SetFailedNotification|33_2();
    internal static System.Void <Uninstall>g__ProcessException|34_1(System.Exception ex);
    internal static System.Void <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex);
    internal static System.Void <Uninstall>g__SetFailedNotification|34_2();
    private static System.Boolean CheckFreeSpace(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> requirements, System.String& message);
    public System.Threading.Tasks.Task<Game.Modding.Toolchain.ToolchainDependencyManager+State> GetCurrentState();
    private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> GetDeploymentState(System.Threading.CancellationToken token, System.Boolean forceRefresh, System.Boolean throwException);
    public System.Collections.Generic.IEnumerator<Game.Modding.Toolchain.IToolchainDependency> GetEnumerator();
    public System.Threading.Tasks.Task Install(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToInstall, System.Threading.CancellationToken token);
    private static System.Void OpenOptions();
    public System.Void Register<T>();
    private System.Void SetProgress(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State dependencyState);
    private static System.Void ShowErrorDialog(Game.UI.Localization.LocalizedString message, System.Exception ex);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Threading.Tasks.Task Uninstall(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToUninstall, System.Threading.CancellationToken token);
}
```


## Fields

- `private System.Boolean <isInProgress>k__BackingField`  

```csharp
private System.Boolean <isInProgress>k__BackingField;
```

- `private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged`  

```csharp
private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged;
```

- `private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies`  

```csharp
private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies;
```

- `public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State;
```

- `public static readonly System.String kUserToolingPath`  

```csharp
public static readonly System.String kUserToolingPath;
```

- `public static readonly System.String kGameToolingPath`  

```csharp
public static readonly System.String kGameToolingPath;
```

- `public static readonly Colossal.Logging.ILog log`  

```csharp
public static readonly Colossal.Logging.ILog log;
```

- `public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency`  

```csharp
public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency;
```

- `private static const System.String kToolchain`  

```csharp
private static const System.String kToolchain;
```

- `private static const System.String kInstallingToolchain`  

```csharp
private static const System.String kInstallingToolchain;
```

- `private static const System.String kUninstallingToolchain`  

```csharp
private static const System.String kUninstallingToolchain;
```

- `private static const System.String kInstallingToolchainFailed`  

```csharp
private static const System.String kInstallingToolchainFailed;
```

- `private static const System.String kUninstallingToolchainFailed`  

```csharp
private static const System.String kUninstallingToolchainFailed;
```

- `private static const System.String kInstalledKey`  

```csharp
private static const System.String kInstalledKey;
```

- `private static const System.String kInstalledValue`  

```csharp
private static const System.String kInstalledValue;
```


## Properties

- `public System.Boolean isInProgress { get; private set }`  

```csharp
public System.Boolean isInProgress { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
```

- `public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set }`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set; }
```

- `private static System.Boolean isInstalled { private get; private set }`  

```csharp
private static System.Boolean isInstalled { private get; private set; }
```


## Constructors

- `public ToolchainDependencyManager()`  

```csharp
public ToolchainDependencyManager();
```


## Methods

- `private <GetCurrentState>b__25_0() : System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState>`  

```csharp
private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> <GetCurrentState>b__25_0();
```

- `internal static <Install>g__ProcessException|33_1(System.Exception ex) : System.Void`  

```csharp
internal static System.Void <Install>g__ProcessException|33_1(System.Exception ex);
```

- `internal static <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex) : System.Void`  

```csharp
internal static System.Void <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex);
```

- `internal static <Install>g__SetFailedNotification|33_2() : System.Void`  

```csharp
internal static System.Void <Install>g__SetFailedNotification|33_2();
```

- `internal static <Uninstall>g__ProcessException|34_1(System.Exception ex) : System.Void`  

```csharp
internal static System.Void <Uninstall>g__ProcessException|34_1(System.Exception ex);
```

- `internal static <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex) : System.Void`  

```csharp
internal static System.Void <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex);
```

- `internal static <Uninstall>g__SetFailedNotification|34_2() : System.Void`  

```csharp
internal static System.Void <Uninstall>g__SetFailedNotification|34_2();
```

- `private static CheckFreeSpace(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> requirements, System.String& message) : System.Boolean`  

```csharp
private static System.Boolean CheckFreeSpace(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> requirements, System.String& message);
```

- `public GetCurrentState() : System.Threading.Tasks.Task<Game.Modding.Toolchain.ToolchainDependencyManager+State>`  

```csharp
public System.Threading.Tasks.Task<Game.Modding.Toolchain.ToolchainDependencyManager+State> GetCurrentState();
```

- `private GetDeploymentState(System.Threading.CancellationToken token, System.Boolean forceRefresh = False, System.Boolean throwException = True) : System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState>`  

```csharp
private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> GetDeploymentState(System.Threading.CancellationToken token, System.Boolean forceRefresh, System.Boolean throwException);
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.Modding.Toolchain.IToolchainDependency>`  

```csharp
public System.Collections.Generic.IEnumerator<Game.Modding.Toolchain.IToolchainDependency> GetEnumerator();
```

- `public Install(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToInstall, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Install(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToInstall, System.Threading.CancellationToken token);
```

- `private static OpenOptions() : System.Void`  

```csharp
private static System.Void OpenOptions();
```

- `public Register<T>() : System.Void`  

```csharp
public System.Void Register<T>();
```

- `private SetProgress(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State dependencyState) : System.Void`  

```csharp
private System.Void SetProgress(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State dependencyState);
```

- `private static ShowErrorDialog(Game.UI.Localization.LocalizedString message, System.Exception ex = null) : System.Void`  

```csharp
private static System.Void ShowErrorDialog(Game.UI.Localization.LocalizedString message, System.Exception ex);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public Uninstall(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToUninstall, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Uninstall(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToUninstall, System.Threading.CancellationToken token);
```


## Events

- `OnStateChanged` : `System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State>`  

```csharp
public event System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged;
```


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


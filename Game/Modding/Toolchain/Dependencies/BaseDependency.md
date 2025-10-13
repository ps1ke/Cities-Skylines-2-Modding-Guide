# Game.Modding.Toolchain.Dependencies.BaseDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public abstract class BaseDependency : Game.Modding.Toolchain.IToolchainDependency
{
    private Game.Modding.Toolchain.IToolchainDependency+State m_State;
    private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
    private System.String <version>k__BackingField;
    private System.Boolean <needDownload>k__BackingField;
    private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField;
    private System.String <installationDirectory>k__BackingField;

    public Game.UI.Localization.LocalizedString localizedName { get; }
    public System.String name { get; }
    public System.String version { get; protected set; }
    private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set; }
    public System.String icon { get; }
    public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
    public System.Boolean needDownload { get; protected set; }
    private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set; }
    public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set; }
    private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set; }
    public System.Boolean confirmUninstallation { get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public System.String installationDirectory { get; set; }
    public Game.UI.Localization.LocalizedString description { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }

    protected BaseDependency();

    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    protected static System.Threading.Tasks.Task Download(Game.Modding.Toolchain.Dependencies.BaseDependency dependency, System.Threading.CancellationToken token, System.String url, System.String pathOnDisk, System.String detail);
    public virtual System.Int32 GetHashCode();
    public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Refresh(System.Threading.CancellationToken token);
    public virtual System.String ToString();
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private Game.Modding.Toolchain.IToolchainDependency+State m_State`  

```csharp
private Game.Modding.Toolchain.IToolchainDependency+State m_State;
```

- `private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress`  

```csharp
private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```

- `private System.String <version>k__BackingField`  

```csharp
private System.String <version>k__BackingField;
```

- `private System.Boolean <needDownload>k__BackingField`  

```csharp
private System.Boolean <needDownload>k__BackingField;
```

- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField;
```

- `private System.String <installationDirectory>k__BackingField`  

```csharp
private System.String <installationDirectory>k__BackingField;
```


## Properties

- `public Game.UI.Localization.LocalizedString localizedName { get }`  

```csharp
public Game.UI.Localization.LocalizedString localizedName { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```

- `private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set }`  

```csharp
private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  

```csharp
public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
```

- `public System.Boolean needDownload { get; protected set }`  

```csharp
public System.Boolean needDownload { get; protected set; }
```

- `private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set }`  

```csharp
private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set; }
```

- `public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set }`  

```csharp
public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set; }
```

- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set; }
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

- `public System.Boolean canChangeInstallationDirectory { get }`  

```csharp
public System.Boolean canChangeInstallationDirectory { get; }
```

- `public System.String installationDirectory { get; set }`  

```csharp
public System.String installationDirectory { get; set; }
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


## Constructors

- `protected BaseDependency()`  

```csharp
protected BaseDependency();
```


## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
```

- `protected static Download(Game.Modding.Toolchain.Dependencies.BaseDependency dependency, System.Threading.CancellationToken token, System.String url, System.String pathOnDisk, System.String detail) : System.Threading.Tasks.Task`  

```csharp
protected static System.Threading.Tasks.Task Download(Game.Modding.Toolchain.Dependencies.BaseDependency dependency, System.Threading.CancellationToken token, System.String url, System.String pathOnDisk, System.String detail);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
```

- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
```

- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
```

- `public virtual Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Refresh(System.Threading.CancellationToken token);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
```


## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

```csharp
public event Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.BaseDependency+<>c__DisplayClass72_0`  
- `Game.Modding.Toolchain.Dependencies.BaseDependency+<Download>d__72`  
- `Game.Modding.Toolchain.Dependencies.BaseDependency+<get_envVariables>d__67`  


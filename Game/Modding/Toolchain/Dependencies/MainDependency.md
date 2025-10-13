# Game.Modding.Toolchain.Dependencies.MainDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class MainDependency : Game.Modding.Toolchain.IToolchainDependency
{
    private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
    private System.String <Game.Modding.Toolchain.IToolchainDependency.version>k__BackingField;
    private System.Boolean <Game.Modding.Toolchain.IToolchainDependency.needDownload>k__BackingField;
    private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <Game.Modding.Toolchain.IToolchainDependency.spaceRequirements>k__BackingField;
    private readonly System.Boolean <confirmUninstallation>k__BackingField;
    private readonly System.Boolean <canBeInstalled>k__BackingField;
    private readonly System.Boolean <canBeUninstalled>k__BackingField;
    private System.String <installationDirectory>k__BackingField;
    private readonly Game.UI.Localization.LocalizedString <installDescr>k__BackingField;
    private readonly Game.UI.Localization.LocalizedString <uninstallDescr>k__BackingField;
    private readonly Game.UI.Localization.LocalizedString <uninstallMessage>k__BackingField;
    private readonly System.Type[] <dependsOnInstallation>k__BackingField;
    private readonly System.Type[] <dependsOnUninstallation>k__BackingField;

    public System.String name { get; }
    public Game.UI.Localization.LocalizedString localizedName { get; }
    public Game.Modding.Toolchain.DeploymentAction availableActions { get; }
    public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
    private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set; }
    private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set; }
    private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set; }
    private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get; }
    public System.String icon { get; }
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

    public MainDependency();

    public System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Int32 GetHashCode();
    public Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task Refresh(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress`  

```csharp
private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```

- `private System.String <Game.Modding.Toolchain.IToolchainDependency.version>k__BackingField`  

```csharp
private System.String <Game.Modding.Toolchain.IToolchainDependency.version>k__BackingField;
```

- `private System.Boolean <Game.Modding.Toolchain.IToolchainDependency.needDownload>k__BackingField`  

```csharp
private System.Boolean <Game.Modding.Toolchain.IToolchainDependency.needDownload>k__BackingField;
```

- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <Game.Modding.Toolchain.IToolchainDependency.spaceRequirements>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <Game.Modding.Toolchain.IToolchainDependency.spaceRequirements>k__BackingField;
```

- `private readonly System.Boolean <confirmUninstallation>k__BackingField`  

```csharp
private readonly System.Boolean <confirmUninstallation>k__BackingField;
```

- `private readonly System.Boolean <canBeInstalled>k__BackingField`  

```csharp
private readonly System.Boolean <canBeInstalled>k__BackingField;
```

- `private readonly System.Boolean <canBeUninstalled>k__BackingField`  

```csharp
private readonly System.Boolean <canBeUninstalled>k__BackingField;
```

- `private System.String <installationDirectory>k__BackingField`  

```csharp
private System.String <installationDirectory>k__BackingField;
```

- `private readonly Game.UI.Localization.LocalizedString <installDescr>k__BackingField`  

```csharp
private readonly Game.UI.Localization.LocalizedString <installDescr>k__BackingField;
```

- `private readonly Game.UI.Localization.LocalizedString <uninstallDescr>k__BackingField`  

```csharp
private readonly Game.UI.Localization.LocalizedString <uninstallDescr>k__BackingField;
```

- `private readonly Game.UI.Localization.LocalizedString <uninstallMessage>k__BackingField`  

```csharp
private readonly Game.UI.Localization.LocalizedString <uninstallMessage>k__BackingField;
```

- `private readonly System.Type[] <dependsOnInstallation>k__BackingField`  

```csharp
private readonly System.Type[] <dependsOnInstallation>k__BackingField;
```

- `private readonly System.Type[] <dependsOnUninstallation>k__BackingField`  

```csharp
private readonly System.Type[] <dependsOnUninstallation>k__BackingField;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Game.UI.Localization.LocalizedString localizedName { get }`  

```csharp
public Game.UI.Localization.LocalizedString localizedName { get; }
```

- `public Game.Modding.Toolchain.DeploymentAction availableActions { get }`  

```csharp
public Game.Modding.Toolchain.DeploymentAction availableActions { get; }
```

- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  

```csharp
public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
```

- `private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set }`  

```csharp
private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set; }
```

- `private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set }`  

```csharp
private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set; }
```

- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set; }
```

- `private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
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


## Constructors

- `public MainDependency()`  

```csharp
public MainDependency();
```


## Methods

- `public Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Download(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return ToolchainDeployment.dependencyManager.cachedState.GetHashCode();
	}
```

- `public GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public LocalizedString GetLocalizedState(bool includeProgress)
	{
		return ToolchainDeployment.dependencyManager.cachedState.GetLocalizedState(includeProgress);
	}
```

- `public GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public Task<List<IToolchainDependency.DiskSpaceRequirements>> GetRequiredDiskSpace(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Install(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> IsInstalled(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> IsUpToDate(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> NeedDownload(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Refresh(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```

- `public Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Uninstall(CancellationToken token)
	{
		throw new NotSupportedException();
	}
```


## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

```csharp
public event Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.MainDependency+<Game-Modding-Toolchain-IToolchainDependency-get_envVariables>d__27`  


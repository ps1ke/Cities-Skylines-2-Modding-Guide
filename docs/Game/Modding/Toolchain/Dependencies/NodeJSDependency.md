# Game.Modding.Toolchain.Dependencies.NodeJSDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class NodeJSDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private System.Nullable<System.Int64> m_DownloadSize;
    private System.String m_InstallationDirectory;
    public static readonly System.String kNodeJSVersion;
    public static readonly System.String kMinNodeJSVersion;
    public static readonly System.String kNodeJSInstallerUrl;
    public static readonly System.String kDefaultInstallationDirectory;
    public static readonly System.String kInstallationFolder;

    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean confirmUninstallation { get; }
    public System.String installerPath { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.String version { get; protected set; }

    public NodeJSDependency();

    private System.Void <>n__0(System.String value);
    private System.String <>n__1();
    private System.Threading.Tasks.Task<System.String> <get_version>b__34_0();
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Int64> GetDotNetInstallerSize(System.Threading.CancellationToken token);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    private System.Threading.Tasks.Task<System.String> GetNodeVersion(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private System.Nullable<System.Int64> m_DownloadSize`  

```csharp
private System.Nullable<System.Int64> m_DownloadSize;
```

- `private System.String m_InstallationDirectory`  

```csharp
private System.String m_InstallationDirectory;
```

- `public static readonly System.String kNodeJSVersion`  

```csharp
public static readonly System.String kNodeJSVersion;
```

- `public static readonly System.String kMinNodeJSVersion`  

```csharp
public static readonly System.String kMinNodeJSVersion;
```

- `public static readonly System.String kNodeJSInstallerUrl`  

```csharp
public static readonly System.String kNodeJSInstallerUrl;
```

- `public static readonly System.String kDefaultInstallationDirectory`  

```csharp
public static readonly System.String kDefaultInstallationDirectory;
```

- `public static readonly System.String kInstallationFolder`  

```csharp
public static readonly System.String kInstallationFolder;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public System.Boolean confirmUninstallation { get }`  

```csharp
public System.Boolean confirmUninstallation { get; }
```

- `public System.String installerPath { get }`  

```csharp
public System.String installerPath { get; }
```

- `public System.String installationDirectory { get; set }`  

```csharp
public System.String installationDirectory { get; set; }
```

- `public System.Boolean canChangeInstallationDirectory { get }`  

```csharp
public System.Boolean canChangeInstallationDirectory { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```


## Constructors

- `public NodeJSDependency()`  

```csharp
public NodeJSDependency();
```


## Methods

- `private <>n__0(System.String value) : System.Void`  

```csharp
private System.Void <>n__0(System.String value);
```

- `private <>n__1() : System.String`  

```csharp
private System.String <>n__1();
```

- `private <get_version>b__34_0() : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> <get_version>b__34_0();
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
```

- `private GetDotNetInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
private System.Threading.Tasks.Task<System.Int64> GetDotNetInstallerSize(System.Threading.CancellationToken token);
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
```

- `private GetNodeVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> GetNodeVersion(System.Threading.CancellationToken token);
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

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<<get_version>b__34_0>d`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<>c__DisplayClass36_0`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<GetDotNetInstallerSize>d__28`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<GetNodeVersion>d__36`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<GetRequiredDiskSpace>d__29`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<Install>d__31`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<IsInstalled>d__25`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<IsUpToDate>d__26`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<NeedDownload>d__27`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<Uninstall>d__32`  


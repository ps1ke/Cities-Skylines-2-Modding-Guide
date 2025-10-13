# Game.Modding.Toolchain.Dependencies.DotNetDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class DotNetDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private System.Nullable<System.Int64> m_DownloadSize;
    private System.String m_InstallationDirectory;
    private static readonly System.String sDotNetVersion;
    public static readonly System.String sDotNetInstallerUrl;
    public static readonly System.String kDefaultInstallationDirectory;
    public static readonly System.String kInstallationFolder;
    private static const System.String kDependencyName;

    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean confirmUninstallation { get; }
    public System.String installerPath { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.String version { get; protected set; }

    public DotNetDependency();

    private System.Void <>n__0(System.String value);
    private System.String <>n__1();
    private System.Threading.Tasks.Task<System.String> <get_version>b__33_0();
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Int64> GetDotNetInstallerSize(System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task<System.Version> GetDotnetVersion(System.Threading.CancellationToken token);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.String> GetVersion(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
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

- `private static readonly System.String sDotNetVersion`  

```csharp
private static readonly System.String sDotNetVersion;
```

- `public static readonly System.String sDotNetInstallerUrl`  

```csharp
public static readonly System.String sDotNetInstallerUrl;
```

- `public static readonly System.String kDefaultInstallationDirectory`  

```csharp
public static readonly System.String kDefaultInstallationDirectory;
```

- `public static readonly System.String kInstallationFolder`  

```csharp
public static readonly System.String kInstallationFolder;
```

- `private static const System.String kDependencyName`  

```csharp
private static const System.String kDependencyName;
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

- `public DotNetDependency()`  

```csharp
public DotNetDependency();
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

- `private <get_version>b__33_0() : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> <get_version>b__33_0();
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
```

- `private GetDotNetInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
private System.Threading.Tasks.Task<System.Int64> GetDotNetInstallerSize(System.Threading.CancellationToken token);
```

- `public static GetDotnetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Version>`  

```csharp
public static System.Threading.Tasks.Task<System.Version> GetDotnetVersion(System.Threading.CancellationToken token);
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
```

- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
```

- `private GetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> GetVersion(System.Threading.CancellationToken token);
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
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

- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<<get_version>b__33_0>d`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<>c__DisplayClass37_0`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetDotNetInstallerSize>d__27`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetDotnetVersion>d__37`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetRequiredDiskSpace>d__28`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetVersion>d__35`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<Install>d__30`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<IsInstalled>d__25`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<NeedDownload>d__26`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<Uninstall>d__31`  


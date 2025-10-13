# Game.Modding.Toolchain.Dependencies.UnityDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class UnityDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private System.Nullable<System.Int64> m_DownloadSize;
    private System.String m_InstallationDirectory;
    public static readonly System.String sUnityVersion;
    public static readonly System.String kDefaultInstallationDirectory;
    public static readonly System.String kInstallationFolder;
    private static System.String sUnityPath;
    public static const System.String kUnityInstallerUrl;

    public System.String name { get; }
    public System.String icon { get; }
    public System.String version { get; protected set; }
    public static System.String unityPath { get; }
    public static System.String unityExe { get; }
    public static System.String unityUninstallerExe { get; }
    public System.String installerPath { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public System.Boolean confirmUninstallation { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }

    public UnityDependency();

    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Int64> GetUnityInstallerSize(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    private static System.Boolean TryGetParentPath(System.String path, System.Int32 depth, System.String& parentPath);
    private static System.Boolean TryGetRegistryKeyValue(Microsoft.Win32.RegistryKey registry, System.String path, System.String key, System.String& value);
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

- `public static readonly System.String sUnityVersion`  

```csharp
public static readonly System.String sUnityVersion;
```

- `public static readonly System.String kDefaultInstallationDirectory`  

```csharp
public static readonly System.String kDefaultInstallationDirectory;
```

- `public static readonly System.String kInstallationFolder`  

```csharp
public static readonly System.String kInstallationFolder;
```

- `private static System.String sUnityPath`  

```csharp
private static System.String sUnityPath;
```

- `public static const System.String kUnityInstallerUrl`  

```csharp
public static const System.String kUnityInstallerUrl;
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

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```

- `public static System.String unityPath { get }`  

```csharp
public static System.String unityPath { get; }
```

- `public static System.String unityExe { get }`  

```csharp
public static System.String unityExe { get; }
```

- `public static System.String unityUninstallerExe { get }`  

```csharp
public static System.String unityUninstallerExe { get; }
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

- `public System.Boolean confirmUninstallation { get }`  

```csharp
public System.Boolean confirmUninstallation { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```


## Constructors

- `public UnityDependency()`  

```csharp
public UnityDependency();
```


## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
```

- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
```

- `private GetUnityInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
private System.Threading.Tasks.Task<System.Int64> GetUnityInstallerSize(System.Threading.CancellationToken token);
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

- `private static TryGetParentPath(System.String path, System.Int32 depth, System.String& parentPath) : System.Boolean`  

```csharp
private static System.Boolean TryGetParentPath(System.String path, System.Int32 depth, System.String& parentPath);
```

- `private static TryGetRegistryKeyValue(Microsoft.Win32.RegistryKey registry, System.String path, System.String key, System.String& value) : System.Boolean`  

```csharp
private static System.Boolean TryGetRegistryKeyValue(Microsoft.Win32.RegistryKey registry, System.String path, System.String key, System.String& value);
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.UnityDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<>c__DisplayClass41_0`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<GetRequiredDiskSpace>d__38`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<GetUnityInstallerSize>d__37`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<Install>d__40`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<NeedDownload>d__36`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<Uninstall>d__41`  


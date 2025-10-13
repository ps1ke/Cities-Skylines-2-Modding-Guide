# Game.Modding.Toolchain.Dependencies.UnityModProjectDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class UnityModProjectDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    public static readonly System.String kProjectUnzipPath;
    public static readonly System.String kProjectZipPath;
    public static readonly System.String kModProjectsUnityVersionPath;
    public static readonly System.String kModProjectsVersionPath;
    public static readonly System.String kModProjectPackages;
    public static const System.String kProjectName;
    public static const System.String kProjectVersionTxt;
    public static const System.String kProjectSettingsAsset;
    public static const System.String kProjectPackageManifest;
    public static const System.String kProjectPackageLock;

    public static System.Boolean isUnityOpened { get; }
    public System.String name { get; }
    public System.String icon { get; }
    public System.String version { get; protected set; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
    public System.Type[] dependsOnInstallation { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }

    public UnityModProjectDependency();

    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    private static System.Boolean IsUnityOpenWithModsProject(System.String projectPath);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    private static Colossal.Version ReadUnityProjectVersion(System.String path);
    private static Colossal.Version ReadYAMLVersion(System.Collections.Generic.IEnumerable<System.String> lines);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `public static readonly System.String kProjectUnzipPath`  

```csharp
public static readonly System.String kProjectUnzipPath;
```

- `public static readonly System.String kProjectZipPath`  

```csharp
public static readonly System.String kProjectZipPath;
```

- `public static readonly System.String kModProjectsUnityVersionPath`  

```csharp
public static readonly System.String kModProjectsUnityVersionPath;
```

- `public static readonly System.String kModProjectsVersionPath`  

```csharp
public static readonly System.String kModProjectsVersionPath;
```

- `public static readonly System.String kModProjectPackages`  

```csharp
public static readonly System.String kModProjectPackages;
```

- `public static const System.String kProjectName`  

```csharp
public static const System.String kProjectName;
```

- `public static const System.String kProjectVersionTxt`  

```csharp
public static const System.String kProjectVersionTxt;
```

- `public static const System.String kProjectSettingsAsset`  

```csharp
public static const System.String kProjectSettingsAsset;
```

- `public static const System.String kProjectPackageManifest`  

```csharp
public static const System.String kProjectPackageManifest;
```

- `public static const System.String kProjectPackageLock`  

```csharp
public static const System.String kProjectPackageLock;
```


## Properties

- `public static System.Boolean isUnityOpened { get }`  

```csharp
public static System.Boolean isUnityOpened { get; }
```

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

- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
```

- `public System.Type[] dependsOnInstallation { get }`  

```csharp
public System.Type[] dependsOnInstallation { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```


## Constructors

- `public UnityModProjectDependency()`  

```csharp
public UnityModProjectDependency();
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

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
```

- `private static IsUnityOpenWithModsProject(System.String projectPath) : System.Boolean`  

```csharp
private static System.Boolean IsUnityOpenWithModsProject(System.String projectPath);
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
```

- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
```

- `private static ReadUnityProjectVersion(System.String path) : Colossal.Version`  

```csharp
private static Colossal.Version ReadUnityProjectVersion(System.String path);
```

- `private static ReadYAMLVersion(System.Collections.Generic.IEnumerable<System.String> lines) : Colossal.Version`  

```csharp
private static Colossal.Version ReadYAMLVersion(System.Collections.Generic.IEnumerable<System.String> lines);
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c__DisplayClass29_0`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c__DisplayClass34_0`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<Install>d__29`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<Uninstall>d__30`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<get_envVariables>d__20`  


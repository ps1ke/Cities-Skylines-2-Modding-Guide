# Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class ProjectTemplateDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private static readonly System.String kPropsFileSource;
    private static readonly System.String kTargetsFileSource;
    private static readonly System.String kPropsFileDeploy;
    private static readonly System.String kTargetsFileDeploy;
    private static readonly System.String kTemplatePackageFile;
    private static readonly System.String kTemplatePackageSource;
    private static readonly System.String kTemplatePackageInstallation;
    private static const System.String kProjectName;
    private static const System.String kPropsFile;
    private static const System.String kTargetsFile;
    private static const System.String kTemplatePackageId;
    private static const System.String kTemplateId;

    public System.String name { get; }
    public System.String icon { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }

    public ProjectTemplateDependency();

    internal static System.UInt64 <IsUpToDate>g__CalculateCache|25_0(System.String file);
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private static readonly System.String kPropsFileSource`  

```csharp
private static readonly System.String kPropsFileSource;
```

- `private static readonly System.String kTargetsFileSource`  

```csharp
private static readonly System.String kTargetsFileSource;
```

- `private static readonly System.String kPropsFileDeploy`  

```csharp
private static readonly System.String kPropsFileDeploy;
```

- `private static readonly System.String kTargetsFileDeploy`  

```csharp
private static readonly System.String kTargetsFileDeploy;
```

- `private static readonly System.String kTemplatePackageFile`  

```csharp
private static readonly System.String kTemplatePackageFile;
```

- `private static readonly System.String kTemplatePackageSource`  

```csharp
private static readonly System.String kTemplatePackageSource;
```

- `private static readonly System.String kTemplatePackageInstallation`  

```csharp
private static readonly System.String kTemplatePackageInstallation;
```

- `private static const System.String kProjectName`  

```csharp
private static const System.String kProjectName;
```

- `private static const System.String kPropsFile`  

```csharp
private static const System.String kPropsFile;
```

- `private static const System.String kTargetsFile`  

```csharp
private static const System.String kTargetsFile;
```

- `private static const System.String kTemplatePackageId`  

```csharp
private static const System.String kTemplatePackageId;
```

- `private static const System.String kTemplateId`  

```csharp
private static const System.String kTemplateId;
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

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
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

- `public ProjectTemplateDependency()`  

```csharp
public ProjectTemplateDependency();
```


## Methods

- `internal static <IsUpToDate>g__CalculateCache|25_0(System.String file) : System.UInt64`  

```csharp
internal static System.UInt64 <IsUpToDate>g__CalculateCache|25_0(System.String file);
```

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

- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass24_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass28_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass29_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<Install>d__28`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<IsInstalled>d__24`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<Uninstall>d__29`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<get_envVariables>d__23`  


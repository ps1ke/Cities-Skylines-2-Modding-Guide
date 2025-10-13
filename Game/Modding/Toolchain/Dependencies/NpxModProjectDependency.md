# Game.Modding.Toolchain.Dependencies.NpxModProjectDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class NpxModProjectDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private static readonly System.String kNpxPackagePath;
    private static const System.String kProjectName;
    private static const System.String kModuleNamespace;
    private static const System.String kModuleName;

    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
    public System.String name { get; }
    public System.String icon { get; }

    public NpxModProjectDependency();

    private static System.Threading.Tasks.Task DeleteNpxModule(System.String globalNodeModulePath, System.String moduleNamespace, System.String moduleName, System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.String> GetGlobalNodeModulePath(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private static readonly System.String kNpxPackagePath`  

```csharp
private static readonly System.String kNpxPackagePath;
```

- `private static const System.String kProjectName`  

```csharp
private static const System.String kProjectName;
```

- `private static const System.String kModuleNamespace`  

```csharp
private static const System.String kModuleNamespace;
```

- `private static const System.String kModuleName`  

```csharp
private static const System.String kModuleName;
```


## Properties

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

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```


## Constructors

- `public NpxModProjectDependency()`  

```csharp
public NpxModProjectDependency();
```


## Methods

- `private static DeleteNpxModule(System.String globalNodeModulePath, System.String moduleNamespace, System.String moduleName, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private static System.Threading.Tasks.Task DeleteNpxModule(System.String globalNodeModulePath, System.String moduleNamespace, System.String moduleName, System.Threading.CancellationToken token);
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
```

- `private GetGlobalNodeModulePath(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> GetGlobalNodeModulePath(System.Threading.CancellationToken token);
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

- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<>c__DisplayClass14_0`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<>c__DisplayClass19_0`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<DeleteNpxModule>d__20`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<GetGlobalNodeModulePath>d__14`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<Install>d__19`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<IsInstalled>d__15`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<IsUpToDate>d__16`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<Uninstall>d__21`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<get_envVariables>d__6`  


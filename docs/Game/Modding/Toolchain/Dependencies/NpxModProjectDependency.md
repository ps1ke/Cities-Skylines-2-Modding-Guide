# Game.Modding.Toolchain.Dependencies.NpxModProjectDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private static readonly System.String kNpxPackagePath`  
- `private static const System.String kProjectName`  
- `private static const System.String kModuleNamespace`  
- `private static const System.String kModuleName`  

## Properties

- `public System.Type[] dependsOnInstallation { get }`  
- `public System.Type[] dependsOnUninstallation { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  
- `public System.String name { get }`  
- `public System.String icon { get }`  

## Constructors

- `public NpxModProjectDependency()`  

## Methods

- `private static DeleteNpxModule(System.String globalNodeModulePath, System.String moduleNamespace, System.String moduleName, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private GetGlobalNodeModulePath(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

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


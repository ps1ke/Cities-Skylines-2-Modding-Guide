# Game.Modding.Toolchain.Dependencies.UnityModProjectDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `public static readonly System.String kProjectUnzipPath`  
- `public static readonly System.String kProjectZipPath`  
- `public static readonly System.String kModProjectsUnityVersionPath`  
- `public static readonly System.String kModProjectsVersionPath`  
- `public static readonly System.String kModProjectPackages`  
- `public static const System.String kProjectName`  
- `public static const System.String kProjectVersionTxt`  
- `public static const System.String kProjectSettingsAsset`  
- `public static const System.String kProjectPackageManifest`  
- `public static const System.String kProjectPackageLock`  

## Properties

- `public static System.Boolean isUnityOpened { get }`  
- `public System.String name { get }`  
- `public System.String icon { get }`  
- `public System.String version { get; protected set }`  
- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  
- `public System.Type[] dependsOnInstallation { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  

## Constructors

- `public UnityModProjectDependency()`  

## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `private static IsUnityOpenWithModsProject(System.String projectPath) : System.Boolean`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `private static ReadUnityProjectVersion(System.String path) : Colossal.Version`  
- `private static ReadYAMLVersion(System.Collections.Generic.IEnumerable<System.String> lines) : Colossal.Version`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c__DisplayClass29_0`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c__DisplayClass34_0`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<Install>d__29`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<Uninstall>d__30`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<get_envVariables>d__20`  


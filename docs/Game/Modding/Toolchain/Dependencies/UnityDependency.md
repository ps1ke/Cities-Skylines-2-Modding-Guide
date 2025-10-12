# Game.Modding.Toolchain.Dependencies.UnityDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private System.Nullable<System.Int64> m_DownloadSize`  
- `private System.String m_InstallationDirectory`  
- `public static readonly System.String sUnityVersion`  
- `public static readonly System.String kDefaultInstallationDirectory`  
- `public static readonly System.String kInstallationFolder`  
- `private static System.String sUnityPath`  
- `public static const System.String kUnityInstallerUrl`  

## Properties

- `public System.String name { get }`  
- `public System.String icon { get }`  
- `public System.String version { get; protected set }`  
- `public static System.String unityPath { get }`  
- `public static System.String unityExe { get }`  
- `public static System.String unityUninstallerExe { get }`  
- `public System.String installerPath { get }`  
- `public System.String installationDirectory { get; set }`  
- `public System.Boolean canChangeInstallationDirectory { get }`  
- `public System.Boolean confirmUninstallation { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

## Constructors

- `public UnityDependency()`  

## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `private GetUnityInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `private static TryGetParentPath(System.String path, System.Int32 depth, System.String& parentPath) : System.Boolean`  
- `private static TryGetRegistryKeyValue(Microsoft.Win32.RegistryKey registry, System.String path, System.String key, System.String& value) : System.Boolean`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.UnityDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<>c__DisplayClass41_0`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<GetRequiredDiskSpace>d__38`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<GetUnityInstallerSize>d__37`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<Install>d__40`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<NeedDownload>d__36`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<Uninstall>d__41`  


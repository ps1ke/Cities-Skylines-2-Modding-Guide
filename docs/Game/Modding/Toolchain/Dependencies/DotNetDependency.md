# Game.Modding.Toolchain.Dependencies.DotNetDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private System.Nullable<System.Int64> m_DownloadSize`  
- `private System.String m_InstallationDirectory`  
- `private static readonly System.String sDotNetVersion`  
- `public static readonly System.String sDotNetInstallerUrl`  
- `public static readonly System.String kDefaultInstallationDirectory`  
- `public static readonly System.String kInstallationFolder`  
- `private static const System.String kDependencyName`  

## Properties

- `public System.String name { get }`  
- `public System.String icon { get }`  
- `public System.Boolean confirmUninstallation { get }`  
- `public System.String installerPath { get }`  
- `public System.String installationDirectory { get; set }`  
- `public System.Boolean canChangeInstallationDirectory { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  
- `public System.String version { get; protected set }`  

## Constructors

- `public DotNetDependency()`  

## Methods

- `private <>n__0(System.String value) : System.Void`  
- `private <>n__1() : System.String`  
- `private <get_version>b__33_0() : System.Threading.Tasks.Task<System.String>`  
- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private GetDotNetInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  
- `public static GetDotnetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Version>`  
- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `private GetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

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


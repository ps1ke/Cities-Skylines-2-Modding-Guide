# Game.Modding.Toolchain.Dependencies.NodeJSDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private System.Nullable<System.Int64> m_DownloadSize`  
- `private System.String m_InstallationDirectory`  
- `public static readonly System.String kNodeJSVersion`  
- `public static readonly System.String kMinNodeJSVersion`  
- `public static readonly System.String kNodeJSInstallerUrl`  
- `public static readonly System.String kDefaultInstallationDirectory`  
- `public static readonly System.String kInstallationFolder`  

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

- `public NodeJSDependency()`  

## Methods

- `private <>n__0(System.String value) : System.Void`  
- `private <>n__1() : System.String`  
- `private <get_version>b__34_0() : System.Threading.Tasks.Task<System.String>`  
- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private GetDotNetInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  
- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  
- `private GetNodeVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

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


# Game.Modding.Toolchain.Dependencies.UnityLicenseDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private static readonly System.String kSerialBasedLicenseFile`  
- `private static readonly System.String kNamedUserLicenseFile`  

## Properties

- `public System.String name { get }`  
- `public System.String icon { get }`  
- `public System.Boolean confirmUninstallation { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  
- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  
- `public System.Type[] dependsOnInstallation { get }`  
- `public System.Type[] dependsOnUninstallation { get }`  
- `public System.Boolean licenseExists { get }`  

## Constructors

- `public UnityLicenseDependency()`  

## Methods

- `private <Install>b__22_0() : System.Boolean`  
- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.UnityLicenseDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityLicenseDependency+<Install>d__22`  
- `Game.Modding.Toolchain.Dependencies.UnityLicenseDependency+<Uninstall>d__23`  


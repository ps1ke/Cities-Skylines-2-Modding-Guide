# Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Fields

- `private static readonly System.String kPropsFileSource`  
- `private static readonly System.String kTargetsFileSource`  
- `private static readonly System.String kPropsFileDeploy`  
- `private static readonly System.String kTargetsFileDeploy`  
- `private static readonly System.String kTemplatePackageFile`  
- `private static readonly System.String kTemplatePackageSource`  
- `private static readonly System.String kTemplatePackageInstallation`  
- `private static const System.String kProjectName`  
- `private static const System.String kPropsFile`  
- `private static const System.String kTargetsFile`  
- `private static const System.String kTemplatePackageId`  
- `private static const System.String kTemplateId`  

## Properties

- `public System.String name { get }`  
- `public System.String icon { get }`  
- `public Game.UI.Localization.LocalizedString installDescr { get }`  
- `public System.Type[] dependsOnInstallation { get }`  
- `public System.Type[] dependsOnUninstallation { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  

## Constructors

- `public ProjectTemplateDependency()`  

## Methods

- `internal static <IsUpToDate>g__CalculateCache|25_0(System.String file) : System.UInt64`  
- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  
- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass24_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass28_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass29_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<Install>d__28`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<IsInstalled>d__24`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<Uninstall>d__29`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<get_envVariables>d__23`  


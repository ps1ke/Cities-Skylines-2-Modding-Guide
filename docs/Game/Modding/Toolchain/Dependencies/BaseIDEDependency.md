# Game.Modding.Toolchain.Dependencies.BaseIDEDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class abstract public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Properties

- `public System.String minVersion { get }`  
- `public System.Boolean isMinVersion { get }`  
- `public System.String version { get; protected set }`  

## Constructors

- `protected BaseIDEDependency()`  

## Methods

- `private <>n__0() : System.String`  
- `private <get_version>b__5_0() : System.Threading.Tasks.Task<System.String>`  
- `protected abstract GetIDEVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  
- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  
- `public GetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  
- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<<get_version>b__5_0>d`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<GetVersion>d__8`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<IsInstalled>d__9`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<IsUpToDate>d__10`  


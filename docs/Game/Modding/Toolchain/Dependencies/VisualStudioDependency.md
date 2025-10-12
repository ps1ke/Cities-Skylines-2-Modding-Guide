# Game.Modding.Toolchain.Dependencies.VisualStudioDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseIDEDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Properties

- `public System.String name { get }`  
- `public System.String icon { get }`  
- `public System.Boolean canBeInstalled { get }`  
- `public System.Boolean canBeUninstalled { get }`  
- `public static System.String vsWhere { get }`  
- `public System.String minVersion { get }`  

## Constructors

- `public VisualStudioDependency()`  

## Methods

- `protected virtual GetIDEVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  
- `private static GetIDEVersion(System.Threading.CancellationToken token, System.String arguments) : System.Threading.Tasks.Task<System.String>`  
- `private static QueryVsWhere(System.Threading.CancellationToken token, System.String arguments) : System.Threading.Tasks.Task<Game.Modding.Toolchain.Dependencies.VsWhereResult>`  

## Nested types

- `Game.Modding.Toolchain.Dependencies.VisualStudioDependency+<>c__DisplayClass14_0`  
- `Game.Modding.Toolchain.Dependencies.VisualStudioDependency+<GetIDEVersion>d__13`  
- `Game.Modding.Toolchain.Dependencies.VisualStudioDependency+<QueryVsWhere>d__14`  


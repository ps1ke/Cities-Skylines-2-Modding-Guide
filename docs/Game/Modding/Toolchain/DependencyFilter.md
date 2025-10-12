# Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `public readonly Game.Modding.Toolchain.DeploymentAction m_Action`  
- `public readonly Game.Modding.Toolchain.IToolchainDependency m_Dependency`  
- `public readonly System.Collections.Generic.HashSet<System.Type> m_DependsOn`  
- `public readonly System.Collections.Generic.HashSet<System.Type> m_IsDependencyOf`  
- `private Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult <result>k__BackingField`  

## Properties

- `public Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult result { get; private set }`  

## Constructors

- `public DependencyFilter(Game.Modding.Toolchain.DeploymentAction action, Game.Modding.Toolchain.IToolchainDependency dependency)`  

## Methods

- `private CheckIfCanBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters) : System.Void`  
- `private CheckIfNeedToBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters) : System.Void`  
- `public static Process(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToFilter) : System.ValueTuple<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>>`  
- `private SetBackwardDependencies(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters) : System.Void`  

## Nested types

- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c__DisplayClass9_0`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c__DisplayClass9_1`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c__DisplayClass9_2`  


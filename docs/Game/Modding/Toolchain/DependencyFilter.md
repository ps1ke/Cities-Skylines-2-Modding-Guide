# Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public class DependencyFilter
{
    public readonly Game.Modding.Toolchain.DeploymentAction m_Action;
    public readonly Game.Modding.Toolchain.IToolchainDependency m_Dependency;
    public readonly System.Collections.Generic.HashSet<System.Type> m_DependsOn;
    public readonly System.Collections.Generic.HashSet<System.Type> m_IsDependencyOf;
    private Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult <result>k__BackingField;

    public Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult result { get; private set; }

    public DependencyFilter(Game.Modding.Toolchain.DeploymentAction action, Game.Modding.Toolchain.IToolchainDependency dependency);

    private System.Void CheckIfCanBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters);
    private System.Void CheckIfNeedToBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters);
    public static System.ValueTuple<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>> Process(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToFilter);
    private System.Void SetBackwardDependencies(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters);
}
```


## Fields

- `public readonly Game.Modding.Toolchain.DeploymentAction m_Action`  

```csharp
public readonly Game.Modding.Toolchain.DeploymentAction m_Action;
```

- `public readonly Game.Modding.Toolchain.IToolchainDependency m_Dependency`  

```csharp
public readonly Game.Modding.Toolchain.IToolchainDependency m_Dependency;
```

- `public readonly System.Collections.Generic.HashSet<System.Type> m_DependsOn`  

```csharp
public readonly System.Collections.Generic.HashSet<System.Type> m_DependsOn;
```

- `public readonly System.Collections.Generic.HashSet<System.Type> m_IsDependencyOf`  

```csharp
public readonly System.Collections.Generic.HashSet<System.Type> m_IsDependencyOf;
```

- `private Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult <result>k__BackingField`  

```csharp
private Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult <result>k__BackingField;
```


## Properties

- `public Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult result { get; private set }`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult result { get; private set; }
```


## Constructors

- `public DependencyFilter(Game.Modding.Toolchain.DeploymentAction action, Game.Modding.Toolchain.IToolchainDependency dependency)`  

```csharp
public DependencyFilter(Game.Modding.Toolchain.DeploymentAction action, Game.Modding.Toolchain.IToolchainDependency dependency);
```


## Methods

- `private CheckIfCanBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters) : System.Void`  

```csharp
private System.Void CheckIfCanBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters);
```

- `private CheckIfNeedToBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters) : System.Void`  

```csharp
private System.Void CheckIfNeedToBeProcessed(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters);
```

- `public static Process(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToFilter) : System.ValueTuple<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>>`  

```csharp
public static System.ValueTuple<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency>> Process(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToFilter);
```

- `private SetBackwardDependencies(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters) : System.Void`  

```csharp
private System.Void SetBackwardDependencies(System.Collections.Generic.Dictionary<System.Type, Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter> filters);
```


## Nested types

- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c__DisplayClass9_0`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c__DisplayClass9_1`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter+<>c__DisplayClass9_2`  


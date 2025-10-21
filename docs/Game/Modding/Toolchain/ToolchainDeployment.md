# Game.Modding.Toolchain.ToolchainDeployment

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ToolchainDeployment
{
    private static readonly Game.Modding.Toolchain.ToolchainDependencyManager <dependencyManager>k__BackingField;

    public static Game.Modding.Toolchain.ToolchainDependencyManager dependencyManager { get; }

    public static System.Threading.Tasks.Task Run(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies);
    private static System.Threading.Tasks.Task RunImpl(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies);
    public static System.Void RunWithUI(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies, System.Action<System.Boolean> callback);
}
```


## Fields

- `private static readonly Game.Modding.Toolchain.ToolchainDependencyManager <dependencyManager>k__BackingField`  

```csharp
private static readonly Game.Modding.Toolchain.ToolchainDependencyManager <dependencyManager>k__BackingField;
```


## Properties

- `public static Game.Modding.Toolchain.ToolchainDependencyManager dependencyManager { get }`  

```csharp
public static Game.Modding.Toolchain.ToolchainDependencyManager dependencyManager { get; }
```


## Methods

- `public static Run(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies = null) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task Run(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies);
```

- `private static RunImpl(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies) : System.Threading.Tasks.Task`  

```csharp
private static System.Threading.Tasks.Task RunImpl(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies);
```

- `public static RunWithUI(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies = null, System.Action<System.Boolean> callback = null) : System.Void`  

```csharp
public static System.Void RunWithUI(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies, System.Action<System.Boolean> callback);
```


## Nested types

- `Game.Modding.Toolchain.ToolchainDeployment+<>c`  
- `Game.Modding.Toolchain.ToolchainDeployment+<>c__DisplayClass4_0`  
- `Game.Modding.Toolchain.ToolchainDeployment+<Run>d__5`  
- `Game.Modding.Toolchain.ToolchainDeployment+<RunImpl>d__6`  
- `Game.Modding.Toolchain.ToolchainDeployment+<RunWithUI>d__4`  


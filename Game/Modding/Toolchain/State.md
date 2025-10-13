# Game.Modding.Toolchain.ToolchainDependencyManager+State

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct State
{
    public Game.Modding.Toolchain.ModdingToolStatus m_Status;
    public Game.Modding.Toolchain.DeploymentState m_State;
    public System.Int32 m_CurrentStage;
    public System.Int32 m_TotalStages;
    public System.Nullable<System.Int32> m_Progress;
    public Game.UI.Localization.LocalizedString m_Details;

    public Game.Modding.Toolchain.IToolchainDependency+State toDependencyState { get; }

    public virtual System.Int32 GetHashCode();
    public Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public Game.Modding.Toolchain.ToolchainDependencyManager+State WithNextStage();
    public Game.Modding.Toolchain.ToolchainDependencyManager+State WithProgress(System.Nullable<System.Int32> progress, Game.UI.Localization.LocalizedString details);
    public Game.Modding.Toolchain.ToolchainDependencyManager+State WithStages(System.Int32 stages);
    public Game.Modding.Toolchain.ToolchainDependencyManager+State WithState(Game.Modding.Toolchain.DeploymentState state);
    public Game.Modding.Toolchain.ToolchainDependencyManager+State WithStatus(Game.Modding.Toolchain.ModdingToolStatus status);
}
```


## Fields

- `public Game.Modding.Toolchain.ModdingToolStatus m_Status`  

```csharp
public Game.Modding.Toolchain.ModdingToolStatus m_Status;
```

- `public Game.Modding.Toolchain.DeploymentState m_State`  

```csharp
public Game.Modding.Toolchain.DeploymentState m_State;
```

- `public System.Int32 m_CurrentStage`  

```csharp
public System.Int32 m_CurrentStage;
```

- `public System.Int32 m_TotalStages`  

```csharp
public System.Int32 m_TotalStages;
```

- `public System.Nullable<System.Int32> m_Progress`  

```csharp
public System.Nullable<System.Int32> m_Progress;
```

- `public Game.UI.Localization.LocalizedString m_Details`  

```csharp
public Game.UI.Localization.LocalizedString m_Details;
```


## Properties

- `public Game.Modding.Toolchain.IToolchainDependency+State toDependencyState { get }`  

```csharp
public Game.Modding.Toolchain.IToolchainDependency+State toDependencyState { get; }
```


## Methods

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
```

- `public WithNextStage() : Game.Modding.Toolchain.ToolchainDependencyManager+State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State WithNextStage();
```

- `public WithProgress(System.Nullable<System.Int32> progress, Game.UI.Localization.LocalizedString details = null) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State WithProgress(System.Nullable<System.Int32> progress, Game.UI.Localization.LocalizedString details);
```

- `public WithStages(System.Int32 stages) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State WithStages(System.Int32 stages);
```

- `public WithState(Game.Modding.Toolchain.DeploymentState state) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State WithState(Game.Modding.Toolchain.DeploymentState state);
```

- `public WithStatus(Game.Modding.Toolchain.ModdingToolStatus status) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State WithStatus(Game.Modding.Toolchain.ModdingToolStatus status);
```



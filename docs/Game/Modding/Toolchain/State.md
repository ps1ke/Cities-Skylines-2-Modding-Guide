# Game.Modding.Toolchain.ToolchainDependencyManager+State

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Game.Modding.Toolchain.ModdingToolStatus m_Status`  
- `public Game.Modding.Toolchain.DeploymentState m_State`  
- `public System.Int32 m_CurrentStage`  
- `public System.Int32 m_TotalStages`  
- `public System.Nullable<System.Int32> m_Progress`  
- `public Game.UI.Localization.LocalizedString m_Details`  

## Properties

- `public Game.Modding.Toolchain.IToolchainDependency+State toDependencyState { get }`  

## Methods

- `public virtual GetHashCode() : System.Int32`  
- `public GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  
- `public WithNextStage() : Game.Modding.Toolchain.ToolchainDependencyManager+State`  
- `public WithProgress(System.Nullable<System.Int32> progress, Game.UI.Localization.LocalizedString details = null) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  
- `public WithStages(System.Int32 stages) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  
- `public WithState(Game.Modding.Toolchain.DeploymentState state) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  
- `public WithStatus(Game.Modding.Toolchain.ModdingToolStatus status) : Game.Modding.Toolchain.ToolchainDependencyManager+State`  


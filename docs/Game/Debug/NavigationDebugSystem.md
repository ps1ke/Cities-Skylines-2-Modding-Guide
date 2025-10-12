# Game.Debug.NavigationDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_NavigationQuery`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Debug.BaseDebugSystem+Option m_HumanOption`  
- `private Game.Debug.BaseDebugSystem+Option m_AnimalOption`  
- `private Game.Debug.BaseDebugSystem+Option m_CarOption`  
- `private Game.Debug.BaseDebugSystem+Option m_TrainOption`  
- `private Game.Debug.BaseDebugSystem+Option m_WatercraftOption`  
- `private Game.Debug.BaseDebugSystem+Option m_AircraftOption`  
- `private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NavigationDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private DrawNavigationGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private DrawSelectedGizmos(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Debug.NavigationDebugSystem+NavigationGizmoJob`  
- `Game.Debug.NavigationDebugSystem+SelectedNavigationGizmoJob`  
- `Game.Debug.NavigationDebugSystem+TypeHandle`  


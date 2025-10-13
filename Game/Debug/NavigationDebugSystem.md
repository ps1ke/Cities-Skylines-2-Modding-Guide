# Game.Debug.NavigationDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NavigationDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_NavigationQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Debug.BaseDebugSystem+Option m_HumanOption;
    private Game.Debug.BaseDebugSystem+Option m_AnimalOption;
    private Game.Debug.BaseDebugSystem+Option m_CarOption;
    private Game.Debug.BaseDebugSystem+Option m_TrainOption;
    private Game.Debug.BaseDebugSystem+Option m_WatercraftOption;
    private Game.Debug.BaseDebugSystem+Option m_AircraftOption;
    private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle;

    public NavigationDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle DrawNavigationGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle DrawSelectedGizmos(Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NavigationQuery`  

```csharp
private Unity.Entities.EntityQuery m_NavigationQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_HumanOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_HumanOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AnimalOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AnimalOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CarOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CarOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_TrainOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_TrainOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_WatercraftOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_WatercraftOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_AircraftOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_AircraftOption;
```

- `private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.NavigationDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NavigationDebugSystem()`  

```csharp
public NavigationDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private DrawNavigationGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle DrawNavigationGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
```

- `private DrawSelectedGizmos(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle DrawSelectedGizmos(Unity.Jobs.JobHandle inputDeps);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Debug.NavigationDebugSystem+NavigationGizmoJob`  
- `Game.Debug.NavigationDebugSystem+SelectedNavigationGizmoJob`  
- `Game.Debug.NavigationDebugSystem+TypeHandle`  


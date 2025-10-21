# Game.Debug.WindDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class WindDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Colossal.GizmosSystem m_GizmosSystem;

    public WindDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public WindDebugSystem()`  

```csharp
public WindDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.WindDebugSystem+WindGizmoJob`  


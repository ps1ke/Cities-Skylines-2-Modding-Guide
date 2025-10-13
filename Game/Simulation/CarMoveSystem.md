# Game.Simulation.CarMoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CarMoveSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Simulation.CarMoveSystem+TypeHandle __TypeHandle;

    public CarMoveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Simulation.CarMoveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CarMoveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CarMoveSystem()`  

```csharp
public CarMoveSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Simulation.CarMoveSystem+CarMoveJob`  
- `Game.Simulation.CarMoveSystem+TypeHandle`  


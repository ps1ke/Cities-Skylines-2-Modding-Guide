# Game.Simulation.RoadSafetySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadSafetySystem : Game.GameSystemBase
{
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_RoadQuery;
    private Unity.Entities.EntityQuery m_AccidentPrefabQuery;
    private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public RoadSafetySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_RoadQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadQuery;
```

- `private Unity.Entities.EntityQuery m_AccidentPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AccidentPrefabQuery;
```

- `private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public RoadSafetySystem()`  

```csharp
public RoadSafetySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.RoadSafetySystem+RoadSafetyJob`  
- `Game.Simulation.RoadSafetySystem+TypeHandle`  


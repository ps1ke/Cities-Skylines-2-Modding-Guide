# Game.Simulation.SchoolAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SchoolAISystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_SchoolQuery;
    private Game.Simulation.SchoolAISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1235104412_0;
    private Unity.Entities.EntityQuery __query_1235104412_1;
    private Unity.Entities.EntityQuery __query_1235104412_2;

    public SchoolAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_SchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolQuery;
```

- `private Game.Simulation.SchoolAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SchoolAISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1235104412_0`  

```csharp
private Unity.Entities.EntityQuery __query_1235104412_0;
```

- `private Unity.Entities.EntityQuery __query_1235104412_1`  

```csharp
private Unity.Entities.EntityQuery __query_1235104412_1;
```

- `private Unity.Entities.EntityQuery __query_1235104412_2`  

```csharp
private Unity.Entities.EntityQuery __query_1235104412_2;
```


## Constructors

- `public SchoolAISystem()`  

```csharp
public SchoolAISystem();
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.SchoolAISystem+SchoolTickJob`  
- `Game.Simulation.SchoolAISystem+TypeHandle`  


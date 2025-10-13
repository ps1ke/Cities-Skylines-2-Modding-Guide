# Game.Simulation.SpawnableAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SpawnableAmbienceSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Unity.Entities.EntityQuery m_SpawnableQuery;
    private Unity.Entities.EntityQuery m_EmitterQuery;
    private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public SpawnableAmbienceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Unity.Entities.EntityQuery m_SpawnableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableQuery;
```

- `private Unity.Entities.EntityQuery m_EmitterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmitterQuery;
```

- `private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public SpawnableAmbienceSystem()`  

```csharp
public SpawnableAmbienceSystem();
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

- `Game.Simulation.SpawnableAmbienceSystem+GroupAmbienceEffect`  
- `Game.Simulation.SpawnableAmbienceSystem+ApplyAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+EmitterAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+SpawnableAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+TypeHandle`  


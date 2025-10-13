# Game.Simulation.WaterLevelChangeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterLevelChangeSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_WaterLevelChangeQuery;
    private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdateInterval;

    public static System.Int32 TsunamiEndDelay { get; }

    public WaterLevelChangeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.UInt32 GetMinimumDelayAt(Game.Events.WaterLevelChange change, Unity.Mathematics.float3 position);
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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_WaterLevelChangeQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterLevelChangeQuery;
```

- `private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterLevelChangeSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Properties

- `public static System.Int32 TsunamiEndDelay { get }`  

```csharp
public static System.Int32 TsunamiEndDelay { get; }
```


## Constructors

- `public WaterLevelChangeSystem()`  

```csharp
public WaterLevelChangeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetMinimumDelayAt(Game.Events.WaterLevelChange change, Unity.Mathematics.float3 position) : System.UInt32`  

```csharp
public static System.UInt32 GetMinimumDelayAt(Game.Events.WaterLevelChange change, Unity.Mathematics.float3 position);
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

- `Game.Simulation.WaterLevelChangeSystem+WaterLevelChangeJob`  
- `Game.Simulation.WaterLevelChangeSystem+TypeHandle`  


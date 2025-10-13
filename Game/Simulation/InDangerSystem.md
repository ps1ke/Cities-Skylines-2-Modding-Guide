# Game.Simulation.InDangerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InDangerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_InDangerQuery;
    private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype;
    private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 UPDATE_INTERVAL;

    public InDangerSystem();

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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_InDangerQuery`  

```csharp
private Unity.Entities.EntityQuery m_InDangerQuery;
```

- `private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype;
```

- `private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public InDangerSystem()`  

```csharp
public InDangerSystem();
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

- `Game.Simulation.InDangerSystem+InDangerJob`  
- `Game.Simulation.InDangerSystem+TypeHandle`  


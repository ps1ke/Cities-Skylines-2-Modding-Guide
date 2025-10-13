# Game.Simulation.RideNeederSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RideNeederSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NeederQuery;
    private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.RideNeederSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public RideNeederSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NeederQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeederQuery;
```

- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.RideNeederSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.RideNeederSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public RideNeederSystem()`  

```csharp
public RideNeederSystem();
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

- `Game.Simulation.RideNeederSystem+RideNeederTickJob`  
- `Game.Simulation.RideNeederSystem+TypeHandle`  


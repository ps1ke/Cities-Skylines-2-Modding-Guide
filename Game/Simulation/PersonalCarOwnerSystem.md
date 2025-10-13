# Game.Simulation.PersonalCarOwnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PersonalCarOwnerSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_VehicleGroup;
    private Game.Simulation.PersonalCarOwnerSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdateInterval;

    public PersonalCarOwnerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleGroup`  

```csharp
private Unity.Entities.EntityQuery m_VehicleGroup;
```

- `private Game.Simulation.PersonalCarOwnerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PersonalCarOwnerSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Constructors

- `public PersonalCarOwnerSystem()`  

```csharp
public PersonalCarOwnerSystem();
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

- `Game.Simulation.PersonalCarOwnerSystem+PersonalCarOwnerJob`  
- `Game.Simulation.PersonalCarOwnerSystem+TypeHandle`  


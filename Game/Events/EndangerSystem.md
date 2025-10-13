# Game.Events.EndangerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EndangerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_EndangerQuery;
    private Game.Events.EndangerSystem+TypeHandle __TypeHandle;

    public EndangerSystem();

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

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_EndangerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EndangerQuery;
```

- `private Game.Events.EndangerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.EndangerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EndangerSystem()`  

```csharp
public EndangerSystem();
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

- `Game.Events.EndangerSystem+EndangerJob`  
- `Game.Events.EndangerSystem+TypeHandle`  


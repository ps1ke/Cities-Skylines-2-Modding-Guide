# Game.Simulation.MailAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MailAccumulationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_MailProducerQuery;
    private Unity.Entities.EntityArchetype m_PostVanRequestArchetype;
    private Game.Simulation.MailAccumulationSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_890676534_0;
    private Unity.Entities.EntityQuery __query_890676534_1;
    private static const System.UInt32 UPDATE_INTERVAL;

    public MailAccumulationSystem();

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

- `private Unity.Entities.EntityQuery m_MailProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailProducerQuery;
```

- `private Unity.Entities.EntityArchetype m_PostVanRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PostVanRequestArchetype;
```

- `private Game.Simulation.MailAccumulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MailAccumulationSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_890676534_0`  

```csharp
private Unity.Entities.EntityQuery __query_890676534_0;
```

- `private Unity.Entities.EntityQuery __query_890676534_1`  

```csharp
private Unity.Entities.EntityQuery __query_890676534_1;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public MailAccumulationSystem()`  

```csharp
public MailAccumulationSystem();
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

- `Game.Simulation.MailAccumulationSystem+MailAccumulationJob`  
- `Game.Simulation.MailAccumulationSystem+TypeHandle`  


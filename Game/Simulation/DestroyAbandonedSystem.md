# Game.Simulation.DestroyAbandonedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DestroyAbandonedSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_AbandonedQuery;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Game.Simulation.DestroyAbandonedSystem+TypeHandle __TypeHandle;

    public DestroyAbandonedSystem();

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

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_AbandonedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AbandonedQuery;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Game.Simulation.DestroyAbandonedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DestroyAbandonedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DestroyAbandonedSystem()`  

```csharp
public DestroyAbandonedSystem();
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

- `Game.Simulation.DestroyAbandonedSystem+DestroyAbandonedJob`  
- `Game.Simulation.DestroyAbandonedSystem+TypeHandle`  


# Game.Simulation.ObjectCollisionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectCollisionSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityArchetype m_EventImpactArchetype;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
    private Game.Simulation.ObjectCollisionSystem+TypeHandle __TypeHandle;

    public ObjectCollisionSystem();

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

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_EventImpactArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventImpactArchetype;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  

```csharp
private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
```

- `private Game.Simulation.ObjectCollisionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ObjectCollisionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectCollisionSystem()`  

```csharp
public ObjectCollisionSystem();
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

- `Game.Simulation.ObjectCollisionSystem+Collision`  
- `Game.Simulation.ObjectCollisionSystem+FindCollisionsJob`  
- `Game.Simulation.ObjectCollisionSystem+ResolveCollisionsJob`  
- `Game.Simulation.ObjectCollisionSystem+TypeHandle`  


# Game.Prefabs.ProcessingRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProcessingRequirementSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle;

    public ProcessingRequirementSystem();

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

- `private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem`  

```csharp
private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ProcessingRequirementSystem()`  

```csharp
public ProcessingRequirementSystem();
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

- `Game.Prefabs.ProcessingRequirementSystem+ProcessingRequirementJob`  
- `Game.Prefabs.ProcessingRequirementSystem+TypeHandle`  


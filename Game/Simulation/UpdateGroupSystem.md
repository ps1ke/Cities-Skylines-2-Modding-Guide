# Game.Simulation.UpdateGroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpdateGroupSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
    private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes;
    private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle;

    public UpdateGroupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Simulation.UpdateGroupSystem+UpdateGroupSizes GetUpdateGroupSizes();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes`  

```csharp
private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
```

- `private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes`  

```csharp
private Game.Simulation.UpdateGroupSystem+UpdateGroupSizes m_UpdateGroupSizes;
```

- `private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.UpdateGroupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UpdateGroupSystem()`  

```csharp
public UpdateGroupSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetUpdateGroupSizes() : Game.Simulation.UpdateGroupSystem+UpdateGroupSizes`  

```csharp
public Game.Simulation.UpdateGroupSystem+UpdateGroupSizes GetUpdateGroupSizes();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.UpdateGroupSystem+UpdateGroupTypes`  
- `Game.Simulation.UpdateGroupSystem+UpdateGroupSizes`  
- `Game.Simulation.UpdateGroupSystem+UpdateGroupJob`  
- `Game.Simulation.UpdateGroupSystem+MovingObjectsUpdatedJob`  
- `Game.Simulation.UpdateGroupSystem+TypeHandle`  


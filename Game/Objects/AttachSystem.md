# Game.Objects.AttachSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AttachSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.Objects.AttachSystem+TypeHandle __TypeHandle;

    public AttachSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.Objects.AttachSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.AttachSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AttachSystem()`  

```csharp
public AttachSystem();
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

- `Game.Objects.AttachSystem+RemovedAttached`  
- `Game.Objects.AttachSystem+FindAttachedParentsJob`  
- `Game.Objects.AttachSystem+UpdateAttachedReferencesJob`  
- `Game.Objects.AttachSystem+TypeHandle`  


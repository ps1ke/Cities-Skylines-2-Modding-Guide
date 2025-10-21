# Game.Tools.ApplyObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyObjectsSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
    private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle;

    public ApplyObjectsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  

```csharp
private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_TempAnimationTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
```

- `private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyObjectsSystem()`  

```csharp
public ApplyObjectsSystem();
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

- `Game.Tools.ApplyObjectsSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyObjectsSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyObjectsSystem+TypeHandle`  


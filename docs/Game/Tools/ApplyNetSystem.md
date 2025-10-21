# Game.Tools.ApplyNetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyNetSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes;
    private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes;
    private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes;
    private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle;

    public ApplyNetSystem();

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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes;
```

- `private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ApplyNetSystem()`  

```csharp
public ApplyNetSystem();
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

- `Game.Tools.ApplyNetSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyNetSystem+FixConnectedEdgesJob`  
- `Game.Tools.ApplyNetSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyNetSystem+TypeHandle`  


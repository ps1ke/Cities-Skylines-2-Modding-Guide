# Game.Simulation.ResourceFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceFlowSystem : Game.GameSystemBase
{
    private Game.Simulation.ExtractorCompanySystem m_ExtractorCompanySystem;
    private Unity.Entities.EntityQuery m_NetQuery;
    private Game.Simulation.ResourceFlowSystem+TypeHandle __TypeHandle;

    public ResourceFlowSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ExtractorCompanySystem m_ExtractorCompanySystem`  

```csharp
private Game.Simulation.ExtractorCompanySystem m_ExtractorCompanySystem;
```

- `private Unity.Entities.EntityQuery m_NetQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetQuery;
```

- `private Game.Simulation.ResourceFlowSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceFlowSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResourceFlowSystem()`  

```csharp
public ResourceFlowSystem();
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

- `Game.Simulation.ResourceFlowSystem+SourceNodeData`  
- `Game.Simulation.ResourceFlowSystem+TargetDirectionData`  
- `Game.Simulation.ResourceFlowSystem+ResourceNodeItem`  
- `Game.Simulation.ResourceFlowSystem+ResourceFlowJob`  
- `Game.Simulation.ResourceFlowSystem+TypeHandle`  


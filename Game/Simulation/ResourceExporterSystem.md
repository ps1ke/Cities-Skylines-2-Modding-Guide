# Game.Simulation.ResourceExporterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceExporterSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ExporterQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue;
    private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle;

    public ResourceExporterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ExporterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExporterQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ResourceExporterSystem+ExportEvent> m_ExportQueue;
```

- `private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceExporterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResourceExporterSystem()`  

```csharp
public ResourceExporterSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.ResourceExporterSystem+ExportJob`  
- `Game.Simulation.ResourceExporterSystem+ExportEvent`  
- `Game.Simulation.ResourceExporterSystem+HandleExportsJob`  
- `Game.Simulation.ResourceExporterSystem+TypeHandle`  


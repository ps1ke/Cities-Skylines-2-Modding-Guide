# Game.Simulation.WaterPipeRoadConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeRoadConnectionGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeRoadConnectionGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetEdgeUpdateQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeRoadConnectionGraphSystem()`  

```csharp
public WaterPipeRoadConnectionGraphSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
```

- `public GetEdgeUpdateQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetEdgeUpdateQueue(Unity.Jobs.JobHandle& deps);
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

- `Game.Simulation.WaterPipeRoadConnectionGraphSystem+UpdateRoadConnectionsJob`  
- `Game.Simulation.WaterPipeRoadConnectionGraphSystem+UpdateRoadEdgesJob`  
- `Game.Simulation.WaterPipeRoadConnectionGraphSystem+TypeHandle`  


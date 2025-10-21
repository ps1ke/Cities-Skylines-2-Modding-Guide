# Game.Simulation.WorkProviderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkProviderSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_WorkProviderGroup;
    private Unity.Collections.NativeQueue<Game.Simulation.WorkProviderSystem+LayOffReason> m_LayOffQueue;
    private Unity.Collections.NativeArray<System.Int32> m_LayOffs;
    private Game.Simulation.WorkProviderSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_543653706_0;
    private Unity.Entities.EntityQuery __query_543653706_1;
    private static const System.Int32 kUpdatesPerDay;

    public WorkProviderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_WorkProviderGroup`  

```csharp
private Unity.Entities.EntityQuery m_WorkProviderGroup;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.WorkProviderSystem+LayOffReason> m_LayOffQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.WorkProviderSystem+LayOffReason> m_LayOffQueue;
```

- `private Unity.Collections.NativeArray<System.Int32> m_LayOffs`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_LayOffs;
```

- `private Game.Simulation.WorkProviderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WorkProviderSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_543653706_0`  

```csharp
private Unity.Entities.EntityQuery __query_543653706_0;
```

- `private Unity.Entities.EntityQuery __query_543653706_1`  

```csharp
private Unity.Entities.EntityQuery __query_543653706_1;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public WorkProviderSystem()`  

```csharp
public WorkProviderSystem();
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

- `Game.Simulation.WorkProviderSystem+LayOffReason`  
- `Game.Simulation.WorkProviderSystem+WorkProviderTickJob`  
- `Game.Simulation.WorkProviderSystem+LayOffCountJob`  
- `Game.Simulation.WorkProviderSystem+TypeHandle`  


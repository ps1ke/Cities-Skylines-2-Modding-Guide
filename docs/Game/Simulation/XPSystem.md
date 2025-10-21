# Game.Simulation.XPSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IXPSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class XPSystem : Game.GameSystemBase, Game.Simulation.IXPSystem
{
    private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages;
    private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue;
    private Unity.Jobs.JobHandle m_QueueWriters;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.XPSystem+TypeHandle __TypeHandle;

    public XPSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Game.Simulation.XPGain> GetQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void TransferMessages(Game.Simulation.IXPMessageHandler handler);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue;
```

- `private Unity.Jobs.JobHandle m_QueueWriters`  

```csharp
private Unity.Jobs.JobHandle m_QueueWriters;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.XPSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.XPSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public XPSystem()`  

```csharp
public XPSystem();
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

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.XPGain>`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.XPGain> GetQueue(Unity.Jobs.JobHandle& deps);
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

- `public TransferMessages(Game.Simulation.IXPMessageHandler handler) : System.Void`  

```csharp
public System.Void TransferMessages(Game.Simulation.IXPMessageHandler handler);
```


## Nested types

- `Game.Simulation.XPSystem+XPQueueProcessJob`  
- `Game.Simulation.XPSystem+TypeHandle`  


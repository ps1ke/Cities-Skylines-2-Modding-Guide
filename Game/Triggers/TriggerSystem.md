# Game.Triggers.TriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TriggerSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues;
    private Unity.Jobs.JobHandle m_Dependencies;
    private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.Triggers.RadioTagSystem m_RadioTagSystem;
    private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem;
    private System.DateTime m_LastTimedEventTime;
    private System.TimeSpan m_TimedEventInterval;
    private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames;
    private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle;

    public TriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddActionBufferWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> CreateActionBuffer();
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem`  

```csharp
private Game.Prefabs.TriggerPrefabSystem m_TriggerPrefabSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues`  

```csharp
private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>> m_Queues;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private Game.Triggers.CreateChirpSystem m_CreateChirpSystem`  

```csharp
private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
```

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.Triggers.RadioTagSystem m_RadioTagSystem`  

```csharp
private Game.Triggers.RadioTagSystem m_RadioTagSystem;
```

- `private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem`  

```csharp
private Game.Tutorials.TutorialEventActivationSystem m_TutorialEventActivationSystem;
```

- `private System.DateTime m_LastTimedEventTime`  

```csharp
private System.DateTime m_LastTimedEventTime;
```

- `private System.TimeSpan m_TimedEventInterval`  

```csharp
private System.TimeSpan m_TimedEventInterval;
```

- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.UInt32> m_TriggerFrames;
```

- `private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.TriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TriggerSystem()`  

```csharp
public TriggerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddActionBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddActionBufferWriter(Unity.Jobs.JobHandle handle);
```

- `public CreateActionBuffer() : Unity.Collections.NativeQueue<Game.Triggers.TriggerAction>`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> CreateActionBuffer();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Triggers.TriggerSystem+TriggerActionJob`  
- `Game.Triggers.TriggerSystem+TypeHandle`  


# Game.Triggers.LifePathEventSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LifePathEventSystem : Game.GameSystemBase
{
    private System.Boolean <m_DebugLifePathChirps>k__BackingField;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
    private Unity.Entities.EntityQuery m_FollowedQuery;
    private Unity.Entities.EntityQuery m_DeletedFollowedQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityArchetype m_EventArchetype;
    private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kMaxFollowed;

    public System.Boolean m_DebugLifePathChirps { get; set; }

    public LifePathEventSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public System.Boolean FollowCitizen(Unity.Entities.Entity citizen);
    public Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> GetQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Boolean UnfollowCitizen(Unity.Entities.Entity citizen);
}
```


## Fields

- `private System.Boolean <m_DebugLifePathChirps>k__BackingField`  

```csharp
private System.Boolean <m_DebugLifePathChirps>k__BackingField;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Game.Triggers.CreateChirpSystem m_CreateChirpSystem`  

```csharp
private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
```

- `private Unity.Entities.EntityQuery m_FollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FollowedQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedFollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedFollowedQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityArchetype m_EventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventArchetype;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kMaxFollowed`  

```csharp
public static readonly System.Int32 kMaxFollowed;
```


## Properties

- `public System.Boolean m_DebugLifePathChirps { get; set }`  

```csharp
public System.Boolean m_DebugLifePathChirps { get; set; }
```


## Constructors

- `public LifePathEventSystem()`  

```csharp
public LifePathEventSystem();
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

- `public FollowCitizen(Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public System.Boolean FollowCitizen(Unity.Entities.Entity citizen);
```

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData>`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> GetQueue(Unity.Jobs.JobHandle& deps);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public UnfollowCitizen(Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public System.Boolean UnfollowCitizen(Unity.Entities.Entity citizen);
```


## Nested types

- `Game.Triggers.LifePathEventSystem+CreateLifePathEventJob`  
- `Game.Triggers.LifePathEventSystem+CleanupLifePathEntriesJob`  
- `Game.Triggers.LifePathEventSystem+TypeHandle`  


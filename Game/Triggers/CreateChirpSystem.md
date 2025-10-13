# Game.Triggers.CreateChirpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CreateChirpSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue;
    private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle;

    public CreateChirpSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> GetQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue;
```

- `private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CreateChirpSystem()`  

```csharp
public CreateChirpSystem();
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

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData>`  

```csharp
public Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> GetQueue(Unity.Jobs.JobHandle& deps);
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


## Nested types

- `Game.Triggers.CreateChirpSystem+CollectRecentChirpsJob`  
- `Game.Triggers.CreateChirpSystem+CreateChirpJob`  
- `Game.Triggers.CreateChirpSystem+TypeHandle`  


# Game.Simulation.LeisureSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LeisureSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Events.AddMeetingSystem m_AddMeetingSystem;
    private Unity.Entities.EntityQuery m_LeisureQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_LeisureParameterQuery;
    private Unity.Entities.EntityQuery m_ResidentPrefabQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue;
    private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kLeisureConsumeAmount;

    public LeisureSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> tempProviderList, Game.Prefabs.LeisureProviderData providerToAdd);
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

- `private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Events.AddMeetingSystem m_AddMeetingSystem`  

```csharp
private Game.Events.AddMeetingSystem m_AddMeetingSystem;
```

- `private Unity.Entities.EntityQuery m_LeisureQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ResidentPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue;
```

- `private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kLeisureConsumeAmount`  

```csharp
private static readonly System.Int32 kLeisureConsumeAmount;
```


## Constructors

- `public LeisureSystem()`  

```csharp
public LeisureSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> tempProviderList, Game.Prefabs.LeisureProviderData providerToAdd) : System.Void`  

```csharp
public static System.Void AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> tempProviderList, Game.Prefabs.LeisureProviderData providerToAdd);
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

- `Game.Simulation.LeisureSystem+SpendLeisurejob`  
- `Game.Simulation.LeisureSystem+LeisureJob`  
- `Game.Simulation.LeisureSystem+TypeHandle`  


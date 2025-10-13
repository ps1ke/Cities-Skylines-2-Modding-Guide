# Game.Simulation.CitizenBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenBehaviorSystem : Game.GameSystemBase
{
    private Unity.Jobs.JobHandle m_CarReserveWriters;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_LeisureParameterQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityArchetype m_HouseholdArchetype;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue;
    private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle;
    public static readonly System.Single kMaxPathfindCost;
    public static readonly System.Single kMaxMovingAwayCost;
    public static readonly System.Int32 kMinLeisurePossibility;

    public CitizenBehaviorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCarReserveWriter(Unity.Jobs.JobHandle writer);
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetCarReserveQueue(Unity.Jobs.JobHandle& deps);
    public static Unity.Mathematics.float2 GetSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    public static System.Boolean IsSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.Single normalizedTime, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Jobs.JobHandle m_CarReserveWriters`  

```csharp
private Unity.Jobs.JobHandle m_CarReserveWriters;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityArchetype m_HouseholdArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HouseholdArchetype;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue;
```

- `private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Single kMaxPathfindCost`  

```csharp
public static readonly System.Single kMaxPathfindCost;
```

- `public static readonly System.Single kMaxMovingAwayCost`  

```csharp
public static readonly System.Single kMaxMovingAwayCost;
```

- `public static readonly System.Int32 kMinLeisurePossibility`  

```csharp
public static readonly System.Int32 kMinLeisurePossibility;
```


## Constructors

- `public CitizenBehaviorSystem()`  

```csharp
public CitizenBehaviorSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddCarReserveWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public System.Void AddCarReserveWriter(Unity.Jobs.JobHandle writer);
```

- `public GetCarReserveQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetCarReserveQueue(Unity.Jobs.JobHandle& deps);
```

- `public static GetSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `public static IsSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.Single normalizedTime, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : System.Boolean`  

```csharp
public static System.Boolean IsSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.Single normalizedTime, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
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

- `Game.Simulation.CitizenBehaviorSystem+CitizenReserveHouseholdCarJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizenTryCollectMailJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizeSleepJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizenAITickJob`  
- `Game.Simulation.CitizenBehaviorSystem+TypeHandle`  


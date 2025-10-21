# Game.Simulation.HouseholdSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle;

    public HouseholdSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  

```csharp
private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem`  

```csharp
private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdSpawnSystem()`  

```csharp
public HouseholdSpawnSystem();
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

- `Game.Simulation.HouseholdSpawnSystem+SpawnHouseholdJob`  
- `Game.Simulation.HouseholdSpawnSystem+TypeHandle`  


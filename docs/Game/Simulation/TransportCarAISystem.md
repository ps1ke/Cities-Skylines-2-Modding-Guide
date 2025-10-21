# Game.Simulation.TransportCarAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportCarAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
    private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype;
    private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes;
    private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
    private Game.Simulation.TransportCarAISystem+TypeHandle __TypeHandle;

    public TransportCarAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes;
```

- `private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData`  

```csharp
private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
```

- `private Game.Simulation.TransportCarAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportCarAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TransportCarAISystem()`  

```csharp
public TransportCarAISystem();
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.TransportCarAISystem+TransportCarTickJob`  
- `Game.Simulation.TransportCarAISystem+TypeHandle`  


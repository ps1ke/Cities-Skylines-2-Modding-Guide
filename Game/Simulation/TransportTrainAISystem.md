# Game.Simulation.TransportTrainAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportTrainAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityQuery m_CarriagePrefabQuery;
    private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainAddTypes;
    private Game.Prefabs.TransportTrainCarriageSelectData m_TransportTrainCarriageSelectData;
    private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
    private Game.Simulation.TransportTrainAISystem+TypeHandle __TypeHandle;

    public TransportTrainAISystem();

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

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityQuery m_CarriagePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarriagePrefabQuery;
```

- `private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainAddTypes;
```

- `private Game.Prefabs.TransportTrainCarriageSelectData m_TransportTrainCarriageSelectData`  

```csharp
private Game.Prefabs.TransportTrainCarriageSelectData m_TransportTrainCarriageSelectData;
```

- `private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData`  

```csharp
private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
```

- `private Game.Simulation.TransportTrainAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportTrainAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TransportTrainAISystem()`  

```csharp
public TransportTrainAISystem();
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

- `Game.Simulation.TransportTrainAISystem+TransportTrainTickJob`  
- `Game.Simulation.TransportTrainAISystem+TypeHandle`  


# Game.Simulation.TransportWatercraftAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportWatercraftAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
    private Game.Simulation.TransportWatercraftAISystem+TypeHandle __TypeHandle;

    public TransportWatercraftAISystem();

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

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData`  

```csharp
private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
```

- `private Game.Simulation.TransportWatercraftAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportWatercraftAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TransportWatercraftAISystem()`  

```csharp
public TransportWatercraftAISystem();
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

- `Game.Simulation.TransportWatercraftAISystem+TransportWatercraftTickJob`  
- `Game.Simulation.TransportWatercraftAISystem+TypeHandle`  


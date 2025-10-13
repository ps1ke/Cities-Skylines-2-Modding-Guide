# Game.Simulation.HouseholdFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdFindPropertySystem : Game.GameSystemBase
{
    public System.Boolean debugDisableHomeless;
    private Game.Debug.DebugWatchDistribution m_DefaultDistribution;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_HomelessHouseholdQuery;
    private Unity.Entities.EntityQuery m_FreePropertyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityQuery m_ParkParameterQuery;
    private Unity.Entities.EntityQuery m_EducationParameterQuery;
    private Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Unity.Entities.EntityQuery m_PoliceParameterQuery;
    private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kMaxProcessEntitiesPerUpdate;
    public static readonly System.Int32 kFindPropertyCoolDown;
    private static const System.Int32 UPDATE_INTERVAL;

    public HouseholdFindPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Boolean debugDisableHomeless`  

```csharp
public System.Boolean debugDisableHomeless;
```

- `private Game.Debug.DebugWatchDistribution m_DefaultDistribution`  

```csharp
private Game.Debug.DebugWatchDistribution m_DefaultDistribution;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HomelessHouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HomelessHouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreePropertyQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  

```csharp
private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
```

- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kMaxProcessEntitiesPerUpdate`  

```csharp
public static readonly System.Int32 kMaxProcessEntitiesPerUpdate;
```

- `public static readonly System.Int32 kFindPropertyCoolDown`  

```csharp
public static readonly System.Int32 kFindPropertyCoolDown;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Constructors

- `public HouseholdFindPropertySystem()`  

```csharp
public HouseholdFindPropertySystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.HouseholdFindPropertySystem+CachedPropertyInformation`  
- `Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality`  
- `Game.Simulation.HouseholdFindPropertySystem+PreparePropertyJob`  
- `Game.Simulation.HouseholdFindPropertySystem+FindPropertyJob`  
- `Game.Simulation.HouseholdFindPropertySystem+TypeHandle`  


# Game.Simulation.HouseholdFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Boolean debugDisableHomeless`  
- `private Game.Debug.DebugWatchDistribution m_DefaultDistribution`  
- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow`  
- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium`  
- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh`  
- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_HomelessHouseholdQuery`  
- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  
- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  
- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  
- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  
- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  
- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  
- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  
- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  
- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  
- `private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kMaxProcessEntitiesPerUpdate`  
- `public static readonly System.Int32 kFindPropertyCoolDown`  
- `private static const System.Int32 UPDATE_INTERVAL`  

## Constructors

- `public HouseholdFindPropertySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HouseholdFindPropertySystem+CachedPropertyInformation`  
- `Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality`  
- `Game.Simulation.HouseholdFindPropertySystem+PreparePropertyJob`  
- `Game.Simulation.HouseholdFindPropertySystem+FindPropertyJob`  
- `Game.Simulation.HouseholdFindPropertySystem+TypeHandle`  


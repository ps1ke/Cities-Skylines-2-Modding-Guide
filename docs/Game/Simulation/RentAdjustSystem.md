# Game.Simulation.RentAdjustSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  
- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  
- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  
- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  
- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  
- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  
- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  
- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  
- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `protected System.Int32 cycles`  
- `private Game.Simulation.RentAdjustSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public RentAdjustSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.RentAdjustSystem+AdjustRentJob`  
- `Game.Simulation.RentAdjustSystem+TypeHandle`  


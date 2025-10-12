# Game.Simulation.CrimeAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  
- `private Unity.Entities.EntityQuery m_PoliceConfigurationQuery`  
- `private Unity.Entities.EntityArchetype m_PatrolRequestArchetype`  
- `private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kUpdateInterval`  

## Constructors

- `public CrimeAccumulationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CrimeAccumulationSystem+CrimeAccumulationJob`  
- `Game.Simulation.CrimeAccumulationSystem+TypeHandle`  


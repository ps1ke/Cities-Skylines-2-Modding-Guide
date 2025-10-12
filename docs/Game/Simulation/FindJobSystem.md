# Game.Simulation.FindJobSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_JobSeekerQuery`  
- `private Unity.Entities.EntityQuery m_ResultsQuery`  
- `private Unity.Entities.EntityQuery m_FreeQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Collections.NativeArray<System.Int32> m_FreeCache`  
- `private Colossal.Collections.NativeValue<System.Int32> m_StartedWorking`  
- `private Unity.Jobs.JobHandle m_WriteDeps`  
- `private Game.Simulation.FindJobSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATE_INTERVAL`  

## Constructors

- `public FindJobSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.FindJobSystem+CalculateFreeWorkplaceJob`  
- `Game.Simulation.FindJobSystem+FindJobJob`  
- `Game.Simulation.FindJobSystem+StartWorkingJob`  
- `Game.Simulation.FindJobSystem+TypeHandle`  


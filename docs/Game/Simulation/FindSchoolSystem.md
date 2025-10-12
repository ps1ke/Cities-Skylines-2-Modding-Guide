# Game.Simulation.FindSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Boolean debugFastFindSchool`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_SchoolSeekerQuery`  
- `private Unity.Entities.EntityQuery m_ResultsQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.FindSchoolSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_17488131_0`  
- `private Unity.Entities.EntityQuery __query_17488131_1`  

## Constructors

- `public FindSchoolSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.FindSchoolSystem+FindSchoolJob`  
- `Game.Simulation.FindSchoolSystem+StartStudyingJob`  
- `Game.Simulation.FindSchoolSystem+TypeHandle`  


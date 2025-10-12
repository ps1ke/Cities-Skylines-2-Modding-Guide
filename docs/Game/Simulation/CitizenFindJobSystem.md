# Game.Simulation.CitizenFindJobSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_UnemployedQuery`  
- `private Unity.Entities.EntityQuery m_EmployedQuery`  
- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  
- `private Game.Simulation.CitizenFindJobSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kJobSeekCoolDownMax`  
- `public static readonly System.Int32 kJobSeekCoolDownMin`  

## Constructors

- `public CitizenFindJobSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CitizenFindJobSystem+CitizenFindJobJob`  
- `Game.Simulation.CitizenFindJobSystem+TypeHandle`  


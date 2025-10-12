# Game.Simulation.LeaveHouseholdSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_LeaveHouseholdQuery`  
- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.Simulation.LeaveHouseholdSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kNewHouseholdStartMoney`  

## Constructors

- `public LeaveHouseholdSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.LeaveHouseholdSystem+LeaveHouseholdJob`  
- `Game.Simulation.LeaveHouseholdSystem+TypeHandle`  


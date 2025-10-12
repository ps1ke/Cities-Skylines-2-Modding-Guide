# Game.Simulation.FindEventAttendantsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue`  
- `private Unity.Entities.EntityArchetype m_MeetingArchetype`  
- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  
- `private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public FindEventAttendantsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.FindEventAttendantsSystem+Attend`  
- `Game.Simulation.FindEventAttendantsSystem+AttendJob`  
- `Game.Simulation.FindEventAttendantsSystem+ConsiderAttendanceJob`  
- `Game.Simulation.FindEventAttendantsSystem+TypeHandle`  


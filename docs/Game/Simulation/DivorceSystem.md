# Game.Simulation.DivorceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce`  
- `private Colossal.NativeCounter m_DebugDivorceCount`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  
- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public DivorceSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.DivorceSystem+CheckDivorceJob`  
- `Game.Simulation.DivorceSystem+SumDivorceJob`  
- `Game.Simulation.DivorceSystem+TypeHandle`  


# Game.Simulation.BirthSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Colossal.Collections.NativeValue<System.Int32> m_DebugBirth`  
- `private Colossal.NativeCounter m_DebugBirthCounter`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  
- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  
- `public System.Int32 m_BirthChance`  
- `private Game.Simulation.BirthSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public BirthSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.BirthSystem+CheckBirthJob`  
- `Game.Simulation.BirthSystem+SumBirthJob`  
- `Game.Simulation.BirthSystem+TypeHandle`  


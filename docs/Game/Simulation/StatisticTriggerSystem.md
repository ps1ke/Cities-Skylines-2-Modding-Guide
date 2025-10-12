# Game.Simulation.StatisticTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 kUpdatesPerDay`  

## Constructors

- `public StatisticTriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.StatisticTriggerSystem+SendTriggersJob`  
- `Game.Simulation.StatisticTriggerSystem+TypeHandle`  


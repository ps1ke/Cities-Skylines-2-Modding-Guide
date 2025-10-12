# Game.Simulation.PollutionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult`  
- `private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_380796347_0`  

## Constructors

- `public PollutionTriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PollutionTriggerSystem+CalculateAverageAirPollutionJob`  
- `Game.Simulation.PollutionTriggerSystem+SendPollutionTriggerJob`  
- `Game.Simulation.PollutionTriggerSystem+TypeHandle`  


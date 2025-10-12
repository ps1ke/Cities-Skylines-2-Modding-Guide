# Game.Simulation.PetAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_CreatureQuery`  
- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  
- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypes`  
- `private Game.Simulation.PetAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public PetAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PetAISystem+Boarding`  
- `Game.Simulation.PetAISystem+BoardingType`  
- `Game.Simulation.PetAISystem+PetTickJob`  
- `Game.Simulation.PetAISystem+BoardingJob`  
- `Game.Simulation.PetAISystem+TypeHandle`  


# Game.Simulation.MailAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_MailProducerQuery`  
- `private Unity.Entities.EntityArchetype m_PostVanRequestArchetype`  
- `private Game.Simulation.MailAccumulationSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_890676534_0`  
- `private Unity.Entities.EntityQuery __query_890676534_1`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public MailAccumulationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.MailAccumulationSystem+MailAccumulationJob`  
- `Game.Simulation.MailAccumulationSystem+TypeHandle`  


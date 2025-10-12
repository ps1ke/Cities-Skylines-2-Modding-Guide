# Game.Events.ImpactSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_ImpactQuery`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes`  
- `private Game.Events.ImpactSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ImpactSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Events.ImpactSystem+AddImpactJob`  
- `Game.Events.ImpactSystem+TypeHandle`  


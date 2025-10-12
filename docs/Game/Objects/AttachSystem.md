# Game.Objects.AttachSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_ObjectQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.Objects.AttachSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AttachSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Objects.AttachSystem+RemovedAttached`  
- `Game.Objects.AttachSystem+FindAttachedParentsJob`  
- `Game.Objects.AttachSystem+UpdateAttachedReferencesJob`  
- `Game.Objects.AttachSystem+TypeHandle`  


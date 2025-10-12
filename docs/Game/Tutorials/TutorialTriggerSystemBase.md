# Game.Tutorials.TutorialTriggerSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Fields

- `protected Game.Common.ModificationBarrier5 m_BarrierSystem`  
- `protected Unity.Entities.EntityQuery m_ActiveTriggerQuery`  
- `private Game.Tutorials.TutorialSystem m_TutorialSystem`  
- `private Unity.Entities.Entity m_LastPhase`  
- `private System.Boolean <triggersChanged>k__BackingField`  

## Properties

- `protected System.Boolean triggersChanged { protected get; private set }`  

## Constructors

- `protected TutorialTriggerSystemBase()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  


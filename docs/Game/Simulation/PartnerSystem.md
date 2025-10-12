# Game.Simulation.PartnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_PartnerQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.PartnerSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public PartnerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.PartnerSystem+MatchJob`  
- `Game.Simulation.PartnerSystem+TypeHandle`  


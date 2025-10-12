# Game.Simulation.TrafficBottleneckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_BlockerQuery`  
- `private Unity.Entities.EntityQuery m_BottleneckQuery`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TrafficBottleneckSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TrafficBottleneckSystem+GroupData`  
- `Game.Simulation.TrafficBottleneckSystem+BottleneckData`  
- `Game.Simulation.TrafficBottleneckSystem+BottleneckState`  
- `Game.Simulation.TrafficBottleneckSystem+TrafficBottleneckJob`  
- `Game.Simulation.TrafficBottleneckSystem+TypeHandle`  


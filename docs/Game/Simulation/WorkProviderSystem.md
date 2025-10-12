# Game.Simulation.WorkProviderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_WorkProviderGroup`  
- `private Unity.Collections.NativeQueue<Game.Simulation.WorkProviderSystem+LayOffReason> m_LayOffQueue`  
- `private Unity.Collections.NativeArray<System.Int32> m_LayOffs`  
- `private Game.Simulation.WorkProviderSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_543653706_0`  
- `private Unity.Entities.EntityQuery __query_543653706_1`  
- `private static const System.Int32 kUpdatesPerDay`  

## Constructors

- `public WorkProviderSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WorkProviderSystem+LayOffReason`  
- `Game.Simulation.WorkProviderSystem+WorkProviderTickJob`  
- `Game.Simulation.WorkProviderSystem+LayOffCountJob`  
- `Game.Simulation.WorkProviderSystem+TypeHandle`  


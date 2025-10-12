# Game.Simulation.LookForPartnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Entities.EntityQuery m_LookingQuery`  
- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  
- `private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue`  
- `private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner`  
- `private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public LookForPartnerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.LookForPartnerSystem+AddPartnerSeekerJob`  
- `Game.Simulation.LookForPartnerSystem+LookForPartnerJob`  
- `Game.Simulation.LookForPartnerSystem+TypeHandle`  


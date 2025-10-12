# Game.Simulation.PayWageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  
- `private Unity.Entities.EntityQuery m_HouseholdGroup`  
- `private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue`  
- `private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public PayWageSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PayWageSystem+Payment`  
- `Game.Simulation.PayWageSystem+PayJob`  
- `Game.Simulation.PayWageSystem+PayWageJob`  
- `Game.Simulation.PayWageSystem+TypeHandle`  


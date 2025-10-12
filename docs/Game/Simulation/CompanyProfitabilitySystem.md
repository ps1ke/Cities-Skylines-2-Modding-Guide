# Game.Simulation.CompanyProfitabilitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery`  
- `private Game.Simulation.CompanyProfitabilitySystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public CompanyProfitabilitySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CompanyProfitabilitySystem+CompanyProfitabilityJob`  
- `Game.Simulation.CompanyProfitabilitySystem+TypeHandle`  


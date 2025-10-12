# Game.Simulation.CompanyDividendSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_CompanyQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.CompanyDividendSystem+Dividend> m_DividendQueue`  
- `private Game.Simulation.CompanyDividendSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public CompanyDividendSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CompanyDividendSystem+Dividend`  
- `Game.Simulation.CompanyDividendSystem+ProcessDividendsJob`  
- `Game.Simulation.CompanyDividendSystem+DividendJob`  
- `Game.Simulation.CompanyDividendSystem+TypeHandle`  


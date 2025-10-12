# Game.Simulation.IndustrialAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Unity.Entities.EntityQuery m_CompanyQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.Simulation.IndustrialAISystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kLowestCompanyWorth`  
- `public static readonly System.Int32 kMinimumEmployee`  
- `public static readonly System.Int32 kMaxVirtualResourceStorage`  

## Constructors

- `public IndustrialAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.IndustrialAISystem+CompanyAITickJob`  
- `Game.Simulation.IndustrialAISystem+TypeHandle`  


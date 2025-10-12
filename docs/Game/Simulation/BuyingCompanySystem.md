# Game.Simulation.BuyingCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  
- `private Unity.Entities.EntityQuery m_CompanyGroup`  
- `private Game.Simulation.BuyingCompanySystem+TypeHandle __TypeHandle`  
- `private static readonly System.Single kNotificationCostLimit`  
- `private static readonly System.Int32 kResourceLowStockAmount`  
- `private static readonly System.Int32 kResourceMinimumRequestAmount`  

## Constructors

- `public BuyingCompanySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.BuyingCompanySystem+CompanyBuyJob`  
- `Game.Simulation.BuyingCompanySystem+TypeHandle`  


# Game.Simulation.ResourceBuyerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuyerQuery`  
- `private Unity.Entities.EntityQuery m_CarPrefabQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_ResidentPrefabQuery`  
- `private Unity.Entities.EntityQuery m_PopulationQuery`  
- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.ResourceBuyerSystem+SalesEvent> m_SalesQueue`  
- `private Game.Simulation.ResourceBuyerSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATE_INTERVAL`  

## Constructors

- `public ResourceBuyerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ResourceBuyerSystem+SaleFlags`  
- `Game.Simulation.ResourceBuyerSystem+SalesEvent`  
- `Game.Simulation.ResourceBuyerSystem+BuyJob`  
- `Game.Simulation.ResourceBuyerSystem+HandleBuyersJob`  
- `Game.Simulation.ResourceBuyerSystem+TypeHandle`  


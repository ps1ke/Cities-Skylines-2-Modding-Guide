# Game.Policies.ModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  
- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos`  
- `private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData`  
- `private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData`  
- `private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData`  
- `private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData`  
- `private Unity.Entities.Entity m_TicketPricePolicy`  
- `private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ModifiedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Policies.ModifiedSystem+PolicyRange`  
- `Game.Policies.ModifiedSystem+PolicyEventInfo`  
- `Game.Policies.ModifiedSystem+ModifyPolicyJob`  
- `Game.Policies.ModifiedSystem+TypeHandle`  


# Game.Simulation.RemovedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_DeletedBuildings`  
- `private Unity.Entities.EntityQuery m_DeletedWorkplaces`  
- `private Unity.Entities.EntityQuery m_DeletedCompanies`  
- `private Unity.Entities.EntityQuery m_NeedUpdateRenterQuery`  
- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  
- `private Unity.Entities.EntityQuery m_CompanyNotificationParameterQuery`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Simulation.RemovedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RemovedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.RemovedSystem+RemovedPropertyJob`  
- `Game.Simulation.RemovedSystem+RemovedWorkplaceJob`  
- `Game.Simulation.RemovedSystem+RemovedCompanyJob`  
- `Game.Simulation.RemovedSystem+RentersUpdateJob`  
- `Game.Simulation.RemovedSystem+TypeHandle`  


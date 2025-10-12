# Game.Vehicles.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Objects.SearchSystem m_SearchSystem`  
- `private Unity.Entities.EntityQuery m_CarQuery`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.EntityQuery m_LayoutQuery`  
- `private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ReferencesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Vehicles.ReferencesSystem+InitializeCurrentLaneJob`  
- `Game.Vehicles.ReferencesSystem+UpdateLayoutReferencesJob`  
- `Game.Vehicles.ReferencesSystem+UpdateVehicleReferencesJob`  
- `Game.Vehicles.ReferencesSystem+TypeHandle`  


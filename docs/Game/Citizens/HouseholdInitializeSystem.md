# Game.Citizens.HouseholdInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CarPrefabGroup`  
- `private Unity.Entities.EntityQuery m_CitizenPrefabGroup`  
- `private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup`  
- `private Unity.Entities.EntityQuery m_Additions`  
- `private Game.Common.ModificationBarrier4 m_EndFrameBarrier`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  
- `private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public HouseholdInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Citizens.HouseholdInitializeSystem+InitializeHouseholdJob`  
- `Game.Citizens.HouseholdInitializeSystem+TypeHandle`  


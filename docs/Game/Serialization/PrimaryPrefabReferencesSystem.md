# Game.Serialization.PrimaryPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  
- `private Unity.Entities.EntityQuery m_PrefabRefQuery`  
- `private Unity.Entities.EntityQuery m_SetLevelQuery`  
- `private Unity.Entities.EntityQuery m_CompanyDataQuery`  
- `private Unity.Entities.EntityQuery m_PolicyQuery`  
- `private Unity.Entities.EntityQuery m_ActualBudgetQuery`  
- `private Unity.Entities.EntityQuery m_ServiceBudgetQuery`  
- `private Unity.Entities.EntityQuery m_VehicleModelQuery`  
- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  
- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  
- `private Unity.Entities.EntityQuery m_BiomeQuery`  
- `private Unity.Entities.EntityQuery m_ChirpQuery`  
- `private Unity.Entities.EntityQuery m_SubReplacementQuery`  
- `private Game.Serialization.PrimaryPrefabReferencesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PrimaryPrefabReferencesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.PrimaryPrefabReferencesSystem+FixPrefabRefJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixUnderConstructionJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixCompanyDataJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixPolicyJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixServiceBudgetJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixAtmosphereJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixBiomeJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixVehicleModelJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixEditorContainerJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixChirpJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixSubReplacementJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+TypeHandle`  


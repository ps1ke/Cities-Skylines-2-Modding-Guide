# Game.Serialization.SecondaryPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  
- `private Unity.Entities.EntityQuery m_SpawnableBuildingQuery`  
- `private Unity.Entities.EntityQuery m_PlaceholderBuildingQuery`  
- `private Unity.Entities.EntityQuery m_ServiceObjectQuery`  
- `private Unity.Entities.EntityQuery m_NetLaneQuery`  
- `private Unity.Entities.EntityQuery m_TransportLineQuery`  
- `private Unity.Entities.EntityQuery m_ContentPrerequisiteQuery`  
- `private Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SecondaryPrefabReferencesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.SecondaryPrefabReferencesSystem+FixSpawnableBuildingJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixPlaceholderBuildingJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixServiceObjectDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixNetLaneDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixTransportLineDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+FixContentPrerequisiteDataJob`  
- `Game.Serialization.SecondaryPrefabReferencesSystem+TypeHandle`  


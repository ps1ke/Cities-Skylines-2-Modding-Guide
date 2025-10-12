# Game.Serialization.BeginPrefabSerializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  
- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Unity.Entities.EntityQuery m_EnabledPrefabsQuery`  
- `private Unity.Entities.EntityQuery m_LoadedPrefabsQuery`  
- `private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public BeginPrefabSerializationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.BeginPrefabSerializationSystem+BeginPrefabSerializationJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+CheckSavedPrefabsJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+SetPrefabDataIndexJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+TypeHandle`  


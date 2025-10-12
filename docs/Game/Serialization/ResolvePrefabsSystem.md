# Game.Serialization.ResolvePrefabsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  
- `private Unity.Entities.EntityQuery m_ActualPrefabQuery`  
- `private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery`  
- `private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery`  
- `private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery`  
- `private Unity.Entities.EntityQuery m_LoadedZoneCellQuery`  
- `private Unity.Entities.EntityQuery m_ActualBudgetQuery`  
- `private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ResolvePrefabsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddOrRemoveComponent(Game.Serialization.ResolvePrefabsSystem+ComponentModification componentModification, Game.Prefabs.PrefabComponents mask, Unity.Entities.ComponentType type) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Serialization.ResolvePrefabsSystem+ComponentModification`  
- `Game.Serialization.ResolvePrefabsSystem+FillLoadedPrefabsJob`  
- `Game.Serialization.ResolvePrefabsSystem+CheckActualPrefabsJob`  
- `Game.Serialization.ResolvePrefabsSystem+CopyBudgetDataJob`  
- `Game.Serialization.ResolvePrefabsSystem+FillZoneTypeArrayJob`  
- `Game.Serialization.ResolvePrefabsSystem+FixZoneTypeJob`  
- `Game.Serialization.ResolvePrefabsSystem+TypeHandle`  


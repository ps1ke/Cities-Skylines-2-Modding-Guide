# Game.Prefabs.AreaInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_SubAreaQuery`  
- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  
- `private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AreaInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private InitializeAreaPrefabs() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ValidateSubAreas() : System.Void`  

## Nested types

- `Game.Prefabs.AreaInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.AreaInitializeSystem+ValidateSubAreasJob`  
- `Game.Prefabs.AreaInitializeSystem+TypeHandle`  


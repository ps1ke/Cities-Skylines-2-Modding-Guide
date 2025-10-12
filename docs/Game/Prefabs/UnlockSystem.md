# Game.Prefabs.UnlockSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_LockedQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private System.Boolean m_Loaded`  
- `private Colossal.Logging.ILog m_Log`  
- `private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle`  

## Constructors

- `public UnlockSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public IsLocked(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessEvents() : System.Boolean`  
- `private UnlockPrefab(Unity.Entities.Entity unlock, System.Boolean createEvent) : System.Void`  

## Nested types

- `Game.Prefabs.UnlockSystem+CheckUnlockRequirementsJob`  
- `Game.Prefabs.UnlockSystem+TypeHandle`  


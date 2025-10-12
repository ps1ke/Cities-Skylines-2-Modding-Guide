# Game.Prefabs.ZoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_ZonePrefabs`  
- `private System.Int32 m_ZoneFillColors`  
- `private System.Int32 m_ZoneEdgeColors`  
- `private System.Boolean m_IsEditorMode`  
- `private System.Boolean m_UpdateColors`  
- `private System.Boolean m_RemovedZones`  
- `private UnityEngine.Vector4[] m_FillColorArray`  
- `private UnityEngine.Vector4[] m_EdgeColorArray`  
- `private Unity.Jobs.JobHandle m_PrefabsReaders`  
- `private Game.Prefabs.ZoneSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ZoneSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddPrefabsReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `private GetNextIndex() : System.Int32`  
- `public GetPrefab(Game.Zones.ZoneType zoneType) : Unity.Entities.Entity`  
- `public GetPrefabs() : Game.Prefabs.ZonePrefabs`  
- `private GetZoneColors(UnityEngine.Color color, UnityEngine.Color& occupied, UnityEngine.Color& selected) : System.Void`  
- `private InitializeZonePrefabs() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdateZoneColors() : System.Void`  
- `private UpdateZoneColors(Game.Prefabs.ZonePrefab zonePrefab, Game.Prefabs.ZoneData zoneData) : System.Void`  

## Nested types

- `Game.Prefabs.ZoneSystem+TypeHandle`  


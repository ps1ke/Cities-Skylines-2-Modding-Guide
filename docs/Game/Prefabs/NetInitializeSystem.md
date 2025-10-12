# Game.Prefabs.NetInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_LaneQuery`  
- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  
- `private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData`  
- `private Unity.Jobs.JobHandle m_PathfindHeuristicDeps`  
- `private Game.Net.Layer m_InGameLayersOnce`  
- `private Game.Net.Layer m_InGameLayersTwice`  
- `private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NetInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddSections(Game.Prefabs.PrefabBase prefab, Game.Prefabs.NetSectionInfo[] source, Unity.Entities.DynamicBuffer<Game.Prefabs.NetGeometrySection> target, Game.Prefabs.NetSectionFlags flags) : System.Void`  
- `public CanReplace(Game.Prefabs.NetData netData, System.Boolean inGame) : System.Boolean`  
- `public GetHeuristicData() : Game.Pathfind.PathfindHeuristicData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.NetInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.NetInitializeSystem+InitializeNetDefaultsJob`  
- `Game.Prefabs.NetInitializeSystem+CollectPathfindDataJob`  
- `Game.Prefabs.NetInitializeSystem+TypeHandle`  


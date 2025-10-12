# Game.Net.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedNetsQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  
- `private Unity.Entities.EntityQuery m_AllNetsQuery`  
- `private Unity.Entities.EntityQuery m_AllLanesQuery`  
- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree`  
- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_LaneSearchTree`  
- `private Unity.Jobs.JobHandle m_NetReadDependencies`  
- `private Unity.Jobs.JobHandle m_NetWriteDependencies`  
- `private Unity.Jobs.JobHandle m_LaneReadDependencies`  
- `private Unity.Jobs.JobHandle m_LaneWriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.SearchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SearchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddLaneSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddLaneSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNetSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNetSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public GetLaneSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  
- `public static GetLayers(Game.Common.Owner owner, Game.Net.UtilityLane utilityLane, Game.Prefabs.MeshLayer defaultLayers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas) : Game.Prefabs.MeshLayer`  
- `private GetLoaded() : System.Boolean`  
- `public GetNetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  
- `public static IsNetOwnerPipeline(Game.Common.Owner owner, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.NetGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netGeometryDatas) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Net.SearchSystem+UpdateNetSearchTreeJob`  
- `Game.Net.SearchSystem+UpdateLaneSearchTreeJob`  
- `Game.Net.SearchSystem+TypeHandle`  


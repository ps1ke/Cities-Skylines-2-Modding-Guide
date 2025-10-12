# Game.Net.SearchSystem+UpdateLaneSearchTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Overridden> m_OverriddenType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Net.UtilityLane> m_UtilityLaneType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetData> m_PrefabNetData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetGeometryData> m_PrefabNetGeometryData`  
- `public System.Boolean m_EditorMode`  
- `public System.Boolean m_Loaded`  
- `public Game.Net.UtilityTypes m_DilatedUtilityTypes`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  


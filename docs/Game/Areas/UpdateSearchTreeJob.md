# Game.Areas.SearchSystem+UpdateSearchTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_NodeType`  
- `public Unity.Entities.BufferTypeHandle<Game.Areas.Triangle> m_TriangleType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Batch> m_BatchType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData`  
- `public System.Boolean m_Loaded`  
- `public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  
- `public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  


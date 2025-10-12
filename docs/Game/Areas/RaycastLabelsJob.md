# Game.Areas.RaycastJobs+RaycastLabelsJob

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Mathematics.float3 m_CameraRight`  
- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_GeometryType`  
- `public Unity.Entities.BufferTypeHandle<Game.Areas.LabelExtents> m_LabelExtentsType`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  


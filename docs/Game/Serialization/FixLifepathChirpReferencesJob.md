# Game.Serialization.LifepathEntrySystem+FixLifepathChirpReferencesJob

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityTypeHandle`  
- `public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType`  
- `public Unity.Entities.BufferLookup<Game.Triggers.LifePathEntry> m_EntryDatas`  
- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

## Methods

- `private Contains(Unity.Entities.DynamicBuffer<Game.Triggers.LifePathEntry> entries, Unity.Entities.Entity chirp) : System.Boolean`  
- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  


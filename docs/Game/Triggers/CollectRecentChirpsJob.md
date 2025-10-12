# Game.Triggers.CreateChirpSystem+CollectRecentChirpsJob

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ChirpData> m_ChirpDatas`  
- `public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_RecentChirps`  
- `public System.UInt32 m_SimulationFrame`  

## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  
- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  


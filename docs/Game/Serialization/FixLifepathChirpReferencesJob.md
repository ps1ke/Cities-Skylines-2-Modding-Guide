# Game.Serialization.LifepathEntrySystem+FixLifepathChirpReferencesJob

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

## Code

```csharp
public sealed struct FixLifepathChirpReferencesJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityTypeHandle;
    public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType;
    public Unity.Entities.BufferLookup<Game.Triggers.LifePathEntry> m_EntryDatas;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;

    private System.Boolean Contains(Unity.Entities.DynamicBuffer<Game.Triggers.LifePathEntry> entries, Unity.Entities.Entity chirp);
    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityTypeHandle`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityTypeHandle;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType;
```

- `public Unity.Entities.BufferLookup<Game.Triggers.LifePathEntry> m_EntryDatas`  

```csharp
public Unity.Entities.BufferLookup<Game.Triggers.LifePathEntry> m_EntryDatas;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```


## Methods

- `private Contains(Unity.Entities.DynamicBuffer<Game.Triggers.LifePathEntry> entries, Unity.Entities.Entity chirp) : System.Boolean`  

```csharp
private System.Boolean Contains(Unity.Entities.DynamicBuffer<Game.Triggers.LifePathEntry> entries, Unity.Entities.Entity chirp);
```

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```



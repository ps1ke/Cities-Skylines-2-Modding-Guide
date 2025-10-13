# Game.Triggers.CreateChirpSystem+CollectRecentChirpsJob

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CollectRecentChirpsJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
    public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ChirpData> m_ChirpDatas;
    public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_RecentChirps;
    public System.UInt32 m_SimulationFrame;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Triggers.Chirp> m_ChirpType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ChirpData> m_ChirpDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ChirpData> m_ChirpDatas;
```

- `public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_RecentChirps`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_RecentChirps;
```

- `public System.UInt32 m_SimulationFrame`  

```csharp
public System.UInt32 m_SimulationFrame;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```



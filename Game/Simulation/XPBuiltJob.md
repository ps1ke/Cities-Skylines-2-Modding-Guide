# Game.Simulation.XPBuiltSystem+XPBuiltJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct XPBuiltJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PlaceableObjectDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SignatureBuildingData> m_SignatureBuildingDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PlacedSignatureBuildingData> m_PlacedSignatureBuildingDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ServiceUpgradeData> m_ServiceUpgradeDatas;
    public Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PlaceableObjectDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableObjectData> m_PlaceableObjectDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SignatureBuildingData> m_SignatureBuildingDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SignatureBuildingData> m_SignatureBuildingDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PlacedSignatureBuildingData> m_PlacedSignatureBuildingDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PlacedSignatureBuildingData> m_PlacedSignatureBuildingDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ServiceUpgradeData> m_ServiceUpgradeDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ServiceUpgradeData> m_ServiceUpgradeDatas;
```

- `public Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
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



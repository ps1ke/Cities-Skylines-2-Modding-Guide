# Game.Tools.FindOwnersSystem+SetSubEntityOwnerJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct SetSubEntityOwnerJob : Unity.Entities.IJobChunk
{
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_OwnerChunks;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.OwnerDefinition> m_OwnerDefinitionType;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_OwnerChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_OwnerChunks;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_CurveType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.OwnerDefinition> m_OwnerDefinitionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.OwnerDefinition> m_OwnerDefinitionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
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



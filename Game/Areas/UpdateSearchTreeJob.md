# Game.Areas.SearchSystem+UpdateSearchTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateSearchTreeJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_NodeType;
    public Unity.Entities.BufferTypeHandle<Game.Areas.Triangle> m_TriangleType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.Batch> m_BatchType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
    public System.Boolean m_Loaded;
    public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_NodeType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_NodeType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Areas.Triangle> m_TriangleType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Areas.Triangle> m_TriangleType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Batch> m_BatchType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.Batch> m_BatchType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
```

- `public System.Boolean m_Loaded`  

```csharp
public System.Boolean m_Loaded;
```

- `public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount;
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



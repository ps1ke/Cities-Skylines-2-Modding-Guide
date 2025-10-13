# Game.Routes.SearchSystem+UpdateSearchTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateSearchTreeJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Routes.Position> m_PositionType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathUpdated> m_PathUpdatedType;
    public Unity.Entities.BufferTypeHandle<Game.Routes.CurveElement> m_CurveElementType;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData;
    public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData;
    public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_DeletedData;
    public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements;
    public System.Boolean m_Loaded;
    public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void UpdateSegment(Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.CurveElement> curveElements);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Routes.Position> m_PositionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Routes.Position> m_PositionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Created> m_CreatedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Deleted> m_DeletedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathUpdated> m_PathUpdatedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathUpdated> m_PathUpdatedType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Routes.CurveElement> m_CurveElementType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Routes.CurveElement> m_CurveElementType;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.RouteData> m_PrefabRouteData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_DeletedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_DeletedData;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.Segment> m_SegmentData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Routes.CurveElement> m_CurveElements;
```

- `public System.Boolean m_Loaded`  

```csharp
public System.Boolean m_Loaded;
```

- `public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount;
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

- `private UpdateSegment(Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.CurveElement> curveElements) : System.Void`  

```csharp
private System.Void UpdateSegment(Unity.Entities.Entity entity, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.CurveElement> curveElements);
```



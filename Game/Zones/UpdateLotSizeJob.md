# Game.Zones.LotSizeJobs+UpdateLotSizeJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateLotSizeJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
    public Game.Prefabs.ZonePrefabs m_ZonePrefabs;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;
    public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData;
    public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData;
    public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
    public Unity.Entities.BufferLookup<Game.Zones.VacantLot> m_VacantLots;
    public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
    public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue;

    public System.Void Execute(System.Int32 index);
    private Unity.Collections.NativeArray<Game.Zones.Cell> ExpandArea(Unity.Entities.Entity entity, Game.Zones.Block block, Game.Zones.ValidArea validArea, Game.Zones.BuildOrder buildOrder, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& expandedOffset, Game.Zones.Block& expandedBlock);
    private System.Void ExpandLeft(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone);
    private System.Void ExpandRight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone);
    private System.Void FindDepth(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone);
    private System.Void FindHeight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Int32& height);
    private System.Void WidthReductionLeft(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset);
    private System.Void WidthReductionRight(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  

```csharp
public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
```

- `public Game.Prefabs.ZonePrefabs m_ZonePrefabs`  

```csharp
public Game.Prefabs.ZonePrefabs m_ZonePrefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData;
```

- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
```

- `public Unity.Entities.BufferLookup<Game.Zones.VacantLot> m_VacantLots`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.VacantLot> m_VacantLots;
```

- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer;
```

- `public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue`  

```csharp
public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```

- `private ExpandArea(Unity.Entities.Entity entity, Game.Zones.Block block, Game.Zones.ValidArea validArea, Game.Zones.BuildOrder buildOrder, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& expandedOffset, Game.Zones.Block& expandedBlock) : Unity.Collections.NativeArray<Game.Zones.Cell>`  

```csharp
private Unity.Collections.NativeArray<Game.Zones.Cell> ExpandArea(Unity.Entities.Entity entity, Game.Zones.Block block, Game.Zones.ValidArea validArea, Game.Zones.BuildOrder buildOrder, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& expandedOffset, Game.Zones.Block& expandedBlock);
```

- `private ExpandLeft(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone) : System.Void`  

```csharp
private System.Void ExpandLeft(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone);
```

- `private ExpandRight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone) : System.Void`  

```csharp
private System.Void ExpandRight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone);
```

- `private FindDepth(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone) : System.Void`  

```csharp
private System.Void FindDepth(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone);
```

- `private FindHeight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Int32& height) : System.Void`  

```csharp
private System.Void FindHeight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Int32& height);
```

- `private WidthReductionLeft(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset) : System.Void`  

```csharp
private System.Void WidthReductionLeft(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset);
```

- `private WidthReductionRight(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset) : System.Void`  

```csharp
private System.Void WidthReductionRight(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset);
```


## Nested types

- `Game.Zones.LotSizeJobs+UpdateLotSizeJob+Iterator`  


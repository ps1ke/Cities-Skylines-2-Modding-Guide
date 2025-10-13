# Game.Zones.CellCheckHelpers+FindOverlappingBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct FindOverlappingBlocksJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;
    public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData;
    public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_ResultQueue;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  

```csharp
public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
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

- `public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_ResultQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_ResultQueue;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```


## Nested types

- `Game.Zones.CellCheckHelpers+FindOverlappingBlocksJob+Iterator`  


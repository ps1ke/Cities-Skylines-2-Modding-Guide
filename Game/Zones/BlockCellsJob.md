# Game.Zones.CellBlockJobs+BlockCellsJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct BlockCellsJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree;
    public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_AreaSearchTree;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Net.EdgeGeometry> m_EdgeGeometryData;
    public Unity.Entities.ComponentLookup<Game.Net.StartNodeGeometry> m_StartNodeGeometryData;
    public Unity.Entities.ComponentLookup<Game.Net.EndNodeGeometry> m_EndNodeGeometryData;
    public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.RoadComposition> m_PrefabRoadCompositionData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Common.Native> m_NativeData;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
    public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles;
    public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
    public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;

    private static System.Void CleanBlockedCells(Game.Zones.Block blockData, Game.Zones.ValidArea& validAreaData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells);
    private static System.Void ClearBlockStatus(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells);
    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  

```csharp
public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_NetSearchTree;
```

- `public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_AreaSearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_AreaSearchTree;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.EdgeGeometry> m_EdgeGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.EdgeGeometry> m_EdgeGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.StartNodeGeometry> m_StartNodeGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.StartNodeGeometry> m_StartNodeGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.EndNodeGeometry> m_EndNodeGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.EndNodeGeometry> m_EndNodeGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_PrefabCompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.RoadComposition> m_PrefabRoadCompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.RoadComposition> m_PrefabRoadCompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> m_PrefabAreaGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Native> m_NativeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Native> m_NativeData;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangles;
```

- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;
```


## Methods

- `private static CleanBlockedCells(Game.Zones.Block blockData, Game.Zones.ValidArea& validAreaData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells) : System.Void`  

```csharp
private static System.Void CleanBlockedCells(Game.Zones.Block blockData, Game.Zones.ValidArea& validAreaData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells);
```

- `private static ClearBlockStatus(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells) : System.Void`  

```csharp
private static System.Void ClearBlockStatus(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells);
```

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```


## Nested types

- `Game.Zones.CellBlockJobs+BlockCellsJob+NetIterator`  
- `Game.Zones.CellBlockJobs+BlockCellsJob+AreaIterator`  


# Game.Zones.CellOverlapJobs+CheckBlockOverlapJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CheckBlockOverlapJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps;
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups;
    public Game.Prefabs.ZonePrefabs m_ZonePrefabs;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData;
    public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
    public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps`  

```csharp
public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps;
```

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups`  

```csharp
public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups;
```

- `public Game.Prefabs.ZonePrefabs m_ZonePrefabs`  

```csharp
public Game.Prefabs.ZonePrefabs m_ZonePrefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData;
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

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```


## Nested types

- `Game.Zones.CellOverlapJobs+CheckBlockOverlapJob+CellReduction`  
- `Game.Zones.CellOverlapJobs+CheckBlockOverlapJob+OverlapIterator`  


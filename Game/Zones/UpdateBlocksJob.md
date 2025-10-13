# Game.Zones.CellCheckHelpers+UpdateBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateBlocksJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;

    public System.Void Execute(System.Int32 index);
    private System.Void SetVisible(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells);
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

- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```

- `private SetVisible(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells) : System.Void`  

```csharp
private System.Void SetVisible(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells);
```



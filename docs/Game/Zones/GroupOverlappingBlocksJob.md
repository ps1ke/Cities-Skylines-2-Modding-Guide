# Game.Zones.CellCheckHelpers+GroupOverlappingBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct GroupOverlappingBlocksJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
    public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_OverlapQueue;
    public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps;
    public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups;

    private System.Int32 CreateGroup(Unity.Collections.NativeList<System.Int32> groups);
    public System.Void Execute();
    private System.Int32 MergeGroups(Unity.Collections.NativeList<System.Int32> groups, System.Int32 group1, System.Int32 group2);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  

```csharp
public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks;
```

- `public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_OverlapQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_OverlapQueue;
```

- `public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps`  

```csharp
public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps;
```

- `public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups`  

```csharp
public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups;
```


## Methods

- `private CreateGroup(Unity.Collections.NativeList<System.Int32> groups) : System.Int32`  

```csharp
private System.Int32 CreateGroup(Unity.Collections.NativeList<System.Int32> groups);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private MergeGroups(Unity.Collections.NativeList<System.Int32> groups, System.Int32 group1, System.Int32 group2) : System.Int32`  

```csharp
private System.Int32 MergeGroups(Unity.Collections.NativeList<System.Int32> groups, System.Int32 group1, System.Int32 group2);
```



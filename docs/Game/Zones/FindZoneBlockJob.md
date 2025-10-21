# Game.Zones.RaycastJobs+FindZoneBlockJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct FindZoneBlockJob : Unity.Jobs.IJobParallelFor
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
    public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
    public Unity.Collections.NativeArray<Game.Common.RaycastResult> m_TerrainResults;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData;
```

- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

```csharp
public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
```

- `public Unity.Collections.NativeArray<Game.Common.RaycastResult> m_TerrainResults`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastResult> m_TerrainResults;
```

- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

```csharp
public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```


## Nested types

- `Game.Zones.RaycastJobs+FindZoneBlockJob+Iterator`  


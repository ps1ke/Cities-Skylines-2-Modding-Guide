# Game.Zones.CellCheckHelpers+FindUpdatedBlocksDoubleIterationJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct FindUpdatedBlocksDoubleIterationJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> m_Bounds;
    public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ResultQueue;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> m_Bounds`  

```csharp
public Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> m_Bounds;
```

- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree;
```

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ResultQueue`  

```csharp
public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ResultQueue;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```


## Nested types

- `Game.Zones.CellCheckHelpers+FindUpdatedBlocksDoubleIterationJob+FirstIterator`  
- `Game.Zones.CellCheckHelpers+FindUpdatedBlocksDoubleIterationJob+SecondIterator`  


# Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct GroundWaterReservoirJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeArray<Game.Simulation.GroundWater> m_GroundWaterMap;
    public Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, System.Int32> m_PumpCapacityMap;
    public Unity.Collections.NativeList<Unity.Mathematics.int2> m_TempGroundWaterPumpCells;
    public Unity.Collections.NativeQueue<Unity.Mathematics.int2> m_Queue;
    public Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_Result;

    private System.Void EnqueueIfUnprocessed(Unity.Mathematics.int2 cell, Unity.Collections.NativeParallelHashSet<Unity.Mathematics.int2> processedCells);
    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Simulation.GroundWater> m_GroundWaterMap`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.GroundWater> m_GroundWaterMap;
```

- `public Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, System.Int32> m_PumpCapacityMap`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, System.Int32> m_PumpCapacityMap;
```

- `public Unity.Collections.NativeList<Unity.Mathematics.int2> m_TempGroundWaterPumpCells`  

```csharp
public Unity.Collections.NativeList<Unity.Mathematics.int2> m_TempGroundWaterPumpCells;
```

- `public Unity.Collections.NativeQueue<Unity.Mathematics.int2> m_Queue`  

```csharp
public Unity.Collections.NativeQueue<Unity.Mathematics.int2> m_Queue;
```

- `public Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_Result`  

```csharp
public Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_Result;
```


## Methods

- `private EnqueueIfUnprocessed(Unity.Mathematics.int2 cell, Unity.Collections.NativeParallelHashSet<Unity.Mathematics.int2> processedCells) : System.Void`  

```csharp
private System.Void EnqueueIfUnprocessed(Unity.Mathematics.int2 cell, Unity.Collections.NativeParallelHashSet<Unity.Mathematics.int2> processedCells);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```



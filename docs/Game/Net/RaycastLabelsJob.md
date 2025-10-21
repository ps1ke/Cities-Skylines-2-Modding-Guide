# Game.Net.RaycastJobs+RaycastLabelsJob

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct RaycastLabelsJob : Unity.Jobs.IJobParallelForDefer
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Mathematics.float3 m_CameraRight;
    public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Edges;
    public Unity.Entities.ComponentLookup<Game.Net.Aggregated> m_AggregatedData;
    public Unity.Entities.ComponentLookup<Game.Net.LabelExtents> m_LabelExtentsData;
    public Unity.Entities.BufferLookup<Game.Net.LabelPosition> m_LabelPositions;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    private System.Void CheckAggregate(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity aggregate);
    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Mathematics.float3 m_CameraRight`  

```csharp
public Unity.Mathematics.float3 m_CameraRight;
```

- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Edges`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Edges;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Aggregated> m_AggregatedData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Aggregated> m_AggregatedData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LabelExtents> m_LabelExtentsData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LabelExtents> m_LabelExtentsData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LabelPosition> m_LabelPositions`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LabelPosition> m_LabelPositions;
```

- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

```csharp
public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;
```


## Methods

- `private CheckAggregate(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity aggregate) : System.Void`  

```csharp
private System.Void CheckAggregate(System.Int32 raycastIndex, Game.Common.RaycastInput input, Unity.Entities.Entity aggregate);
```

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```



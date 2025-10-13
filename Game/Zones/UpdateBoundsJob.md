# Game.Zones.LotSizeJobs+UpdateBoundsJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateBoundsJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue;
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_BoundsList;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue`  

```csharp
public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue;
```

- `public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_BoundsList`  

```csharp
public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_BoundsList;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```



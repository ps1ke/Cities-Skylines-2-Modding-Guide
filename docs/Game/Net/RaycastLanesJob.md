# Game.Net.RaycastJobs+RaycastLanesJob

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct RaycastLanesJob : Unity.Jobs.IJobParallelForDefer
{
    public System.Single m_FovTan;
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Lanes;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public System.Single m_FovTan`  

```csharp
public System.Single m_FovTan;
```

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Lanes`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastSystem+EntityResult> m_Lanes;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.UtilityLaneData> m_PrefabUtilityLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneGeometryData> m_PrefabLaneGeometryData;
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



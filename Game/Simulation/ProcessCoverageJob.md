# Game.Simulation.ServiceCoverageSystem+ProcessCoverageJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ProcessCoverageJob : Unity.Jobs.IJobParallelForDefer
{
    public System.Int32 m_CoverageIndex;
    public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData;
    public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.Density> m_DensityData;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    public Unity.Entities.ComponentLookup<Game.Buildings.ModifiedServiceCoverage> m_ModifiedServiceCoverageData;
    public Unity.Entities.ComponentLookup<Game.Areas.BorderDistrict> m_BorderDistrictData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData;
    public Unity.Entities.BufferLookup<Game.Pathfind.CoverageElement> m_CoverageElements;
    public Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies;
    public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_CoverageData;

    public System.Void Execute(System.Int32 index);
}
```


## Fields

- `public System.Int32 m_CoverageIndex`  

```csharp
public System.Int32 m_CoverageIndex;
```

- `public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+BuildingData> m_BuildingData;
```

- `public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.ServiceCoverageSystem+CoverageElement> m_Elements;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Density> m_DensityData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Density> m_DensityData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.ModifiedServiceCoverage> m_ModifiedServiceCoverageData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.ModifiedServiceCoverage> m_ModifiedServiceCoverageData;
```

- `public Unity.Entities.ComponentLookup<Game.Areas.BorderDistrict> m_BorderDistrictData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Areas.BorderDistrict> m_BorderDistrictData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CoverageData> m_PrefabCoverageData;
```

- `public Unity.Entities.BufferLookup<Game.Pathfind.CoverageElement> m_CoverageElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Pathfind.CoverageElement> m_CoverageElements;
```

- `public Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies;
```

- `public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_CoverageData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_CoverageData;
```


## Methods

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```



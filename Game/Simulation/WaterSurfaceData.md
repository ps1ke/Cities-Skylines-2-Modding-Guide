# Game.Simulation.WaterSurfaceData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct WaterSurfaceData
{
    private Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> <depths>k__BackingField;
    private Unity.Mathematics.int3 <resolution>k__BackingField;
    private Unity.Mathematics.float3 <scale>k__BackingField;
    private Unity.Mathematics.float3 <offset>k__BackingField;

    public Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> depths { get; private set; }
    public Unity.Mathematics.int3 resolution { get; private set; }
    public Unity.Mathematics.float3 scale { get; private set; }
    public Unity.Mathematics.float3 offset { get; private set; }
    public System.Boolean isCreated { get; }

    public WaterSurfaceData(Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> _depths, Unity.Mathematics.int3 _resolution, Unity.Mathematics.float3 _scale, Unity.Mathematics.float3 _offset);

}
```


## Fields

- `private Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> <depths>k__BackingField`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> <depths>k__BackingField;
```

- `private Unity.Mathematics.int3 <resolution>k__BackingField`  

```csharp
private Unity.Mathematics.int3 <resolution>k__BackingField;
```

- `private Unity.Mathematics.float3 <scale>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <scale>k__BackingField;
```

- `private Unity.Mathematics.float3 <offset>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <offset>k__BackingField;
```


## Properties

- `public Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> depths { get; private set }`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> depths { get; private set; }
```

- `public Unity.Mathematics.int3 resolution { get; private set }`  

```csharp
public Unity.Mathematics.int3 resolution { get; private set; }
```

- `public Unity.Mathematics.float3 scale { get; private set }`  

```csharp
public Unity.Mathematics.float3 scale { get; private set; }
```

- `public Unity.Mathematics.float3 offset { get; private set }`  

```csharp
public Unity.Mathematics.float3 offset { get; private set; }
```

- `public System.Boolean isCreated { get }`  

```csharp
public System.Boolean isCreated { get; }
```


## Constructors

- `public WaterSurfaceData(Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> _depths, Unity.Mathematics.int3 _resolution, Unity.Mathematics.float3 _scale, Unity.Mathematics.float3 _offset)`  

```csharp
public WaterSurfaceData(Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> _depths, Unity.Mathematics.int3 _resolution, Unity.Mathematics.float3 _scale, Unity.Mathematics.float3 _offset);
```



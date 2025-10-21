# Game.Simulation.WaterUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class WaterUtils
{
    public static System.Single GetSampleInterval(Game.Simulation.WaterSurfaceData& data);
    public static System.Single GetSurfaceDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition);
    public static Unity.Mathematics.float3 GetWorldPosition(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition);
    public static System.Boolean Raycast(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t);
    private static System.Boolean RaycastCell(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, Unity.Mathematics.float2 terrainToWaterSpace, Unity.Mathematics.int2 waterToTerrainFactor, System.Boolean outside, System.Single& t);
    public static System.Single SampleDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
    public static System.Single SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition);
    public static System.Single SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& waterDepth);
    public static System.Void SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& terrainHeight, System.Single& waterHeight, System.Single& waterDepth);
    public static System.Single SamplePolluted(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
    public static Unity.Mathematics.float2 SampleVelocity(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
    public static Unity.Mathematics.float3 ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
    public static Colossal.Mathematics.Line3+Segment ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Colossal.Mathematics.Line3+Segment worldLine);
    public static Unity.Mathematics.float3 ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 surfacePosition);
    public static Unity.Mathematics.float2 ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float2 surfaceVelocity);
    public static System.Single ToWorldSpace(Game.Simulation.WaterSurfaceData& data, System.Single surfaceDepth);
}
```


## Methods

- `public static GetSampleInterval(Game.Simulation.WaterSurfaceData& data) : System.Single`  

```csharp
public static System.Single GetSampleInterval(Game.Simulation.WaterSurfaceData& data);
```

- `public static GetSurfaceDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition) : System.Single`  

```csharp
public static System.Single GetSurfaceDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition);
```

- `public static GetWorldPosition(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetWorldPosition(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition);
```

- `public static Raycast(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t) : System.Boolean`  

```csharp
public static System.Boolean Raycast(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t);
```

- `private static RaycastCell(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, Unity.Mathematics.float2 terrainToWaterSpace, Unity.Mathematics.int2 waterToTerrainFactor, System.Boolean outside, System.Single& t) : System.Boolean`  

```csharp
private static System.Boolean RaycastCell(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, Unity.Mathematics.float2 terrainToWaterSpace, Unity.Mathematics.int2 waterToTerrainFactor, System.Boolean outside, System.Single& t);
```

- `public static SampleDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static System.Single SampleDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
```

- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static System.Single SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition);
```

- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& waterDepth) : System.Single`  

```csharp
public static System.Single SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& waterDepth);
```

- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& terrainHeight, System.Single& waterHeight, System.Single& waterDepth) : System.Void`  

```csharp
public static System.Void SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& terrainHeight, System.Single& waterHeight, System.Single& waterDepth);
```

- `public static SamplePolluted(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static System.Single SamplePolluted(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
```

- `public static SampleVelocity(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 SampleVelocity(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
```

- `public static ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition);
```

- `public static ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Colossal.Mathematics.Line3+Segment worldLine) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Colossal.Mathematics.Line3+Segment worldLine);
```

- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 surfacePosition) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 surfacePosition);
```

- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float2 surfaceVelocity) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float2 surfaceVelocity);
```

- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, System.Single surfaceDepth) : System.Single`  

```csharp
public static System.Single ToWorldSpace(Game.Simulation.WaterSurfaceData& data, System.Single surfaceDepth);
```



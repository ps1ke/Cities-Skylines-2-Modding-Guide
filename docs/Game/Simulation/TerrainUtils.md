# Game.Simulation.TerrainUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TerrainUtils
{
    public static Colossal.Mathematics.Bounds3 GetBounds(Game.Simulation.TerrainHeightData& data);
    public static Colossal.Mathematics.Bounds3 GetEditorCameraBounds(Game.Simulation.TerrainSystem terrainSystem, Game.Simulation.TerrainHeightData& data);
    public static Colossal.Mathematics.Bounds1 GetHeightRange(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Bounds3 worldBounds);
    public static System.Boolean Raycast(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal);
    private static System.Boolean RaycastCell(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal);
    public static System.Single SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition);
    public static System.Single SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition, Unity.Mathematics.float3& normal);
    public static Unity.Mathematics.float3 ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition);
    public static Colossal.Mathematics.Line3+Segment ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine);
    public static System.Single ToWorldSpace(Game.Simulation.TerrainHeightData& data, System.Single heightmapHeight);
}
```


## Methods

- `public static GetBounds(Game.Simulation.TerrainHeightData& data) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 GetBounds(Game.Simulation.TerrainHeightData& data);
```

- `public static GetEditorCameraBounds(Game.Simulation.TerrainSystem terrainSystem, Game.Simulation.TerrainHeightData& data) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 GetEditorCameraBounds(Game.Simulation.TerrainSystem terrainSystem, Game.Simulation.TerrainHeightData& data);
```

- `public static GetHeightRange(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Bounds3 worldBounds) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 GetHeightRange(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Bounds3 worldBounds);
```

- `public static Raycast(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal) : System.Boolean`  

```csharp
public static System.Boolean Raycast(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal);
```

- `private static RaycastCell(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal) : System.Boolean`  

```csharp
private static System.Boolean RaycastCell(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal);
```

- `public static SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static System.Single SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition);
```

- `public static SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition, Unity.Mathematics.float3& normal) : System.Single`  

```csharp
public static System.Single SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition, Unity.Mathematics.float3& normal);
```

- `public static ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition);
```

- `public static ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine);
```

- `public static ToWorldSpace(Game.Simulation.TerrainHeightData& data, System.Single heightmapHeight) : System.Single`  

```csharp
public static System.Single ToWorldSpace(Game.Simulation.TerrainHeightData& data, System.Single heightmapHeight);
```



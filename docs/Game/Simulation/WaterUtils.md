# Game.Simulation.WaterUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static GetSampleInterval(Game.Simulation.WaterSurfaceData& data) : System.Single`  
- `public static GetSurfaceDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition) : System.Single`  
- `public static GetWorldPosition(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition) : Unity.Mathematics.float3`  
- `public static Raycast(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t) : System.Boolean`  
- `private static RaycastCell(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, Unity.Mathematics.float2 terrainToWaterSpace, Unity.Mathematics.int2 waterToTerrainFactor, System.Boolean outside, System.Single& t) : System.Boolean`  
- `public static SampleDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  
- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition) : System.Single`  
- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& waterDepth) : System.Single`  
- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& terrainHeight, System.Single& waterHeight, System.Single& waterDepth) : System.Void`  
- `public static SamplePolluted(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  
- `public static SampleVelocity(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float2`  
- `public static ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float3`  
- `public static ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Colossal.Mathematics.Line3+Segment worldLine) : Colossal.Mathematics.Line3+Segment`  
- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 surfacePosition) : Unity.Mathematics.float3`  
- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float2 surfaceVelocity) : Unity.Mathematics.float2`  
- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, System.Single surfaceDepth) : System.Single`  


# Game.Simulation.TerrainUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static GetBounds(Game.Simulation.TerrainHeightData& data) : Colossal.Mathematics.Bounds3`  
- `public static GetEditorCameraBounds(Game.Simulation.TerrainSystem terrainSystem, Game.Simulation.TerrainHeightData& data) : Colossal.Mathematics.Bounds3`  
- `public static GetHeightRange(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Bounds3 worldBounds) : Colossal.Mathematics.Bounds1`  
- `public static Raycast(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal) : System.Boolean`  
- `private static RaycastCell(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal) : System.Boolean`  
- `public static SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  
- `public static SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition, Unity.Mathematics.float3& normal) : System.Single`  
- `public static ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float3`  
- `public static ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine) : Colossal.Mathematics.Line3+Segment`  
- `public static ToWorldSpace(Game.Simulation.TerrainHeightData& data, System.Single heightmapHeight) : System.Single`  


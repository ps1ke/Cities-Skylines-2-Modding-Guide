# Game.Zones.ZoneUtils

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single CELL_SIZE`  
- `public static const System.Single CELL_AREA`  
- `public static const System.Int32 MAX_ZONE_WIDTH`  
- `public static const System.Int32 MAX_ZONE_DEPTH`  
- `public static const System.Int32 MAX_ZONE_TYPES`  

## Methods

- `public static CalculateBounds(Game.Zones.Block block) : Colossal.Mathematics.Bounds2`  
- `public static CalculateCorners(Game.Zones.Block block) : Colossal.Mathematics.Quad2`  
- `public static CalculateCorners(Game.Zones.Block block, Game.Zones.ValidArea validArea) : Colossal.Mathematics.Quad2`  
- `public static CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2) : System.Boolean`  
- `public static CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2) : System.Boolean`  
- `public static GetCellIndex(Game.Zones.Block block, Unity.Mathematics.float2 position) : Unity.Mathematics.int2`  
- `public static GetCellPosition(Game.Zones.Block block, Unity.Mathematics.int2 cellIndex) : Unity.Mathematics.float3`  
- `public static GetCellWidth(System.Single roadWidth) : System.Int32`  
- `public static GetColorIndex(Game.Zones.CellFlags state, Game.Zones.ZoneType type) : System.Int32`  
- `public static GetPosition(Game.Zones.Block block, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : Unity.Mathematics.float3`  
- `public static GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source) : Game.Zones.CellFlags`  
- `public static GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source, Game.Zones.CellFlags directionFlags) : Game.Zones.CellFlags`  
- `public static GetRotation(Game.Zones.Block block) : Unity.Mathematics.quaternion`  
- `public static IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2) : System.Boolean`  
- `public static IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2) : System.Boolean`  


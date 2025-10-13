# Game.Zones.ZoneUtils

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ZoneUtils
{
    public static const System.Single CELL_SIZE;
    public static const System.Single CELL_AREA;
    public static const System.Int32 MAX_ZONE_WIDTH;
    public static const System.Int32 MAX_ZONE_DEPTH;
    public static const System.Int32 MAX_ZONE_TYPES;

    public static Colossal.Mathematics.Bounds2 CalculateBounds(Game.Zones.Block block);
    public static Colossal.Mathematics.Quad2 CalculateCorners(Game.Zones.Block block);
    public static Colossal.Mathematics.Quad2 CalculateCorners(Game.Zones.Block block, Game.Zones.ValidArea validArea);
    public static System.Boolean CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2);
    public static System.Boolean CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2);
    public static Unity.Mathematics.int2 GetCellIndex(Game.Zones.Block block, Unity.Mathematics.float2 position);
    public static Unity.Mathematics.float3 GetCellPosition(Game.Zones.Block block, Unity.Mathematics.int2 cellIndex);
    public static System.Int32 GetCellWidth(System.Single roadWidth);
    public static System.Int32 GetColorIndex(Game.Zones.CellFlags state, Game.Zones.ZoneType type);
    public static Unity.Mathematics.float3 GetPosition(Game.Zones.Block block, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
    public static Game.Zones.CellFlags GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source);
    public static Game.Zones.CellFlags GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source, Game.Zones.CellFlags directionFlags);
    public static Unity.Mathematics.quaternion GetRotation(Game.Zones.Block block);
    public static System.Boolean IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2);
    public static System.Boolean IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2);
}
```


## Fields

- `public static const System.Single CELL_SIZE`  

```csharp
public static const System.Single CELL_SIZE;
```

- `public static const System.Single CELL_AREA`  

```csharp
public static const System.Single CELL_AREA;
```

- `public static const System.Int32 MAX_ZONE_WIDTH`  

```csharp
public static const System.Int32 MAX_ZONE_WIDTH;
```

- `public static const System.Int32 MAX_ZONE_DEPTH`  

```csharp
public static const System.Int32 MAX_ZONE_DEPTH;
```

- `public static const System.Int32 MAX_ZONE_TYPES`  

```csharp
public static const System.Int32 MAX_ZONE_TYPES;
```


## Methods

- `public static CalculateBounds(Game.Zones.Block block) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 CalculateBounds(Game.Zones.Block block);
```

- `public static CalculateCorners(Game.Zones.Block block) : Colossal.Mathematics.Quad2`  

```csharp
public static Colossal.Mathematics.Quad2 CalculateCorners(Game.Zones.Block block);
```

- `public static CalculateCorners(Game.Zones.Block block, Game.Zones.ValidArea validArea) : Colossal.Mathematics.Quad2`  

```csharp
public static Colossal.Mathematics.Quad2 CalculateCorners(Game.Zones.Block block, Game.Zones.ValidArea validArea);
```

- `public static CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2) : System.Boolean`  

```csharp
public static System.Boolean CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2);
```

- `public static CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2) : System.Boolean`  

```csharp
public static System.Boolean CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2);
```

- `public static GetCellIndex(Game.Zones.Block block, Unity.Mathematics.float2 position) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetCellIndex(Game.Zones.Block block, Unity.Mathematics.float2 position);
```

- `public static GetCellPosition(Game.Zones.Block block, Unity.Mathematics.int2 cellIndex) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellPosition(Game.Zones.Block block, Unity.Mathematics.int2 cellIndex);
```

- `public static GetCellWidth(System.Single roadWidth) : System.Int32`  

```csharp
public static System.Int32 GetCellWidth(System.Single roadWidth);
```

- `public static GetColorIndex(Game.Zones.CellFlags state, Game.Zones.ZoneType type) : System.Int32`  

```csharp
public static System.Int32 GetColorIndex(Game.Zones.CellFlags state, Game.Zones.ZoneType type);
```

- `public static GetPosition(Game.Zones.Block block, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetPosition(Game.Zones.Block block, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max);
```

- `public static GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source) : Game.Zones.CellFlags`  

```csharp
public static Game.Zones.CellFlags GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source);
```

- `public static GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source, Game.Zones.CellFlags directionFlags) : Game.Zones.CellFlags`  

```csharp
public static Game.Zones.CellFlags GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source, Game.Zones.CellFlags directionFlags);
```

- `public static GetRotation(Game.Zones.Block block) : Unity.Mathematics.quaternion`  

```csharp
public static Unity.Mathematics.quaternion GetRotation(Game.Zones.Block block);
```

- `public static IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2) : System.Boolean`  

```csharp
public static System.Boolean IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2);
```

- `public static IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2) : System.Boolean`  

```csharp
public static System.Boolean IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2);
```



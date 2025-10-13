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
public static Bounds2 CalculateBounds(Block block)
	{
		float2 @float = (float2)block.m_Size * 4f;
		float2 float2 = math.abs(block.m_Direction * @float.y) + math.abs(MathUtils.Right(block.m_Direction) * @float.x);
		return new Bounds2(block.m_Position.xz - float2, block.m_Position.xz + float2);
	}
```

- `public static CalculateCorners(Game.Zones.Block block) : Colossal.Mathematics.Quad2`  

```csharp
public static Quad2 CalculateCorners(Block block, ValidArea validArea)
	{
		float4 @float = (float4)(block.m_Size.xxyy - (validArea.m_Area << 1)) * 4f;
		float4 float2 = block.m_Direction.xyxy * @float.zzww;
		float4 float3 = MathUtils.Right(block.m_Direction).xyxy * @float.xxyy;
		float4 float4 = block.m_Position.xzxz + float2;
		float4 float5 = float4.xyxy + float3;
		float4 float6 = float4.zwzw + float3;
		return new Quad2(float5.xy, float5.zw, float6.zw, float6.xy);
	}
```

- `public static CalculateCorners(Game.Zones.Block block, Game.Zones.ValidArea validArea) : Colossal.Mathematics.Quad2`  

```csharp
public static Quad2 CalculateCorners(Block block, ValidArea validArea)
	{
		float4 @float = (float4)(block.m_Size.xxyy - (validArea.m_Area << 1)) * 4f;
		float4 float2 = block.m_Direction.xyxy * @float.zzww;
		float4 float3 = MathUtils.Right(block.m_Direction).xyxy * @float.xxyy;
		float4 float4 = block.m_Position.xzxz + float2;
		float4 float5 = float4.xyxy + float3;
		float4 float6 = float4.zwzw + float3;
		return new Quad2(float5.xy, float5.zw, float6.zw, float6.xy);
	}
```

- `public static CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2) : System.Boolean`  

```csharp
public static bool CanShareCells(Block block1, Block block2)
	{
		float num = math.abs(math.dot(block1.m_Direction, block2.m_Direction));
		if (num > 0.017452406f && num < 0.9998477f)
		{
			return false;
		}
		float2 @float = MathUtils.Right(block1.m_Direction);
		float2 float2 = MathUtils.Right(block2.m_Direction);
		float2 float3 = block2.m_Position.xz - block1.m_Position.xz;
		bool2 @bool = (block1.m_Size & 1) != 0;
		bool2 bool2 = (block2.m_Size & 1) != 0;
		float3 = math.select(float3, float3 - block1.m_Direction * 4f, @bool.y);
		float3 = math.select(float3, float3 + block2.m_Direction * 4f, bool2.y);
		float3 = math.select(float3, float3 - @float * 4f, @bool.x);
		float3 = math.select(float3, float3 + float2 * 4f, bool2.x);
		float2 float4 = default(float2);
		float4.y = math.dot(float3, block1.m_Direction);
		float4.x = math.dot(float3, MathUtils.Right(block1.m_Direction));
		float4 = math.abs(float4 / 8f);
		return math.all(math.abs(math.frac(float4) - 0.5f) >= 0.48f);
	}
```

- `public static CanShareCells(Game.Zones.Block block1, Game.Zones.Block block2) : System.Boolean`  

```csharp
public static bool CanShareCells(Block block1, Block block2)
	{
		float num = math.abs(math.dot(block1.m_Direction, block2.m_Direction));
		if (num > 0.017452406f && num < 0.9998477f)
		{
			return false;
		}
		float2 @float = MathUtils.Right(block1.m_Direction);
		float2 float2 = MathUtils.Right(block2.m_Direction);
		float2 float3 = block2.m_Position.xz - block1.m_Position.xz;
		bool2 @bool = (block1.m_Size & 1) != 0;
		bool2 bool2 = (block2.m_Size & 1) != 0;
		float3 = math.select(float3, float3 - block1.m_Direction * 4f, @bool.y);
		float3 = math.select(float3, float3 + block2.m_Direction * 4f, bool2.y);
		float3 = math.select(float3, float3 - @float * 4f, @bool.x);
		float3 = math.select(float3, float3 + float2 * 4f, bool2.x);
		float2 float4 = default(float2);
		float4.y = math.dot(float3, block1.m_Direction);
		float4.x = math.dot(float3, MathUtils.Right(block1.m_Direction));
		float4 = math.abs(float4 / 8f);
		return math.all(math.abs(math.frac(float4) - 0.5f) >= 0.48f);
	}
```

- `public static GetCellIndex(Game.Zones.Block block, Unity.Mathematics.float2 position) : Unity.Mathematics.int2`  

```csharp
public static int2 GetCellIndex(Block block, float2 position)
	{
		float2 y = MathUtils.Right(block.m_Direction);
		float2 x = block.m_Position.xz - position;
		return (int2)math.floor((new float2(math.dot(x, y), math.dot(x, block.m_Direction)) + (float2)block.m_Size * 4f) / 8f);
	}
```

- `public static GetCellPosition(Game.Zones.Block block, Unity.Mathematics.int2 cellIndex) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellPosition(Block block, int2 cellIndex)
	{
		float2 @float = (float2)(block.m_Size - (cellIndex << 1) - 1) * 4f;
		float3 position = block.m_Position;
		position.xz += block.m_Direction * @float.y;
		position.xz += MathUtils.Right(block.m_Direction) * @float.x;
		return position;
	}
```

- `public static GetCellWidth(System.Single roadWidth) : System.Int32`  

```csharp
public static int GetCellWidth(float roadWidth)
	{
		return (int)math.ceil(roadWidth / 8f - 0.01f);
	}
```

- `public static GetColorIndex(Game.Zones.CellFlags state, Game.Zones.ZoneType type) : System.Int32`  

```csharp
public static int GetColorIndex(CellFlags state, ZoneType type)
	{
		int num = math.select(0, 3 + type.m_Index * 3, (state & (CellFlags.Shared | CellFlags.Visible)) == CellFlags.Visible);
		int falseValue = math.select(0, 1, (state & CellFlags.Occupied) != 0);
		falseValue = math.select(falseValue, 2, (state & CellFlags.Selected) != 0);
		return num + falseValue;
	}
```

- `public static GetPosition(Game.Zones.Block block, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max) : Unity.Mathematics.float3`  

```csharp
public static float3 GetPosition(Block block, int2 min, int2 max)
	{
		float2 @float = (float2)(block.m_Size - min - max) * 4f;
		float3 position = block.m_Position;
		position.xz += block.m_Direction * @float.y;
		position.xz += MathUtils.Right(block.m_Direction) * @float.x;
		return position;
	}
```

- `public static GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source) : Game.Zones.CellFlags`  

```csharp
public static CellFlags GetRoadDirection(Block target, Block source, CellFlags directionFlags)
	{
		float2 x = new float2(math.dot(target.m_Direction, source.m_Direction), math.dot(MathUtils.Right(target.m_Direction), source.m_Direction));
		int4 @int = new int4(4, 512, 2048, 1024);
		int4 falseValue = math.select(@int.xyzw, @int.zwxy, x.x < 0f);
		int4 trueValue = math.select(@int.yzwx, @int.wxyz, x.y < 0f);
		x = math.abs(x);
		return (CellFlags)math.csum(math.select(0, math.select(falseValue, trueValue, x.y > x.x), ((int)directionFlags & @int) != 0));
	}
```

- `public static GetRoadDirection(Game.Zones.Block target, Game.Zones.Block source, Game.Zones.CellFlags directionFlags) : Game.Zones.CellFlags`  

```csharp
public static CellFlags GetRoadDirection(Block target, Block source, CellFlags directionFlags)
	{
		float2 x = new float2(math.dot(target.m_Direction, source.m_Direction), math.dot(MathUtils.Right(target.m_Direction), source.m_Direction));
		int4 @int = new int4(4, 512, 2048, 1024);
		int4 falseValue = math.select(@int.xyzw, @int.zwxy, x.x < 0f);
		int4 trueValue = math.select(@int.yzwx, @int.wxyz, x.y < 0f);
		x = math.abs(x);
		return (CellFlags)math.csum(math.select(0, math.select(falseValue, trueValue, x.y > x.x), ((int)directionFlags & @int) != 0));
	}
```

- `public static GetRotation(Game.Zones.Block block) : Unity.Mathematics.quaternion`  

```csharp
public static quaternion GetRotation(Block block)
	{
		return quaternion.LookRotation(new float3(block.m_Direction.x, 0f, block.m_Direction.y), math.up());
	}
```

- `public static IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2, Game.Zones.BuildOrder buildOrder1, Game.Zones.BuildOrder buildOrder2) : System.Boolean`  

```csharp
public static bool IsNeighbor(Block block1, Block block2)
	{
		if (math.dot(block1.m_Direction, block2.m_Direction) < 0.9998477f)
		{
			return false;
		}
		float2 x = block2.m_Position.xz - block1.m_Position.xz;
		x -= block1.m_Direction * ((float)block1.m_Size.y * 4f);
		x += block2.m_Direction * ((float)block2.m_Size.y * 4f);
		float2 @float = default(float2);
		@float.y = math.dot(x, block1.m_Direction);
		@float.x = math.dot(x, MathUtils.Right(block1.m_Direction));
		@float = math.abs(@float / 8f);
		return math.all(new float2(math.abs(@float.x - (float)(block1.m_Size.x + block2.m_Size.x) * 0.5f), @float.y) <= 0.02f);
	}
```

- `public static IsNeighbor(Game.Zones.Block block1, Game.Zones.Block block2) : System.Boolean`  

```csharp
public static bool IsNeighbor(Block block1, Block block2)
	{
		if (math.dot(block1.m_Direction, block2.m_Direction) < 0.9998477f)
		{
			return false;
		}
		float2 x = block2.m_Position.xz - block1.m_Position.xz;
		x -= block1.m_Direction * ((float)block1.m_Size.y * 4f);
		x += block2.m_Direction * ((float)block2.m_Size.y * 4f);
		float2 @float = default(float2);
		@float.y = math.dot(x, block1.m_Direction);
		@float.x = math.dot(x, MathUtils.Right(block1.m_Direction));
		@float = math.abs(@float / 8f);
		return math.all(new float2(math.abs(@float.x - (float)(block1.m_Size.x + block2.m_Size.x) * 0.5f), @float.y) <= 0.02f);
	}
```



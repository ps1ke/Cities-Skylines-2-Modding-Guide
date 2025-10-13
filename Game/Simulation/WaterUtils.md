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
public static float GetSampleInterval(ref WaterSurfaceData data)
	{
		return math.cmin(1f / data.scale.xz);
	}
```

- `public static GetSurfaceDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition) : System.Single`  

```csharp
public static float GetSurfaceDepth(ref WaterSurfaceData data, int2 surfacePosition)
	{
		return math.max(data.depths[surfacePosition.y * data.resolution.x + surfacePosition.x].m_Depth, 0f);
	}
```

- `public static GetWorldPosition(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.int2 surfacePosition) : Unity.Mathematics.float3`  

```csharp
public static float3 GetWorldPosition(ref WaterSurfaceData data, int2 surfacePosition)
	{
		return ToWorldSpace(ref data, new float3
		{
			y = GetSurfaceDepth(ref data, surfacePosition),
			xz = surfacePosition
		});
	}
```

- `public static Raycast(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t) : System.Boolean`  

```csharp
public static bool Raycast(ref WaterSurfaceData waterData, ref TerrainHeightData terrainData, Line3.Segment worldLine, bool outside, out float t)
	{
		Line3.Segment line = TerrainUtils.ToHeightmapSpace(ref terrainData, worldLine);
		Bounds3 bounds = new Bounds3(new float3(0f, -50f, 0f), terrainData.resolution - 1 + new float3(0f, 100f, 0f));
		float2 t2;
		if (outside)
		{
			if (!MathUtils.Intersect(bounds.y, line.y, out t2))
			{
				t = 2f;
				return false;
			}
		}
		else if (!MathUtils.Intersect(bounds, line, out t2))
		{
			t = 2f;
			return false;
		}
		Line3.Segment line2 = ToSurfaceSpace(ref waterData, worldLine);
		line2 = MathUtils.Cut(line2, t2);
		float2 terrainToWaterSpace = new float2(waterData.scale.y / terrainData.scale.y, (0f - terrainData.offset.y) * waterData.scale.y);
		int2 waterToTerrainFactor = terrainData.resolution.xz / waterData.resolution.xz;
		float3 x = line2.b - line2.a;
		float3 @float = math.abs(x);
		float4 float2 = math.floor(new float4(line2.a.xz, line2.b.xz));
		int4 @int = new int4((int)float2.x, (int)float2.z, (int)float2.y, (int)float2.w);
		if (math.all(@int.xz == @int.yw))
		{
			if (RaycastCell(ref waterData, ref terrainData, line2, @int.xz, terrainToWaterSpace, waterToTerrainFactor, outside, out t))
			{
				t = math.saturate(math.lerp(t2.x, t2.y, t));
				return true;
			}
		}
		else if (@float.x > @float.z)
		{
			int2 int2 = math.select(1, -1, x.xz < 0f);
			@int.y += int2.x;
			float num = (float)math.select(1, 0, x.x < 0f) - line2.a.x;
			float num2 = 1f / x.x;
			int2 pos = default(int2);
			pos.x = @int.x;
			while (pos.x != @int.y)
			{
				float t3 = ((float)pos.x + num) * num2;
				@int.w = (int)math.floor(math.lerp(line2.a.z, line2.b.z, t3)) + int2.y;
				pos.y = @int.z;
				while (pos.y != @int.w)
				{
					if (RaycastCell(ref waterData, ref terrainData, line2, pos, terrainToWaterSpace, waterToTerrainFactor, outside, out t))
					{
						t = math.saturate(math.lerp(t2.x, t2.y, t));
						return true;
					}
					pos.y += int2.y;
				}
				@int.z = @int.w - int2.y;
				pos.x += int2.x;
			}
		}
		else
		{
			int2 int3 = math.select(1, -1, x.xz < 0f);
			@int.w += int3.y;
			float num3 = (float)math.select(1, 0, x.z < 0f) - line2.a.z;
			float num4 = 1f / x.z;
			int2 pos2 = default(int2);
			pos2.y = @int.z;
			while (pos2.y != @int.w)
			{
				float t4 = ((float)pos2.y + num3) * num4;
				@int.y = (int)math.floor(math.lerp(line2.a.x, line2.b.x, t4)) + int3.x;
				pos2.x = @int.x;
				while (pos2.x != @int.y)
				{
					if (RaycastCell(ref waterData, ref terrainData, line2, pos2, terrainToWaterSpace, waterToTerrainFactor, outside, out t))
					{
						t = math.saturate(math.lerp(t2.x, t2.y, t));
						return true;
					}
					pos2.x += int3.x;
				}
				@int.x = @int.y - int3.x;
				pos2.y += int3.y;
			}
		}
		t = 2f;
		return false;
	}
```

- `private static RaycastCell(Game.Simulation.WaterSurfaceData& waterData, Game.Simulation.TerrainHeightData& terrainData, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, Unity.Mathematics.float2 terrainToWaterSpace, Unity.Mathematics.int2 waterToTerrainFactor, System.Boolean outside, System.Single& t) : System.Boolean`  

```csharp
private static bool RaycastCell(ref WaterSurfaceData waterData, ref TerrainHeightData terrainData, Line3.Segment localLine, int2 pos, float2 terrainToWaterSpace, int2 waterToTerrainFactor, bool outside, out float t)
	{
		t = 2f;
		int4 @int = math.clamp(new int4(pos, pos + 1), 0, waterData.resolution.xzxz - 1);
		int4 int2 = @int.yyww * waterData.resolution.x + @int.xzxz;
		int4 int3 = math.clamp(@int * waterToTerrainFactor.xyxy, 0, terrainData.resolution.xzxz - 1);
		int4 int4 = int3.yyww * terrainData.resolution.x + int3.xzxz;
		float4 @float = default(float4);
		@float.x = math.max(waterData.depths[int2.x].m_Depth, 0f);
		@float.y = math.max(waterData.depths[int2.y].m_Depth, 0f);
		@float.z = math.max(waterData.depths[int2.z].m_Depth, 0f);
		@float.w = math.max(waterData.depths[int2.w].m_Depth, 0f);
		float4 float2 = default(float4);
		float2.x = (int)terrainData.heights[int4.x];
		float2.y = (int)terrainData.heights[int4.y];
		float2.z = (int)terrainData.heights[int4.z];
		float2.w = (int)terrainData.heights[int4.w];
		float4 x = float2 * terrainToWaterSpace.x + terrainToWaterSpace.y + @float;
		Bounds3 bounds = default(Bounds3);
		@int = math.select(@int, new int4(pos, pos + 1), outside);
		bounds.min = new float3(@int.x, math.cmin(x), @int.y);
		bounds.max = new float3(@int.z, math.cmax(x), @int.w);
		if (MathUtils.Intersect(bounds, localLine, out var _))
		{
			float3 float3 = new float3(bounds.min.x, x.x, bounds.min.z);
			float3 float4 = new float3(bounds.max.x, x.y, bounds.min.z);
			float3 float5 = new float3(bounds.max.x, x.w, bounds.max.z);
			float3 float6 = new float3(bounds.min.x, x.z, bounds.max.z);
			float3 c = MathUtils.Center(bounds);
			if (MathUtils.Intersect(new Triangle3(float3, float4, c), localLine, out var t3))
			{
				t = math.min(t, t3.z);
			}
			if (MathUtils.Intersect(new Triangle3(float4, float5, c), localLine, out t3))
			{
				t = math.min(t, t3.z);
			}
			if (MathUtils.Intersect(new Triangle3(float5, float6, c), localLine, out t3))
			{
				t = math.min(t, t3.z);
			}
			if (MathUtils.Intersect(new Triangle3(float6, float3, c), localLine, out t3))
			{
				t = math.min(t, t3.z);
			}
			if (t != 2f)
			{
				return true;
			}
		}
		return false;
	}
```

- `public static SampleDepth(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static float SampleDepth(ref WaterSurfaceData data, float3 worldPosition)
	{
		float2 xz = ToSurfaceSpace(ref data, worldPosition).xz;
		int4 valueToClamp = default(int4);
		valueToClamp.xy = (int2)math.floor(xz);
		valueToClamp.zw = valueToClamp.xy + 1;
		valueToClamp = math.clamp(valueToClamp, 0, data.resolution.xzxz - 1);
		int4 @int = valueToClamp.yyww * data.resolution.x + valueToClamp.xzxz;
		float4 @float = default(float4);
		@float.x = data.depths[@int.x].m_Depth;
		@float.y = data.depths[@int.y].m_Depth;
		@float.z = data.depths[@int.z].m_Depth;
		@float.w = data.depths[@int.w].m_Depth;
		float2 float2 = math.saturate(xz - valueToClamp.xy);
		float2 float3 = math.lerp(@float.xz, @float.yw, float2.x);
		return math.max(ToWorldSpace(ref data, math.lerp(float3.x, float3.y, float2.y)), 0f);
	}
```

- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static void SampleHeight(ref WaterSurfaceData data, ref TerrainHeightData terrainData, float3 worldPosition, out float terrainHeight, out float waterHeight, out float waterDepth)
	{
		terrainHeight = TerrainUtils.SampleHeight(ref terrainData, worldPosition);
		waterDepth = SampleDepth(ref data, worldPosition);
		waterHeight = terrainHeight + waterDepth;
	}
```

- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& waterDepth) : System.Single`  

```csharp
public static void SampleHeight(ref WaterSurfaceData data, ref TerrainHeightData terrainData, float3 worldPosition, out float terrainHeight, out float waterHeight, out float waterDepth)
	{
		terrainHeight = TerrainUtils.SampleHeight(ref terrainData, worldPosition);
		waterDepth = SampleDepth(ref data, worldPosition);
		waterHeight = terrainHeight + waterDepth;
	}
```

- `public static SampleHeight(Game.Simulation.WaterSurfaceData& data, Game.Simulation.TerrainHeightData& terrainData, Unity.Mathematics.float3 worldPosition, System.Single& terrainHeight, System.Single& waterHeight, System.Single& waterDepth) : System.Void`  

```csharp
public static void SampleHeight(ref WaterSurfaceData data, ref TerrainHeightData terrainData, float3 worldPosition, out float terrainHeight, out float waterHeight, out float waterDepth)
	{
		terrainHeight = TerrainUtils.SampleHeight(ref terrainData, worldPosition);
		waterDepth = SampleDepth(ref data, worldPosition);
		waterHeight = terrainHeight + waterDepth;
	}
```

- `public static SamplePolluted(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static float SamplePolluted(ref WaterSurfaceData data, float3 worldPosition)
	{
		float2 xz = ToSurfaceSpace(ref data, worldPosition).xz;
		int4 valueToClamp = default(int4);
		valueToClamp.xy = (int2)math.floor(xz);
		valueToClamp.zw = valueToClamp.xy + 1;
		valueToClamp = math.clamp(valueToClamp, 0, data.resolution.xzxz - 1);
		int4 @int = valueToClamp.yyww * data.resolution.x + valueToClamp.xzxz;
		float4 @float = default(float4);
		@float.x = data.depths[@int.x].m_Polluted;
		@float.y = data.depths[@int.y].m_Polluted;
		@float.z = data.depths[@int.z].m_Polluted;
		@float.w = data.depths[@int.w].m_Polluted;
		float2 float2 = math.saturate(xz - valueToClamp.xy);
		float2 float3 = math.lerp(@float.xz, @float.yw, float2.x);
		return ToWorldSpace(ref data, math.lerp(float3.x, float3.y, float2.y));
	}
```

- `public static SampleVelocity(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float2`  

```csharp
public static float2 SampleVelocity(ref WaterSurfaceData data, float3 worldPosition)
	{
		float2 xz = ToSurfaceSpace(ref data, worldPosition).xz;
		int4 valueToClamp = default(int4);
		valueToClamp.xy = (int2)math.floor(xz);
		valueToClamp.zw = valueToClamp.xy + 1;
		valueToClamp = math.clamp(valueToClamp, 0, data.resolution.xzxz - 1);
		int4 @int = valueToClamp.yyww * data.resolution.x + valueToClamp.xzxz;
		float4 start = default(float4);
		float4 end = default(float4);
		start.xy = data.depths[@int.x].m_Velocity;
		end.xy = data.depths[@int.y].m_Velocity;
		start.zw = data.depths[@int.z].m_Velocity;
		end.zw = data.depths[@int.w].m_Velocity;
		float2 @float = math.saturate(xz - valueToClamp.xy);
		float4 float2 = math.lerp(start, end, @float.x);
		return ToWorldSpace(ref data, math.lerp(float2.xy, float2.zw, @float.y));
	}
```

- `public static ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float3`  

```csharp
public static Line3.Segment ToSurfaceSpace(ref WaterSurfaceData data, Line3.Segment worldLine)
	{
		return new Line3.Segment(ToSurfaceSpace(ref data, worldLine.a), ToSurfaceSpace(ref data, worldLine.b));
	}
```

- `public static ToSurfaceSpace(Game.Simulation.WaterSurfaceData& data, Colossal.Mathematics.Line3+Segment worldLine) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Line3.Segment ToSurfaceSpace(ref WaterSurfaceData data, Line3.Segment worldLine)
	{
		return new Line3.Segment(ToSurfaceSpace(ref data, worldLine.a), ToSurfaceSpace(ref data, worldLine.b));
	}
```

- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float3 surfacePosition) : Unity.Mathematics.float3`  

```csharp
public static float ToWorldSpace(ref WaterSurfaceData data, float surfaceDepth)
	{
		return surfaceDepth / data.scale.y - data.offset.y;
	}
```

- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, Unity.Mathematics.float2 surfaceVelocity) : Unity.Mathematics.float2`  

```csharp
public static float ToWorldSpace(ref WaterSurfaceData data, float surfaceDepth)
	{
		return surfaceDepth / data.scale.y - data.offset.y;
	}
```

- `public static ToWorldSpace(Game.Simulation.WaterSurfaceData& data, System.Single surfaceDepth) : System.Single`  

```csharp
public static float ToWorldSpace(ref WaterSurfaceData data, float surfaceDepth)
	{
		return surfaceDepth / data.scale.y - data.offset.y;
	}
```



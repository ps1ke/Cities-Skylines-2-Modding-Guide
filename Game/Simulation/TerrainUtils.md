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
public static Bounds3 GetBounds(ref TerrainHeightData data)
	{
		return new Bounds3(-data.offset, (data.resolution - 1) / data.scale - data.offset);
	}
```

- `public static GetEditorCameraBounds(Game.Simulation.TerrainSystem terrainSystem, Game.Simulation.TerrainHeightData& data) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 GetEditorCameraBounds(TerrainSystem terrainSystem, ref TerrainHeightData data)
	{
		if (terrainSystem?.worldHeightmap != null)
		{
			return new Bounds3(new float3(terrainSystem.worldOffset.x, terrainSystem.heightScaleOffset.y, terrainSystem.worldOffset.y), new float3(terrainSystem.worldOffset.x + terrainSystem.worldSize.x, terrainSystem.heightScaleOffset.y + terrainSystem.heightScaleOffset.x, terrainSystem.worldOffset.y + terrainSystem.worldSize.y));
		}
		return GetBounds(ref data);
	}
```

- `public static GetHeightRange(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Bounds3 worldBounds) : Colossal.Mathematics.Bounds1`  

```csharp
public static Bounds1 GetHeightRange(ref TerrainHeightData data, Bounds3 worldBounds)
	{
		float2 xz = ToHeightmapSpace(ref data, worldBounds.min).xz;
		float2 xz2 = ToHeightmapSpace(ref data, worldBounds.max).xz;
		int4 @int = math.clamp(new int4
		{
			xy = (int2)math.floor(xz),
			zw = (int2)math.ceil(xz2)
		}, 0, data.resolution.xzxz - 1);
		Bounds1 result = new Bounds1(float.MaxValue, float.MinValue);
		for (int i = @int.y; i <= @int.w; i++)
		{
			int2 int2 = i * data.resolution.x + @int.xz;
			for (int j = int2.x; j <= int2.y; j++)
			{
				result |= (float)(int)data.heights[j];
			}
		}
		result.min = ToWorldSpace(ref data, result.min);
		result.max = ToWorldSpace(ref data, result.max);
		return result;
	}
```

- `public static Raycast(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal) : System.Boolean`  

```csharp
public static bool Raycast(ref TerrainHeightData data, Line3.Segment worldLine, bool outside, out float t, out float3 normal)
	{
		Line3.Segment line = ToHeightmapSpace(ref data, worldLine);
		Bounds3 bounds = new Bounds3(new float3(0f, -50f, 0f), data.resolution - 1 + new float3(0f, 100f, 0f));
		float2 t2;
		if (outside)
		{
			if (!MathUtils.Intersect(bounds.y, line.y, out t2))
			{
				t = 2f;
				normal = default(float3);
				return false;
			}
		}
		else if (!MathUtils.Intersect(bounds, line, out t2))
		{
			t = 2f;
			normal = default(float3);
			return false;
		}
		line = MathUtils.Cut(line, t2);
		float3 x = line.b - line.a;
		float3 @float = math.abs(x);
		float4 float2 = math.floor(new float4(line.a.xz, line.b.xz));
		int4 @int = new int4((int)float2.x, (int)float2.z, (int)float2.y, (int)float2.w);
		if (math.all(@int.xz == @int.yw))
		{
			if (RaycastCell(ref data, line, @int.xz, outside, out t, out normal))
			{
				t = math.saturate(math.lerp(t2.x, t2.y, t));
				normal = math.normalizesafe(normal);
				return true;
			}
		}
		else if (@float.x > @float.z)
		{
			int2 int2 = math.select(1, -1, x.xz < 0f);
			@int.y += int2.x;
			float num = (float)math.select(1, 0, x.x < 0f) - line.a.x;
			float num2 = 1f / x.x;
			int2 pos = default(int2);
			pos.x = @int.x;
			while (pos.x != @int.y)
			{
				float t3 = ((float)pos.x + num) * num2;
				@int.w = (int)math.floor(math.lerp(line.a.z, line.b.z, t3)) + int2.y;
				pos.y = @int.z;
				while (pos.y != @int.w)
				{
					if (RaycastCell(ref data, line, pos, outside, out t, out normal))
					{
						t = math.saturate(math.lerp(t2.x, t2.y, t));
						normal = math.normalizesafe(normal);
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
			float num3 = (float)math.select(1, 0, x.z < 0f) - line.a.z;
			float num4 = 1f / x.z;
			int2 pos2 = default(int2);
			pos2.y = @int.z;
			while (pos2.y != @int.w)
			{
				float t4 = ((float)pos2.y + num3) * num4;
				@int.y = (int)math.floor(math.lerp(line.a.x, line.b.x, t4)) + int3.x;
				pos2.x = @int.x;
				while (pos2.x != @int.y)
				{
					if (RaycastCell(ref data, line, pos2, outside, out t, out normal))
					{
						t = math.saturate(math.lerp(t2.x, t2.y, t));
						normal = math.normalizesafe(normal);
						return true;
					}
					pos2.x += int3.x;
				}
				@int.x = @int.y - int3.x;
				pos2.y += int3.y;
			}
		}
		t = 2f;
		normal = default(float3);
		return false;
	}
```

- `private static RaycastCell(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment localLine, Unity.Mathematics.int2 pos, System.Boolean outside, System.Single& t, Unity.Mathematics.float3& normal) : System.Boolean`  

```csharp
private static bool RaycastCell(ref TerrainHeightData data, Line3.Segment localLine, int2 pos, bool outside, out float t, out float3 normal)
	{
		t = 2f;
		normal = default(float3);
		int4 falseValue = math.clamp(new int4(pos, pos + 1), 0, data.resolution.xzxz - 1);
		int4 @int = falseValue.yyww * data.resolution.x + falseValue.xzxz;
		float4 x = default(float4);
		x.x = (int)data.heights[@int.x];
		x.y = (int)data.heights[@int.y];
		x.z = (int)data.heights[@int.z];
		x.w = (int)data.heights[@int.w];
		Bounds3 bounds = default(Bounds3);
		falseValue = math.select(falseValue, new int4(pos, pos + 1), outside);
		bounds.min = new float3(falseValue.x, math.cmin(x), falseValue.y);
		bounds.max = new float3(falseValue.z, math.cmax(x), falseValue.w);
		if (MathUtils.Intersect(bounds, localLine, out var _))
		{
			float3 @float = new float3(bounds.min.x, x.x, bounds.min.z);
			float3 float2 = new float3(bounds.max.x, x.y, bounds.min.z);
			float3 float3 = new float3(bounds.max.x, x.w, bounds.max.z);
			float3 float4 = new float3(bounds.min.x, x.z, bounds.max.z);
			float3 float5 = MathUtils.Center(bounds);
			if (MathUtils.Intersect(new Triangle3(@float, float2, float5), localLine, out var t3))
			{
				t = math.min(t, t3.z);
				normal = math.cross(float5 - @float, float2 - @float);
			}
			if (MathUtils.Intersect(new Triangle3(float2, float3, float5), localLine, out t3))
			{
				t = math.min(t, t3.z);
				normal = math.cross(float5 - float2, float3 - float2);
			}
			if (MathUtils.Intersect(new Triangle3(float3, float4, float5), localLine, out t3))
			{
				t = math.min(t, t3.z);
				normal = math.cross(float5 - float3, float4 - float3);
			}
			if (MathUtils.Intersect(new Triangle3(float4, @float, float5), localLine, out t3))
			{
				t = math.min(t, t3.z);
				normal = math.cross(float5 - float4, @float - float4);
			}
			return t != 2f;
		}
		return false;
	}
```

- `public static SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition) : System.Single`  

```csharp
public static float SampleHeight(ref TerrainHeightData data, float3 worldPosition, out float3 normal)
	{
		float2 xz = ToHeightmapSpace(ref data, worldPosition).xz;
		int4 valueToClamp = default(int4);
		valueToClamp.xy = (int2)math.floor(xz);
		valueToClamp.zw = valueToClamp.xy + 1;
		valueToClamp = math.clamp(valueToClamp, 0, data.resolution.xzxz - 1);
		int4 @int = valueToClamp.yyww * data.resolution.x + valueToClamp.xzxz;
		float4 @float = default(float4);
		@float.x = (int)data.heights[@int.x];
		@float.y = (int)data.heights[@int.y];
		@float.z = (int)data.heights[@int.z];
		@float.w = (int)data.heights[@int.w];
		float2 float2 = math.saturate(xz - valueToClamp.xy);
		float2 float3 = math.lerp(@float.xz, @float.yw, float2.x);
		float2 float4 = @float.xz - @float.yw;
		normal = math.normalizesafe(new float3(math.lerp(float4.x, float4.y, float2.y), 1f, float3.x - float3.y));
		return ToWorldSpace(ref data, math.lerp(float3.x, float3.y, float2.y));
	}
```

- `public static SampleHeight(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition, Unity.Mathematics.float3& normal) : System.Single`  

```csharp
public static float SampleHeight(ref TerrainHeightData data, float3 worldPosition, out float3 normal)
	{
		float2 xz = ToHeightmapSpace(ref data, worldPosition).xz;
		int4 valueToClamp = default(int4);
		valueToClamp.xy = (int2)math.floor(xz);
		valueToClamp.zw = valueToClamp.xy + 1;
		valueToClamp = math.clamp(valueToClamp, 0, data.resolution.xzxz - 1);
		int4 @int = valueToClamp.yyww * data.resolution.x + valueToClamp.xzxz;
		float4 @float = default(float4);
		@float.x = (int)data.heights[@int.x];
		@float.y = (int)data.heights[@int.y];
		@float.z = (int)data.heights[@int.z];
		@float.w = (int)data.heights[@int.w];
		float2 float2 = math.saturate(xz - valueToClamp.xy);
		float2 float3 = math.lerp(@float.xz, @float.yw, float2.x);
		float2 float4 = @float.xz - @float.yw;
		normal = math.normalizesafe(new float3(math.lerp(float4.x, float4.y, float2.y), 1f, float3.x - float3.y));
		return ToWorldSpace(ref data, math.lerp(float3.x, float3.y, float2.y));
	}
```

- `public static ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Unity.Mathematics.float3 worldPosition) : Unity.Mathematics.float3`  

```csharp
public static Line3.Segment ToHeightmapSpace(ref TerrainHeightData data, Line3.Segment worldLine)
	{
		return new Line3.Segment(ToHeightmapSpace(ref data, worldLine.a), ToHeightmapSpace(ref data, worldLine.b));
	}
```

- `public static ToHeightmapSpace(Game.Simulation.TerrainHeightData& data, Colossal.Mathematics.Line3+Segment worldLine) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Line3.Segment ToHeightmapSpace(ref TerrainHeightData data, Line3.Segment worldLine)
	{
		return new Line3.Segment(ToHeightmapSpace(ref data, worldLine.a), ToHeightmapSpace(ref data, worldLine.b));
	}
```

- `public static ToWorldSpace(Game.Simulation.TerrainHeightData& data, System.Single heightmapHeight) : System.Single`  

```csharp
public static float ToWorldSpace(ref TerrainHeightData data, float heightmapHeight)
	{
		return heightmapHeight / data.scale.y - data.offset.y;
	}
```



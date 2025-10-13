# Game.Rendering.FrustumPlanes

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct FrustumPlanes
{
    public static System.Void BuildSOAPlanePackets(Unity.Collections.NativeArray<UnityEngine.Plane> cullingPlanes, System.Int32 cullingPlaneCount, Unity.Collections.NativeList<Game.Rendering.FrustumPlanes+PlanePacket4> result);
    public static Game.Rendering.FrustumPlanes+IntersectResult CalculateIntersectResult(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents);
    private static Unity.Mathematics.float4 dot4(Unity.Mathematics.float4 xs, Unity.Mathematics.float4 ys, Unity.Mathematics.float4 zs, Unity.Mathematics.float4 mx, Unity.Mathematics.float4 my, Unity.Mathematics.float4 mz);
    public static System.Int32 GetPacketCount(System.Int32 cullingPlaneCount);
    public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& inMask, System.UInt64& outMask);
    public static System.Boolean Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents);
    public static System.Boolean Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius);
    public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& outMask);
    public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt64& outMask);
    public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt32& outMask);
    public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt32& outMask);
}
```


## Methods

- `public static BuildSOAPlanePackets(Unity.Collections.NativeArray<UnityEngine.Plane> cullingPlanes, System.Int32 cullingPlaneCount, Unity.Collections.NativeList<Game.Rendering.FrustumPlanes+PlanePacket4> result) : System.Void`  

```csharp
public static void BuildSOAPlanePackets(NativeArray<Plane> cullingPlanes, int cullingPlaneCount, NativeList<PlanePacket4> result)
	{
		int packetCount = GetPacketCount(cullingPlaneCount);
		result.ResizeUninitialized(packetCount);
		for (int i = 0; i < cullingPlaneCount; i++)
		{
			Plane plane = cullingPlanes[i];
			PlanePacket4 value = result[i >> 2];
			value.Xs[i & 3] = plane.normal.x;
			value.Ys[i & 3] = plane.normal.y;
			value.Zs[i & 3] = plane.normal.z;
			value.Distances[i & 3] = plane.distance;
			result[i >> 2] = value;
		}
		for (int j = cullingPlaneCount; j < 4 * packetCount; j++)
		{
			PlanePacket4 value2 = result[j >> 2];
			value2.Xs[j & 3] = 1f;
			value2.Ys[j & 3] = 0f;
			value2.Zs[j & 3] = 0f;
			value2.Distances[j & 3] = 1E+09f;
			result[j >> 2] = value2;
		}
	}
```

- `public static CalculateIntersectResult(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents) : Game.Rendering.FrustumPlanes+IntersectResult`  

```csharp
public unsafe static IntersectResult CalculateIntersectResult(PlanePacket4* cullingPlanePackets, int length, float3 center, float3 extents)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 xxxx2 = extents.xxxx;
		float4 yyyy2 = extents.yyyy;
		float4 zzzz2 = extents.zzzz;
		int4 x = 0;
		int4 x2 = 0;
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 @float = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float2 = dot4(xxxx2, yyyy2, zzzz2, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += (int4)(@float + float2 < 0f);
			x2 += (int4)(@float >= float2);
		}
		int num = math.csum(x2);
		if (math.csum(x) != 0)
		{
			return IntersectResult.Out;
		}
		if (num != 4 * length)
		{
			return IntersectResult.Partial;
		}
		return IntersectResult.In;
	}
```

- `private static dot4(Unity.Mathematics.float4 xs, Unity.Mathematics.float4 ys, Unity.Mathematics.float4 zs, Unity.Mathematics.float4 mx, Unity.Mathematics.float4 my, Unity.Mathematics.float4 mz) : Unity.Mathematics.float4`  

```csharp
private static float4 dot4(float4 xs, float4 ys, float4 zs, float4 mx, float4 my, float4 mz)
	{
		return xs * mx + ys * my + zs * mz;
	}
```

- `public static GetPacketCount(System.Int32 cullingPlaneCount) : System.Int32`  

```csharp
public static int GetPacketCount(int cullingPlaneCount)
	{
		return cullingPlaneCount + 3 >> 2;
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& inMask, System.UInt64& outMask) : System.Void`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents) : System.Boolean`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius) : System.Boolean`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& outMask) : System.Void`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt64& outMask) : System.Void`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt32& outMask) : System.Void`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt32& outMask) : System.Void`  

```csharp
public unsafe static void Intersect(PlanePacket4* cullingPlanePackets, int length, float3 center, float radius, out uint outMask)
	{
		float4 xxxx = center.xxxx;
		float4 yyyy = center.yyyy;
		float4 zzzz = center.zzzz;
		float4 @float = new float4(radius);
		uint4 x = 0u;
		uint4 trueValue = new uint4(1u, 2u, 4u, 8u);
		for (int i = 0; i < length; i++)
		{
			PlanePacket4 planePacket = cullingPlanePackets[i];
			float4 float2 = dot4(planePacket.Xs, planePacket.Ys, planePacket.Zs, xxxx, yyyy, zzzz) + planePacket.Distances;
			float4 float3 = dot4(@float, @float, @float, math.abs(planePacket.Xs), math.abs(planePacket.Ys), math.abs(planePacket.Zs));
			x += math.select(0u, trueValue, float2 + float3 < 0f);
			trueValue <<= 4;
		}
		outMask = math.csum(x);
	}
```


## Nested types

- `Game.Rendering.FrustumPlanes+IntersectResult`  
- `Game.Rendering.FrustumPlanes+PlanePacket4`  


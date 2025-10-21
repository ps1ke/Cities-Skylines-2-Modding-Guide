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
public static System.Void BuildSOAPlanePackets(Unity.Collections.NativeArray<UnityEngine.Plane> cullingPlanes, System.Int32 cullingPlaneCount, Unity.Collections.NativeList<Game.Rendering.FrustumPlanes+PlanePacket4> result);
```

- `public static CalculateIntersectResult(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents) : Game.Rendering.FrustumPlanes+IntersectResult`  

```csharp
public static Game.Rendering.FrustumPlanes+IntersectResult CalculateIntersectResult(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents);
```

- `private static dot4(Unity.Mathematics.float4 xs, Unity.Mathematics.float4 ys, Unity.Mathematics.float4 zs, Unity.Mathematics.float4 mx, Unity.Mathematics.float4 my, Unity.Mathematics.float4 mz) : Unity.Mathematics.float4`  

```csharp
private static Unity.Mathematics.float4 dot4(Unity.Mathematics.float4 xs, Unity.Mathematics.float4 ys, Unity.Mathematics.float4 zs, Unity.Mathematics.float4 mx, Unity.Mathematics.float4 my, Unity.Mathematics.float4 mz);
```

- `public static GetPacketCount(System.Int32 cullingPlaneCount) : System.Int32`  

```csharp
public static System.Int32 GetPacketCount(System.Int32 cullingPlaneCount);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& inMask, System.UInt64& outMask) : System.Void`  

```csharp
public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& inMask, System.UInt64& outMask);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& outMask) : System.Void`  

```csharp
public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& outMask);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt64& outMask) : System.Void`  

```csharp
public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt64& outMask);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt32& outMask) : System.Void`  

```csharp
public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt32& outMask);
```

- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt32& outMask) : System.Void`  

```csharp
public static System.Void Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt32& outMask);
```


## Nested types

- `Game.Rendering.FrustumPlanes+IntersectResult`  
- `Game.Rendering.FrustumPlanes+PlanePacket4`  


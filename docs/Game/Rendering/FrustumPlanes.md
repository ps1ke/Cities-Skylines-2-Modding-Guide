# Game.Rendering.FrustumPlanes

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Methods

- `public static BuildSOAPlanePackets(Unity.Collections.NativeArray<UnityEngine.Plane> cullingPlanes, System.Int32 cullingPlaneCount, Unity.Collections.NativeList<Game.Rendering.FrustumPlanes+PlanePacket4> result) : System.Void`  
- `public static CalculateIntersectResult(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents) : Game.Rendering.FrustumPlanes+IntersectResult`  
- `private static dot4(Unity.Mathematics.float4 xs, Unity.Mathematics.float4 ys, Unity.Mathematics.float4 zs, Unity.Mathematics.float4 mx, Unity.Mathematics.float4 my, Unity.Mathematics.float4 mz) : Unity.Mathematics.float4`  
- `public static GetPacketCount(System.Int32 cullingPlaneCount) : System.Int32`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& inMask, System.UInt64& outMask) : System.Void`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents) : System.Boolean`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius) : System.Boolean`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt64& outMask) : System.Void`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt64& outMask) : System.Void`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, Unity.Mathematics.float3 extents, System.UInt32& outMask) : System.Void`  
- `public static Intersect(Game.Rendering.FrustumPlanes+PlanePacket4* cullingPlanePackets, System.Int32 length, Unity.Mathematics.float3 center, System.Single radius, System.UInt32& outMask) : System.Void`  

## Nested types

- `Game.Rendering.FrustumPlanes+IntersectResult`  
- `Game.Rendering.FrustumPlanes+PlanePacket4`  


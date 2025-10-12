# Game.Rendering.RenderingUtils

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static CalculateDistance(System.Int32 lod, Unity.Mathematics.float4 lodParameters) : System.Single`  
- `public static CalculateDistanceFactor(System.Int32 lod) : System.Single`  
- `public static CalculateLod(System.Single distanceSq, Unity.Mathematics.float4 lodParameters) : System.Int32`  
- `public static CalculateLodLimit(System.Single metersPerPixel, System.Single bias) : System.Int32`  
- `public static CalculateLodLimit(System.Single metersPerPixel) : System.Int32`  
- `public static CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.BatchCullingContext cullingContext) : Unity.Mathematics.float4`  
- `public static CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.LODParameters lodParameters) : Unity.Mathematics.float4`  
- `public static CalculateMaxDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters) : System.Single`  
- `public static CalculateMinDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters) : System.Single`  
- `public static FindBoneIndex(Unity.Entities.Entity prefab, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Int32 boneID, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBoneBuffers) : Unity.Mathematics.int2`  
- `public static GetBlendWeight(Game.Prefabs.CharacterGroup+IndexWeight indexWeight) : Game.Rendering.BlendWeight`  
- `public static GetBlendWeights(Game.Prefabs.CharacterGroup+IndexWeight8 indexWeight8) : Game.Rendering.BlendWeights`  
- `public static GetRenderingSize(Unity.Mathematics.float3 size) : System.Single`  
- `public static GetRenderingSize(Unity.Mathematics.float3 size, System.Single indexCount) : System.Single`  
- `public static GetRenderingSize(Unity.Mathematics.float2 size) : System.Single`  
- `public static GetRenderingSize(Unity.Mathematics.float2 size, System.Single indexFactor) : System.Single`  
- `public static GetRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection) : System.Single`  
- `public static GetRenderingSize(Unity.Mathematics.float3 boundsSize, Unity.Mathematics.float3 meshSize, System.Single indexCount, Game.Prefabs.StackDirection stackDirection) : System.Single`  
- `public static GetShadowRenderingSize(Unity.Mathematics.float2 size) : System.Single`  
- `public static GetShadowRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection) : System.Single`  
- `public static Lerp(Unity.Mathematics.float4 c0, Unity.Mathematics.float4 c0_5, Unity.Mathematics.float4 c1, System.Single t) : Unity.Mathematics.float4`  
- `public static SafeBounds(Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  
- `public static ToBounds(Colossal.Mathematics.Bounds3 bounds) : UnityEngine.Bounds`  
- `public static ToColor(Unity.Mathematics.float4 vector) : UnityEngine.Color`  
- `public static ToMatrix4x4(Unity.Mathematics.float4x4 matrix) : UnityEngine.Matrix4x4`  


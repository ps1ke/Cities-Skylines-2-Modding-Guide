# Game.Rendering.RenderingUtils

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class RenderingUtils
{
    public static System.Single CalculateDistance(System.Int32 lod, Unity.Mathematics.float4 lodParameters);
    public static System.Single CalculateDistanceFactor(System.Int32 lod);
    public static System.Int32 CalculateLod(System.Single distanceSq, Unity.Mathematics.float4 lodParameters);
    public static System.Int32 CalculateLodLimit(System.Single metersPerPixel, System.Single bias);
    public static System.Int32 CalculateLodLimit(System.Single metersPerPixel);
    public static Unity.Mathematics.float4 CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.BatchCullingContext cullingContext);
    public static Unity.Mathematics.float4 CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.LODParameters lodParameters);
    public static System.Single CalculateMaxDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters);
    public static System.Single CalculateMinDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters);
    public static Unity.Mathematics.int2 FindBoneIndex(Unity.Entities.Entity prefab, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Int32 boneID, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBoneBuffers);
    public static Game.Rendering.BlendWeight GetBlendWeight(Game.Prefabs.CharacterGroup+IndexWeight indexWeight);
    public static Game.Rendering.BlendWeights GetBlendWeights(Game.Prefabs.CharacterGroup+IndexWeight8 indexWeight8);
    public static System.Single GetRenderingSize(Unity.Mathematics.float3 size);
    public static System.Single GetRenderingSize(Unity.Mathematics.float3 size, System.Single indexCount);
    public static System.Single GetRenderingSize(Unity.Mathematics.float2 size);
    public static System.Single GetRenderingSize(Unity.Mathematics.float2 size, System.Single indexFactor);
    public static System.Single GetRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection);
    public static System.Single GetRenderingSize(Unity.Mathematics.float3 boundsSize, Unity.Mathematics.float3 meshSize, System.Single indexCount, Game.Prefabs.StackDirection stackDirection);
    public static System.Single GetShadowRenderingSize(Unity.Mathematics.float2 size);
    public static System.Single GetShadowRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection);
    public static Unity.Mathematics.float4 Lerp(Unity.Mathematics.float4 c0, Unity.Mathematics.float4 c0_5, Unity.Mathematics.float4 c1, System.Single t);
    public static Colossal.Mathematics.Bounds3 SafeBounds(Colossal.Mathematics.Bounds3 bounds);
    public static UnityEngine.Bounds ToBounds(Colossal.Mathematics.Bounds3 bounds);
    public static UnityEngine.Color ToColor(Unity.Mathematics.float4 vector);
    public static UnityEngine.Matrix4x4 ToMatrix4x4(Unity.Mathematics.float4x4 matrix);
}
```


## Methods

- `public static CalculateDistance(System.Int32 lod, Unity.Mathematics.float4 lodParameters) : System.Single`  

```csharp
public static System.Single CalculateDistance(System.Int32 lod, Unity.Mathematics.float4 lodParameters);
```

- `public static CalculateDistanceFactor(System.Int32 lod) : System.Single`  

```csharp
public static System.Single CalculateDistanceFactor(System.Int32 lod);
```

- `public static CalculateLod(System.Single distanceSq, Unity.Mathematics.float4 lodParameters) : System.Int32`  

```csharp
public static System.Int32 CalculateLod(System.Single distanceSq, Unity.Mathematics.float4 lodParameters);
```

- `public static CalculateLodLimit(System.Single metersPerPixel, System.Single bias) : System.Int32`  

```csharp
public static System.Int32 CalculateLodLimit(System.Single metersPerPixel, System.Single bias);
```

- `public static CalculateLodLimit(System.Single metersPerPixel) : System.Int32`  

```csharp
public static System.Int32 CalculateLodLimit(System.Single metersPerPixel);
```

- `public static CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.BatchCullingContext cullingContext) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.BatchCullingContext cullingContext);
```

- `public static CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.LODParameters lodParameters) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.LODParameters lodParameters);
```

- `public static CalculateMaxDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters) : System.Single`  

```csharp
public static System.Single CalculateMaxDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters);
```

- `public static CalculateMinDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters) : System.Single`  

```csharp
public static System.Single CalculateMinDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters);
```

- `public static FindBoneIndex(Unity.Entities.Entity prefab, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Int32 boneID, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBoneBuffers) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 FindBoneIndex(Unity.Entities.Entity prefab, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Int32 boneID, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBoneBuffers);
```

- `public static GetBlendWeight(Game.Prefabs.CharacterGroup+IndexWeight indexWeight) : Game.Rendering.BlendWeight`  

```csharp
public static Game.Rendering.BlendWeight GetBlendWeight(Game.Prefabs.CharacterGroup+IndexWeight indexWeight);
```

- `public static GetBlendWeights(Game.Prefabs.CharacterGroup+IndexWeight8 indexWeight8) : Game.Rendering.BlendWeights`  

```csharp
public static Game.Rendering.BlendWeights GetBlendWeights(Game.Prefabs.CharacterGroup+IndexWeight8 indexWeight8);
```

- `public static GetRenderingSize(Unity.Mathematics.float3 size) : System.Single`  

```csharp
public static System.Single GetRenderingSize(Unity.Mathematics.float3 size);
```

- `public static GetRenderingSize(Unity.Mathematics.float3 size, System.Single indexCount) : System.Single`  

```csharp
public static System.Single GetRenderingSize(Unity.Mathematics.float3 size, System.Single indexCount);
```

- `public static GetRenderingSize(Unity.Mathematics.float2 size) : System.Single`  

```csharp
public static System.Single GetRenderingSize(Unity.Mathematics.float2 size);
```

- `public static GetRenderingSize(Unity.Mathematics.float2 size, System.Single indexFactor) : System.Single`  

```csharp
public static System.Single GetRenderingSize(Unity.Mathematics.float2 size, System.Single indexFactor);
```

- `public static GetRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection) : System.Single`  

```csharp
public static System.Single GetRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection);
```

- `public static GetRenderingSize(Unity.Mathematics.float3 boundsSize, Unity.Mathematics.float3 meshSize, System.Single indexCount, Game.Prefabs.StackDirection stackDirection) : System.Single`  

```csharp
public static System.Single GetRenderingSize(Unity.Mathematics.float3 boundsSize, Unity.Mathematics.float3 meshSize, System.Single indexCount, Game.Prefabs.StackDirection stackDirection);
```

- `public static GetShadowRenderingSize(Unity.Mathematics.float2 size) : System.Single`  

```csharp
public static System.Single GetShadowRenderingSize(Unity.Mathematics.float2 size);
```

- `public static GetShadowRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection) : System.Single`  

```csharp
public static System.Single GetShadowRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection);
```

- `public static Lerp(Unity.Mathematics.float4 c0, Unity.Mathematics.float4 c0_5, Unity.Mathematics.float4 c1, System.Single t) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 Lerp(Unity.Mathematics.float4 c0, Unity.Mathematics.float4 c0_5, Unity.Mathematics.float4 c1, System.Single t);
```

- `public static SafeBounds(Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 SafeBounds(Colossal.Mathematics.Bounds3 bounds);
```

- `public static ToBounds(Colossal.Mathematics.Bounds3 bounds) : UnityEngine.Bounds`  

```csharp
public static UnityEngine.Bounds ToBounds(Colossal.Mathematics.Bounds3 bounds);
```

- `public static ToColor(Unity.Mathematics.float4 vector) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color ToColor(Unity.Mathematics.float4 vector);
```

- `public static ToMatrix4x4(Unity.Mathematics.float4x4 matrix) : UnityEngine.Matrix4x4`  

```csharp
public static UnityEngine.Matrix4x4 ToMatrix4x4(Unity.Mathematics.float4x4 matrix);
```



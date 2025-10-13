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
public static float CalculateDistance(int lod, float4 lodParameters)
	{
		return CalculateDistanceFactor(lod) * lodParameters.x;
	}
```

- `public static CalculateDistanceFactor(System.Int32 lod) : System.Single`  

```csharp
public static float CalculateDistanceFactor(int lod)
	{
		return math.pow(2f, (float)(128 - lod) * (1f / 6f));
	}
```

- `public static CalculateLod(System.Single distanceSq, Unity.Mathematics.float4 lodParameters) : System.Int32`  

```csharp
public static int CalculateLod(float distanceSq, float4 lodParameters)
	{
		distanceSq *= lodParameters.y;
		return (255 - (math.asint(distanceSq * distanceSq * distanceSq) >> 23)) & 0xFF;
	}
```

- `public static CalculateLodLimit(System.Single metersPerPixel, System.Single bias) : System.Int32`  

```csharp
public static int CalculateLodLimit(float metersPerPixel)
	{
		float num = metersPerPixel * metersPerPixel;
		return (255 - (math.asint(num * num * num) >> 23)) & 0xFF;
	}
```

- `public static CalculateLodLimit(System.Single metersPerPixel) : System.Int32`  

```csharp
public static int CalculateLodLimit(float metersPerPixel)
	{
		float num = metersPerPixel * metersPerPixel;
		return (255 - (math.asint(num * num * num) >> 23)) & 0xFF;
	}
```

- `public static CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.BatchCullingContext cullingContext) : Unity.Mathematics.float4`  

```csharp
public static float4 CalculateLodParameters(float lodFactor, LODParameters lodParameters)
	{
		float num = 1f / math.tan(math.radians(lodParameters.fieldOfView * 0.5f));
		lodFactor *= 540f * num;
		return new float4(lodFactor, 1f / (lodFactor * lodFactor), num + 1f, num);
	}
```

- `public static CalculateLodParameters(System.Single lodFactor, UnityEngine.Rendering.LODParameters lodParameters) : Unity.Mathematics.float4`  

```csharp
public static float4 CalculateLodParameters(float lodFactor, LODParameters lodParameters)
	{
		float num = 1f / math.tan(math.radians(lodParameters.fieldOfView * 0.5f));
		lodFactor *= 540f * num;
		return new float4(lodFactor, 1f / (lodFactor * lodFactor), num + 1f, num);
	}
```

- `public static CalculateMaxDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters) : System.Single`  

```csharp
public static float CalculateMaxDistance(Bounds3 bounds, float3 cameraPosition, float3 cameraDirection, float4 lodParameters)
	{
		float3 @float = bounds.min - cameraPosition;
		float3 y = bounds.max - cameraPosition;
		float num = math.length(math.max(-@float, y));
		@float *= cameraDirection;
		y *= cameraDirection;
		return num * lodParameters.z - lodParameters.w * math.clamp(math.csum(math.min(@float, y)), 0f, num);
	}
```

- `public static CalculateMinDistance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 cameraDirection, Unity.Mathematics.float4 lodParameters) : System.Single`  

```csharp
public static float CalculateMinDistance(Bounds3 bounds, float3 cameraPosition, float3 cameraDirection, float4 lodParameters)
	{
		float3 x = bounds.min - cameraPosition;
		float3 @float = bounds.max - cameraPosition;
		float num = math.length(math.max(0f, math.max(x, -@float)));
		x *= cameraDirection;
		@float *= cameraDirection;
		return num * lodParameters.z - lodParameters.w * math.clamp(math.csum(math.max(x, @float)), 0f, num);
	}
```

- `public static FindBoneIndex(Unity.Entities.Entity prefab, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Int32 boneID, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.ProceduralBone, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& proceduralBoneBuffers) : Unity.Mathematics.int2`  

```csharp
public static int2 FindBoneIndex(Entity prefab, ref float3 position, ref quaternion rotation, int boneID, ref BufferLookup<SubMesh> subMeshBuffers, ref BufferLookup<ProceduralBone> proceduralBoneBuffers)
	{
		if (boneID > 0 && subMeshBuffers.TryGetBuffer(prefab, out var bufferData) && boneID >= bufferData.Length)
		{
			int num = 0;
			int2 result = default(int2);
			for (int i = 0; i < bufferData.Length; i++)
			{
				SubMesh subMesh = bufferData[i];
				if (proceduralBoneBuffers.TryGetBuffer(subMesh.m_SubMesh, out var bufferData2))
				{
					for (int j = 0; j < bufferData2.Length; j++)
					{
						ProceduralBone proceduralBone = bufferData2[j];
						if (proceduralBone.m_ConnectionID == boneID)
						{
							if ((subMesh.m_Flags & SubMeshFlags.HasTransform) != 0)
							{
								proceduralBone.m_ObjectPosition = subMesh.m_Position + math.rotate(subMesh.m_Rotation, proceduralBone.m_ObjectPosition);
								proceduralBone.m_ObjectRotation = math.mul(subMesh.m_Rotation, proceduralBone.m_ObjectRotation);
							}
							float4x4 a = float4x4.TRS(proceduralBone.m_ObjectPosition, proceduralBone.m_ObjectRotation, 1f);
							a = math.inverse(math.mul(a, proceduralBone.m_BindPose));
							position = math.transform(a, position);
							float3 forward = math.rotate(a, math.forward(rotation));
							float3 up = math.rotate(a, math.mul(rotation, math.up()));
							rotation = quaternion.LookRotation(forward, up);
							result.x = num + j;
							result.y = math.select(-1, i, (subMesh.m_Flags & SubMeshFlags.HasTransform) != 0);
							return result;
						}
					}
					num += bufferData2.Length;
				}
				boneID++;
			}
		}
		return -1;
	}
```

- `public static GetBlendWeight(Game.Prefabs.CharacterGroup+IndexWeight indexWeight) : Game.Rendering.BlendWeight`  

```csharp
public static BlendWeight GetBlendWeight(CharacterGroup.IndexWeight indexWeight)
	{
		return new BlendWeight
		{
			m_Index = indexWeight.index,
			m_Weight = indexWeight.weight
		};
	}
```

- `public static GetBlendWeights(Game.Prefabs.CharacterGroup+IndexWeight8 indexWeight8) : Game.Rendering.BlendWeights`  

```csharp
public static BlendWeights GetBlendWeights(CharacterGroup.IndexWeight8 indexWeight8)
	{
		return new BlendWeights
		{
			m_Weight0 = GetBlendWeight(indexWeight8.w0),
			m_Weight1 = GetBlendWeight(indexWeight8.w1),
			m_Weight2 = GetBlendWeight(indexWeight8.w2),
			m_Weight3 = GetBlendWeight(indexWeight8.w3),
			m_Weight4 = GetBlendWeight(indexWeight8.w4),
			m_Weight5 = GetBlendWeight(indexWeight8.w5),
			m_Weight6 = GetBlendWeight(indexWeight8.w6),
			m_Weight7 = GetBlendWeight(indexWeight8.w7)
		};
	}
```

- `public static GetRenderingSize(Unity.Mathematics.float3 size) : System.Single`  

```csharp
public static float GetRenderingSize(float3 boundsSize, float3 meshSize, float indexCount, StackDirection stackDirection)
	{
		switch (stackDirection)
		{
		case StackDirection.Right:
		{
			float indexFactor3 = indexCount / math.max(1f, meshSize.x);
			return GetRenderingSize(boundsSize.zy, indexFactor3);
		}
		case StackDirection.Up:
		{
			float indexFactor2 = indexCount / math.max(1f, meshSize.y);
			return GetRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz)), indexFactor2);
		}
		case StackDirection.Forward:
		{
			float indexFactor = indexCount / math.max(1f, meshSize.z);
			return GetRenderingSize(boundsSize.xy, indexFactor);
		}
		default:
			return GetRenderingSize(boundsSize, indexCount);
		}
	}
```

- `public static GetRenderingSize(Unity.Mathematics.float3 size, System.Single indexCount) : System.Single`  

```csharp
public static float GetRenderingSize(float3 boundsSize, float3 meshSize, float indexCount, StackDirection stackDirection)
	{
		switch (stackDirection)
		{
		case StackDirection.Right:
		{
			float indexFactor3 = indexCount / math.max(1f, meshSize.x);
			return GetRenderingSize(boundsSize.zy, indexFactor3);
		}
		case StackDirection.Up:
		{
			float indexFactor2 = indexCount / math.max(1f, meshSize.y);
			return GetRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz)), indexFactor2);
		}
		case StackDirection.Forward:
		{
			float indexFactor = indexCount / math.max(1f, meshSize.z);
			return GetRenderingSize(boundsSize.xy, indexFactor);
		}
		default:
			return GetRenderingSize(boundsSize, indexCount);
		}
	}
```

- `public static GetRenderingSize(Unity.Mathematics.float2 size) : System.Single`  

```csharp
public static float GetRenderingSize(float3 boundsSize, float3 meshSize, float indexCount, StackDirection stackDirection)
	{
		switch (stackDirection)
		{
		case StackDirection.Right:
		{
			float indexFactor3 = indexCount / math.max(1f, meshSize.x);
			return GetRenderingSize(boundsSize.zy, indexFactor3);
		}
		case StackDirection.Up:
		{
			float indexFactor2 = indexCount / math.max(1f, meshSize.y);
			return GetRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz)), indexFactor2);
		}
		case StackDirection.Forward:
		{
			float indexFactor = indexCount / math.max(1f, meshSize.z);
			return GetRenderingSize(boundsSize.xy, indexFactor);
		}
		default:
			return GetRenderingSize(boundsSize, indexCount);
		}
	}
```

- `public static GetRenderingSize(Unity.Mathematics.float2 size, System.Single indexFactor) : System.Single`  

```csharp
public static float GetRenderingSize(float3 boundsSize, float3 meshSize, float indexCount, StackDirection stackDirection)
	{
		switch (stackDirection)
		{
		case StackDirection.Right:
		{
			float indexFactor3 = indexCount / math.max(1f, meshSize.x);
			return GetRenderingSize(boundsSize.zy, indexFactor3);
		}
		case StackDirection.Up:
		{
			float indexFactor2 = indexCount / math.max(1f, meshSize.y);
			return GetRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz)), indexFactor2);
		}
		case StackDirection.Forward:
		{
			float indexFactor = indexCount / math.max(1f, meshSize.z);
			return GetRenderingSize(boundsSize.xy, indexFactor);
		}
		default:
			return GetRenderingSize(boundsSize, indexCount);
		}
	}
```

- `public static GetRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection) : System.Single`  

```csharp
public static float GetRenderingSize(float3 boundsSize, float3 meshSize, float indexCount, StackDirection stackDirection)
	{
		switch (stackDirection)
		{
		case StackDirection.Right:
		{
			float indexFactor3 = indexCount / math.max(1f, meshSize.x);
			return GetRenderingSize(boundsSize.zy, indexFactor3);
		}
		case StackDirection.Up:
		{
			float indexFactor2 = indexCount / math.max(1f, meshSize.y);
			return GetRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz)), indexFactor2);
		}
		case StackDirection.Forward:
		{
			float indexFactor = indexCount / math.max(1f, meshSize.z);
			return GetRenderingSize(boundsSize.xy, indexFactor);
		}
		default:
			return GetRenderingSize(boundsSize, indexCount);
		}
	}
```

- `public static GetRenderingSize(Unity.Mathematics.float3 boundsSize, Unity.Mathematics.float3 meshSize, System.Single indexCount, Game.Prefabs.StackDirection stackDirection) : System.Single`  

```csharp
public static float GetRenderingSize(float3 boundsSize, float3 meshSize, float indexCount, StackDirection stackDirection)
	{
		switch (stackDirection)
		{
		case StackDirection.Right:
		{
			float indexFactor3 = indexCount / math.max(1f, meshSize.x);
			return GetRenderingSize(boundsSize.zy, indexFactor3);
		}
		case StackDirection.Up:
		{
			float indexFactor2 = indexCount / math.max(1f, meshSize.y);
			return GetRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz)), indexFactor2);
		}
		case StackDirection.Forward:
		{
			float indexFactor = indexCount / math.max(1f, meshSize.z);
			return GetRenderingSize(boundsSize.xy, indexFactor);
		}
		default:
			return GetRenderingSize(boundsSize, indexCount);
		}
	}
```

- `public static GetShadowRenderingSize(Unity.Mathematics.float2 size) : System.Single`  

```csharp
public static float GetShadowRenderingSize(float3 boundsSize, StackDirection stackDirection)
	{
		return stackDirection switch
		{
			StackDirection.Right => GetShadowRenderingSize(boundsSize.zy), 
			StackDirection.Up => GetShadowRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz))), 
			StackDirection.Forward => GetShadowRenderingSize(boundsSize.xy), 
			_ => GetRenderingSize(boundsSize), 
		};
	}
```

- `public static GetShadowRenderingSize(Unity.Mathematics.float3 boundsSize, Game.Prefabs.StackDirection stackDirection) : System.Single`  

```csharp
public static float GetShadowRenderingSize(float3 boundsSize, StackDirection stackDirection)
	{
		return stackDirection switch
		{
			StackDirection.Right => GetShadowRenderingSize(boundsSize.zy), 
			StackDirection.Up => GetShadowRenderingSize(new float2(math.cmax(boundsSize.xz), math.cmin(boundsSize.xz))), 
			StackDirection.Forward => GetShadowRenderingSize(boundsSize.xy), 
			_ => GetRenderingSize(boundsSize), 
		};
	}
```

- `public static Lerp(Unity.Mathematics.float4 c0, Unity.Mathematics.float4 c0_5, Unity.Mathematics.float4 c1, System.Single t) : Unity.Mathematics.float4`  

```csharp
public static float4 Lerp(float4 c0, float4 c0_5, float4 c1, float t)
	{
		if (t <= 0.5f)
		{
			return math.lerp(c0, c0_5, t * 2f);
		}
		return math.lerp(c0_5, c1, t * 2f - 1f);
	}
```

- `public static SafeBounds(Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 SafeBounds(Bounds3 bounds)
	{
		float3 @float = math.min(0f, MathUtils.Size(bounds) - 0.01f);
		bounds.min += @float;
		bounds.max -= @float;
		return bounds;
	}
```

- `public static ToBounds(Colossal.Mathematics.Bounds3 bounds) : UnityEngine.Bounds`  

```csharp
public static Bounds ToBounds(Bounds3 bounds)
	{
		return new Bounds(MathUtils.Center(bounds), MathUtils.Size(bounds));
	}
```

- `public static ToColor(Unity.Mathematics.float4 vector) : UnityEngine.Color`  

```csharp
public static Color ToColor(float4 vector)
	{
		return new Color(vector.x, vector.y, vector.z, vector.w);
	}
```

- `public static ToMatrix4x4(Unity.Mathematics.float4x4 matrix) : UnityEngine.Matrix4x4`  

```csharp
public static Matrix4x4 ToMatrix4x4(float4x4 matrix)
	{
		Matrix4x4 result = default(Matrix4x4);
		result.SetColumn(0, matrix.c0);
		result.SetColumn(1, matrix.c1);
		result.SetColumn(2, matrix.c2);
		result.SetColumn(3, matrix.c3);
		return result;
	}
```



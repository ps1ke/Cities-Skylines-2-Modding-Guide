# Game.Rendering.Viewer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Viewer
{
    private UnityEngine.Camera <camera>k__BackingField;
    private Game.Rendering.ViewerDistances m_ViewerDistances;
    private System.Single m_TargetFocusDistance;
    private System.Single m_FocusDistanceVelocity;
    private System.Boolean <shadowsAdjustStartDistance>k__BackingField;
    private System.Single <pushCullingNearPlaneMultiplier>k__BackingField;
    private System.Single <pushCullingNearPlaneValue>k__BackingField;
    private System.Boolean <shadowsAdjustFarDistance>k__BackingField;
    private static System.Int32[] kSamplePattern32;
    private static const System.Int32 kCenterSampleCount;

    public Game.Rendering.ViewerDistances viewerDistances { get; }
    public System.Single visibilityDistance { get; }
    public System.Single nearClipPlane { get; }
    public Unity.Mathematics.float3 position { get; }
    public Unity.Mathematics.float3 forward { get; }
    public Unity.Mathematics.float3 right { get; }
    public UnityEngine.Camera camera { get; private set; }
    public Game.Rendering.Legacy.LegacyFrustumPlanes frustumPlanes { get; }
    public UnityEngine.Bounds bounds { get; }
    public System.Boolean shadowsAdjustStartDistance { get; set; }
    public System.Single pushCullingNearPlaneMultiplier { get; set; }
    public System.Single pushCullingNearPlaneValue { get; set; }
    public System.Boolean shadowsAdjustFarDistance { get; set; }

    public Viewer(UnityEngine.Camera camera);

    private static Game.Rendering.Legacy.LegacyFrustumPlanes CalculateFrustumPlanes(UnityEngine.Camera camera);
    private static Game.Rendering.Legacy.LegacyFrustumPlanes ExtractProjectionPlanes(Unity.Mathematics.float4x4 worldToProjectionMatrix);
    public System.Void Raycast(Game.Common.RaycastSystem raycast);
    public System.Boolean TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters);
    protected UnityEngine.Bounds UpdateBounds();
    private System.Void UpdateDistanceToSeaLevel();
    private System.Void UpdatePushNearCullingPlane();
    public System.Void UpdateRaycast(Game.Common.RaycastSystem raycast, System.Single deltaTime);
}
```


## Fields

- `private UnityEngine.Camera <camera>k__BackingField`  

```csharp
private UnityEngine.Camera <camera>k__BackingField;
```

- `private Game.Rendering.ViewerDistances m_ViewerDistances`  

```csharp
private Game.Rendering.ViewerDistances m_ViewerDistances;
```

- `private System.Single m_TargetFocusDistance`  

```csharp
private System.Single m_TargetFocusDistance;
```

- `private System.Single m_FocusDistanceVelocity`  

```csharp
private System.Single m_FocusDistanceVelocity;
```

- `private System.Boolean <shadowsAdjustStartDistance>k__BackingField`  

```csharp
private System.Boolean <shadowsAdjustStartDistance>k__BackingField;
```

- `private System.Single <pushCullingNearPlaneMultiplier>k__BackingField`  

```csharp
private System.Single <pushCullingNearPlaneMultiplier>k__BackingField;
```

- `private System.Single <pushCullingNearPlaneValue>k__BackingField`  

```csharp
private System.Single <pushCullingNearPlaneValue>k__BackingField;
```

- `private System.Boolean <shadowsAdjustFarDistance>k__BackingField`  

```csharp
private System.Boolean <shadowsAdjustFarDistance>k__BackingField;
```

- `private static System.Int32[] kSamplePattern32`  

```csharp
private static System.Int32[] kSamplePattern32;
```

- `private static const System.Int32 kCenterSampleCount`  

```csharp
private static const System.Int32 kCenterSampleCount;
```


## Properties

- `public Game.Rendering.ViewerDistances viewerDistances { get }`  

```csharp
public Game.Rendering.ViewerDistances viewerDistances { get; }
```

- `public System.Single visibilityDistance { get }`  

```csharp
public System.Single visibilityDistance { get; }
```

- `public System.Single nearClipPlane { get }`  

```csharp
public System.Single nearClipPlane { get; }
```

- `public Unity.Mathematics.float3 position { get }`  

```csharp
public Unity.Mathematics.float3 position { get; }
```

- `public Unity.Mathematics.float3 forward { get }`  

```csharp
public Unity.Mathematics.float3 forward { get; }
```

- `public Unity.Mathematics.float3 right { get }`  

```csharp
public Unity.Mathematics.float3 right { get; }
```

- `public UnityEngine.Camera camera { get; private set }`  

```csharp
public UnityEngine.Camera camera { get; private set; }
```

- `public Game.Rendering.Legacy.LegacyFrustumPlanes frustumPlanes { get }`  

```csharp
public Game.Rendering.Legacy.LegacyFrustumPlanes frustumPlanes { get; }
```

- `public UnityEngine.Bounds bounds { get }`  

```csharp
public UnityEngine.Bounds bounds { get; }
```

- `public System.Boolean shadowsAdjustStartDistance { get; set }`  

```csharp
public System.Boolean shadowsAdjustStartDistance { get; set; }
```

- `public System.Single pushCullingNearPlaneMultiplier { get; set }`  

```csharp
public System.Single pushCullingNearPlaneMultiplier { get; set; }
```

- `public System.Single pushCullingNearPlaneValue { get; set }`  

```csharp
public System.Single pushCullingNearPlaneValue { get; set; }
```

- `public System.Boolean shadowsAdjustFarDistance { get; set }`  

```csharp
public System.Boolean shadowsAdjustFarDistance { get; set; }
```


## Constructors

- `public Viewer(UnityEngine.Camera camera)`  

```csharp
public Viewer(Camera camera)
	{
		this.camera = camera;
	}
```


## Methods

- `private static CalculateFrustumPlanes(UnityEngine.Camera camera) : Game.Rendering.Legacy.LegacyFrustumPlanes`  

```csharp
private static LegacyFrustumPlanes CalculateFrustumPlanes(Camera camera)
	{
		return ExtractProjectionPlanes(camera.projectionMatrix * camera.worldToCameraMatrix);
	}
```

- `private static ExtractProjectionPlanes(Unity.Mathematics.float4x4 worldToProjectionMatrix) : Game.Rendering.Legacy.LegacyFrustumPlanes`  

```csharp
private static LegacyFrustumPlanes ExtractProjectionPlanes(float4x4 worldToProjectionMatrix)
	{
		LegacyFrustumPlanes result = default(LegacyFrustumPlanes);
		float4 @float = new float4(worldToProjectionMatrix.c0.w, worldToProjectionMatrix.c1.w, worldToProjectionMatrix.c2.w, worldToProjectionMatrix.c3.w);
		float4 float2 = new float4(worldToProjectionMatrix.c0.x, worldToProjectionMatrix.c1.x, worldToProjectionMatrix.c2.x, worldToProjectionMatrix.c3.x);
		float3 float3 = new float3(float2.x + @float.x, float2.y + @float.y, float2.z + @float.z);
		float num = 1f / math.length(float3);
		result.left.normal = float3 * num;
		result.left.distance = (float2.w + @float.w) * num;
		float3 = new float3(0f - float2.x + @float.x, 0f - float2.y + @float.y, 0f - float2.z + @float.z);
		num = 1f / math.length(float3);
		result.right.normal = float3 * num;
		result.right.distance = (0f - float2.w + @float.w) * num;
		float2 = new float4(worldToProjectionMatrix.c0.y, worldToProjectionMatrix.c1.y, worldToProjectionMatrix.c2.y, worldToProjectionMatrix.c3.y);
		float3 = new Vector3(float2.x + @float.x, float2.y + @float.y, float2.z + @float.z);
		num = 1f / math.length(float3);
		result.bottom.normal = float3 * num;
		result.bottom.distance = (float2.w + @float.w) * num;
		float3 = new Vector3(0f - float2.x + @float.x, 0f - float2.y + @float.y, 0f - float2.z + @float.z);
		num = 1f / math.length(float3);
		result.top.normal = float3 * num;
		result.top.distance = (0f - float2.w + @float.w) * num;
		float2 = new float4(worldToProjectionMatrix.c0.z, worldToProjectionMatrix.c1.z, worldToProjectionMatrix.c2.z, worldToProjectionMatrix.c3.z);
		float3 = new Vector3(float2.x + @float.x, float2.y + @float.y, float2.z + @float.z);
		num = 1f / math.length(float3);
		result.zNear.normal = float3 * num;
		result.zNear.distance = (float2.w + @float.w) * num;
		float3 = new Vector3(0f - float2.x + @float.x, 0f - float2.y + @float.y, 0f - float2.z + @float.z);
		num = 1f / math.length(float3);
		result.zFar.normal = float3 * num;
		result.zFar.distance = (0f - float2.w + @float.w) * num;
		return result;
	}
```

- `public Raycast(Game.Common.RaycastSystem raycast) : System.Void`  

```csharp
public void Raycast(RaycastSystem raycast)
	{
		float3 @float = position;
		RaycastInput input = new RaycastInput
		{
			m_Flags = (RaycastFlags)0u,
			m_CollisionMask = (CollisionMask.OnGround | CollisionMask.Overground),
			m_NetLayerMask = Layer.All
		};
		input.m_TypeMask = TypeMask.Terrain | TypeMask.Water;
		input.m_Line = new Line3.Segment(@float, @float + (float3)Vector3.down * visibilityDistance);
		raycast.AddInput(this, input);
		for (int i = 0; i < kSamplePattern32.Length; i += 2)
		{
			float x = (float)kSamplePattern32[i] / 7f * 0.5f + 0.5f;
			float y = (float)kSamplePattern32[i + 1] / 7f * 0.5f + 0.5f;
			Ray ray = camera.ViewportPointToRay(new Vector3(x, y, 0f));
			if (i < 8)
			{
				input.m_TypeMask = TypeMask.Terrain | TypeMask.StaticObjects | TypeMask.MovingObjects | TypeMask.Net | TypeMask.Water;
			}
			else
			{
				input.m_TypeMask = TypeMask.Terrain | TypeMask.Water;
			}
			input.m_Line = new Line3.Segment(@float, @float + (float3)ray.direction * visibilityDistance);
			raycast.AddInput(this, input);
		}
	}
```

- `public TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters) : System.Boolean`  

```csharp
public bool TryGetLODParameters(out LODParameters lodParameters)
	{
		if (camera.TryGetCullingParameters(out var cullingParameters))
		{
			lodParameters = cullingParameters.lodParameters;
			return true;
		}
		lodParameters = default(LODParameters);
		return false;
	}
```

- `protected UpdateBounds() : UnityEngine.Bounds`  

```csharp
protected Bounds UpdateBounds()
	{
		Transform transform = camera.transform;
		float num = math.tan(math.radians(camera.fieldOfView * 0.5f));
		float num2 = num * camera.aspect;
		float3 @float = transform.forward;
		float3 float2 = transform.right;
		float3 float3 = transform.up;
		float farClipPlane = camera.farClipPlane;
		float num3 = camera.nearClipPlane;
		float3 float4 = position;
		float3 float5 = float4 + @float * farClipPlane - farClipPlane * float2 * num2 + float3 * num * farClipPlane;
		float3 float6 = float4 + @float * farClipPlane + farClipPlane * float2 * num2 - float3 * num * farClipPlane;
		float3 float7 = float4 + @float * farClipPlane - farClipPlane * float2 * num2 - float3 * num * farClipPlane;
		float3 float8 = float4 + @float * farClipPlane + farClipPlane * float2 * num2 + float3 * num * farClipPlane;
		float3 float9 = float4 + @float * num3;
		Bounds result = new Bounds(Vector3.zero, Vector3.one * float.NegativeInfinity);
		result.Encapsulate(float5);
		result.Encapsulate(float6);
		result.Encapsulate(float7);
		result.Encapsulate(float8);
		result.Encapsulate(float9);
		return result;
	}
```

- `private UpdateDistanceToSeaLevel() : System.Void`  

```csharp
private void UpdateDistanceToSeaLevel()
	{
		float num = 0f;
		UnityEngine.Plane plane = new UnityEngine.Plane(Vector3.up, 0f - WaterSystem.SeaLevel);
		for (int i = 0; i < 4; i++)
		{
			float x = (((i & 1) != 0) ? 1f : 0f);
			float y = (((i & 2) != 0) ? 1f : 0f);
			Ray ray = camera.ViewportPointToRay(new Vector3(x, y, 0f));
			num = (plane.Raycast(ray, out var enter) ? math.max(num, enter) : visibilityDistance);
		}
		m_ViewerDistances.maxDistanceToSeaLevel = num;
	}
```

- `private UpdatePushNearCullingPlane() : System.Void`  

```csharp
private void UpdatePushNearCullingPlane()
	{
		HDCamera orCreate = HDCamera.GetOrCreate(camera);
		if (orCreate != null)
		{
			if (shadowsAdjustStartDistance)
			{
				float valueToClamp = (m_ViewerDistances.closestSurface - pushCullingNearPlaneValue) * pushCullingNearPlaneMultiplier;
				valueToClamp = math.clamp(valueToClamp, nearClipPlane, visibilityDistance * 0.1f);
				orCreate.overrideNearPlaneForCullingOnly = valueToClamp;
			}
			else
			{
				orCreate.overrideNearPlaneForCullingOnly = 0f;
			}
		}
	}
```

- `public UpdateRaycast(Game.Common.RaycastSystem raycast, System.Single deltaTime) : System.Void`  

```csharp
public void UpdateRaycast(RaycastSystem raycast, float deltaTime)
	{
		float3 x = position;
		NativeArray<RaycastResult> result = raycast.GetResult(this);
		float num = visibilityDistance;
		float num2 = 0f;
		float num3 = 0f;
		float num4 = 0f;
		float num5 = -1f;
		for (int i = 0; i < result.Length; i++)
		{
			RaycastResult raycastResult = result[i];
			if (!(raycastResult.m_Owner == Entity.Null))
			{
				float num6 = math.distance(x, raycastResult.m_Hit.m_HitPosition);
				if (i == 0)
				{
					m_ViewerDistances.ground = num6;
					continue;
				}
				if (i - 1 < 4)
				{
					num5 = math.max(num5, num6);
					continue;
				}
				num = math.min(num, num6);
				num2 = math.max(num2, num6);
				num3 += num6;
				num4 += 1f;
			}
		}
		m_ViewerDistances.closestSurface = num;
		m_ViewerDistances.farthestSurface = num2;
		m_ViewerDistances.averageSurface = (num + num2) / 2f;
		if (num4 > 0f)
		{
			m_ViewerDistances.averageSurface = num3 / num4;
		}
		if (num5 >= 0f)
		{
			m_TargetFocusDistance = num5;
		}
		m_ViewerDistances.focus = MathUtils.SmoothDamp(m_ViewerDistances.focus, m_TargetFocusDistance, ref m_FocusDistanceVelocity, 0.3f, float.MaxValue, deltaTime);
		if (camera != null)
		{
			camera.focusDistance = m_ViewerDistances.focus;
			UpdatePushNearCullingPlane();
			UpdateDistanceToSeaLevel();
		}
	}
```



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
public Viewer(UnityEngine.Camera camera);
```


## Methods

- `private static CalculateFrustumPlanes(UnityEngine.Camera camera) : Game.Rendering.Legacy.LegacyFrustumPlanes`  

```csharp
private static Game.Rendering.Legacy.LegacyFrustumPlanes CalculateFrustumPlanes(UnityEngine.Camera camera);
```

- `private static ExtractProjectionPlanes(Unity.Mathematics.float4x4 worldToProjectionMatrix) : Game.Rendering.Legacy.LegacyFrustumPlanes`  

```csharp
private static Game.Rendering.Legacy.LegacyFrustumPlanes ExtractProjectionPlanes(Unity.Mathematics.float4x4 worldToProjectionMatrix);
```

- `public Raycast(Game.Common.RaycastSystem raycast) : System.Void`  

```csharp
public System.Void Raycast(Game.Common.RaycastSystem raycast);
```

- `public TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters) : System.Boolean`  

```csharp
public System.Boolean TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters);
```

- `protected UpdateBounds() : UnityEngine.Bounds`  

```csharp
protected UnityEngine.Bounds UpdateBounds();
```

- `private UpdateDistanceToSeaLevel() : System.Void`  

```csharp
private System.Void UpdateDistanceToSeaLevel();
```

- `private UpdatePushNearCullingPlane() : System.Void`  

```csharp
private System.Void UpdatePushNearCullingPlane();
```

- `public UpdateRaycast(Game.Common.RaycastSystem raycast, System.Single deltaTime) : System.Void`  

```csharp
public System.Void UpdateRaycast(Game.Common.RaycastSystem raycast, System.Single deltaTime);
```



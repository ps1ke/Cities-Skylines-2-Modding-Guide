# Game.Rendering.Viewer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private UnityEngine.Camera <camera>k__BackingField`  
- `private Game.Rendering.ViewerDistances m_ViewerDistances`  
- `private System.Single m_TargetFocusDistance`  
- `private System.Single m_FocusDistanceVelocity`  
- `private System.Boolean <shadowsAdjustStartDistance>k__BackingField`  
- `private System.Single <pushCullingNearPlaneMultiplier>k__BackingField`  
- `private System.Single <pushCullingNearPlaneValue>k__BackingField`  
- `private System.Boolean <shadowsAdjustFarDistance>k__BackingField`  
- `private static System.Int32[] kSamplePattern32`  
- `private static const System.Int32 kCenterSampleCount`  

## Properties

- `public Game.Rendering.ViewerDistances viewerDistances { get }`  
- `public System.Single visibilityDistance { get }`  
- `public System.Single nearClipPlane { get }`  
- `public Unity.Mathematics.float3 position { get }`  
- `public Unity.Mathematics.float3 forward { get }`  
- `public Unity.Mathematics.float3 right { get }`  
- `public UnityEngine.Camera camera { get; private set }`  
- `public Game.Rendering.Legacy.LegacyFrustumPlanes frustumPlanes { get }`  
- `public UnityEngine.Bounds bounds { get }`  
- `public System.Boolean shadowsAdjustStartDistance { get; set }`  
- `public System.Single pushCullingNearPlaneMultiplier { get; set }`  
- `public System.Single pushCullingNearPlaneValue { get; set }`  
- `public System.Boolean shadowsAdjustFarDistance { get; set }`  

## Constructors

- `public Viewer(UnityEngine.Camera camera)`  

## Methods

- `private static CalculateFrustumPlanes(UnityEngine.Camera camera) : Game.Rendering.Legacy.LegacyFrustumPlanes`  
- `private static ExtractProjectionPlanes(Unity.Mathematics.float4x4 worldToProjectionMatrix) : Game.Rendering.Legacy.LegacyFrustumPlanes`  
- `public Raycast(Game.Common.RaycastSystem raycast) : System.Void`  
- `public TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters) : System.Boolean`  
- `protected UpdateBounds() : UnityEngine.Bounds`  
- `private UpdateDistanceToSeaLevel() : System.Void`  
- `private UpdatePushNearCullingPlane() : System.Void`  
- `public UpdateRaycast(Game.Common.RaycastSystem raycast, System.Single deltaTime) : System.Void`  


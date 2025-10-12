# Game.Rendering.CameraUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.RaycastSystem m_RaycastSystem`  
- `private UnityEngine.Rendering.Volume m_Volume`  
- `private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField`  
- `private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings`  
- `private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance`  
- `private Unity.Mathematics.float4 m_StoredShadowBorders`  
- `private Game.Input.InputActivator[] m_CameraActionActivators`  
- `private Game.Input.InputBarrier[] m_CameraActionBarriers`  
- `private Game.Rendering.Viewer <activeViewer>k__BackingField`  
- `private Game.CameraController <gamePlayController>k__BackingField`  
- `private Game.CinematicCameraController <cinematicCameraController>k__BackingField`  
- `private Game.OrbitCameraController <orbitCameraController>k__BackingField`  
- `private System.Single <nearClipPlane>k__BackingField`  
- `private Unity.Mathematics.float3 <position>k__BackingField`  
- `private Unity.Mathematics.float3 <direction>k__BackingField`  
- `private System.Single <zoom>k__BackingField`  

## Properties

- `public Game.Rendering.Viewer activeViewer { get; private set }`  
- `public Game.CameraController gamePlayController { get; set }`  
- `public Game.CinematicCameraController cinematicCameraController { get; set }`  
- `public Game.OrbitCameraController orbitCameraController { get; set }`  
- `public UnityEngine.Camera activeCamera { get; set }`  
- `public System.Single nearClipPlane { get; private set }`  
- `public Unity.Mathematics.float3 position { get; private set }`  
- `public Unity.Mathematics.float3 direction { get; private set }`  
- `public System.Single zoom { get; private set }`  
- `public Game.Rendering.IGameCameraController activeCameraController { get; set }`  

## Constructors

- `public CameraUpdateSystem()`  

## Methods

- `private CheckOrCacheViewer() : System.Boolean`  
- `public GetBlendWeight(System.Single& weight) : Game.Rendering.CameraBlend`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RefreshInput() : System.Void`  
- `public TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters) : System.Boolean`  
- `public TryGetViewer(Game.Rendering.Viewer& viewer) : System.Boolean`  
- `private UpdateDepthOfField(System.Single distance) : System.Void`  
- `private UpdateShadows(Game.Rendering.Viewer viewer) : System.Void`  

## Nested types

- `Game.Rendering.CameraUpdateSystem+<>c`  


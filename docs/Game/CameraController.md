# Game.CameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Fields

- `private Unity.Mathematics.float3 m_Pivot`  
- `private Unity.Mathematics.float2 m_Angle`  
- `private System.Single m_Zoom`  
- `private Colossal.Mathematics.Bounds1 m_ZoomRange`  
- `private Colossal.Mathematics.Bounds1 m_MapTileToolZoomRange`  
- `private System.Boolean m_MapTileToolViewEnabled`  
- `private System.Single m_MapTileToolFOV`  
- `private System.Single m_MapTileToolFarclip`  
- `private Unity.Mathematics.float3 m_MapTileToolPivot`  
- `private Unity.Mathematics.float2 m_MapTileToolAngle`  
- `private System.Single m_MapTileToolZoom`  
- `private System.Single m_MapTileToolTransitionTime`  
- `private System.Single m_MoveSmoothing`  
- `private System.Single m_CollisionSmoothing`  
- `private Game.Input.ProxyActionMap m_CameraMap`  
- `private Game.Input.ProxyAction m_MoveAction`  
- `private Game.Input.ProxyAction m_MoveFastAction`  
- `private Game.Input.ProxyAction m_RotateAction`  
- `private Game.Input.ProxyAction m_ZoomAction`  
- `private Cinemachine.CinemachineVirtualCamera m_VCam`  
- `private System.Single m_InitialFarClip`  
- `private System.Single m_InitialFov`  
- `private System.Single m_LastGameViewZoom`  
- `private Unity.Mathematics.float2 m_LastGameViewAngle`  
- `private Unity.Mathematics.float3 m_LastGameViewPivot`  
- `private System.Single m_LastMapViewZoom`  
- `private Unity.Mathematics.float2 m_LastMapViewAngle`  
- `private Unity.Mathematics.float3 m_LastMapViewPivot`  
- `private System.Action<System.Boolean> <EventCameraMovingChanged>k__BackingField`  
- `private System.Boolean <moving>k__BackingField`  
- `private System.Boolean <inputEnabled>k__BackingField`  
- `private Unity.Mathematics.float3 <cameraPosition>k__BackingField`  
- `private System.Single <velocity>k__BackingField`  
- `private System.Single m_MapViewTimer`  
- `private System.Boolean <edgeScrolling>k__BackingField`  
- `private System.Single <edgeScrollingSensitivity>k__BackingField`  
- `private System.Single <clipDistance>k__BackingField`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Rendering.CameraUpdateSystem m_CameraSystem`  
- `private Game.Rendering.CameraCollisionSystem m_CollisionSystem`  

## Properties

- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> inputActions { get }`  
- `public System.Action<System.Boolean> EventCameraMovingChanged { get; set }`  
- `public System.Boolean moving { get; private set }`  
- `public Cinemachine.LensSettings& lens { get }`  
- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  
- `public UnityEngine.Vector3 rotation { get; set }`  
- `public Game.Simulation.TerrainSystem terrainSystem { get }`  
- `public Game.Simulation.WaterSystem waterSystem { get }`  
- `public UnityEngine.Vector3 pivot { get; set }`  
- `public UnityEngine.Vector3 position { get; set }`  
- `public Unity.Mathematics.float2 angle { get; set }`  
- `public System.Single zoom { get; set }`  
- `public System.Boolean controllerEnabled { get; set }`  
- `public System.Boolean inputEnabled { get; set }`  
- `public Colossal.Mathematics.Bounds1 zoomRange { get }`  
- `public Unity.Mathematics.float3 cameraPosition { get; private set }`  
- `public System.Single velocity { get; private set }`  
- `public System.Boolean edgeScrolling { get; set }`  
- `public System.Single edgeScrollingSensitivity { get; set }`  
- `public System.Single clipDistance { get; set }`  

## Constructors

- `public CameraController()`  

## Methods

- `private Awake() : System.Void`  
- `private GetCameraPos(Unity.Mathematics.float3 cameraOffset) : Unity.Mathematics.float3`  
- `private HandleMapViewCamera() : System.Boolean`  
- `public static LerpAngle(Unity.Mathematics.float2 from, Unity.Mathematics.float2 to, System.Single t) : Unity.Mathematics.float2`  
- `public static TryGet(Game.CameraController& cameraController) : System.Boolean`  
- `private TryGetTerrainHeight(UnityEngine.Vector3 pos, System.Single& terrainHeight) : System.Boolean`  
- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  
- `public UpdateCamera() : System.Void`  

## Nested types

- `Game.CameraController+<Awake>d__95`  
- `Game.CameraController+<get_inputActions>d__20`  


# Game.CinematicCameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Fields

- `private System.Single m_MinMoveSpeed`  
- `private System.Single m_MaxMoveSpeed`  
- `private System.Single m_MinZoomSpeed`  
- `private System.Single m_MaxZoomSpeed`  
- `private System.Single m_RotateSpeed`  
- `private System.Single m_MaxHeight`  
- `private System.Single m_MaxMovementSpeedHeight`  
- `private UnityEngine.Transform m_Anchor`  
- `private Cinemachine.CinemachineVirtualCamera m_VCam`  
- `private Game.CinemachineRestrictToTerrain m_RestrictToTerrain`  
- `private Game.CameraInput m_CameraInput`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private System.Action <eventCameraMove>k__BackingField`  
- `private System.Boolean <inputEnabled>k__BackingField`  

## Properties

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  
- `public System.Single zoom { get; set }`  
- `public UnityEngine.Vector3 pivot { get; set }`  
- `public UnityEngine.Vector3 position { get; set }`  
- `public UnityEngine.Vector3 rotation { get; set }`  
- `public System.Boolean controllerEnabled { get; set }`  
- `public System.Boolean collisionsEnabled { get; set }`  
- `public Cinemachine.LensSettings& lens { get }`  
- `public System.Action eventCameraMove { get; set }`  
- `public System.Single fov { get; set }`  
- `public System.Single dutch { get; set }`  
- `public System.Boolean inputEnabled { get; set }`  

## Constructors

- `public CinematicCameraController()`  

## Methods

- `private Awake() : System.Void`  
- `private OnDestroy() : System.Void`  
- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  
- `public UpdateCamera() : System.Void`  
- `private UpdateController(Game.CameraInput input) : System.Void`  

## Nested types

- `Game.CinematicCameraController+<Awake>d__48`  


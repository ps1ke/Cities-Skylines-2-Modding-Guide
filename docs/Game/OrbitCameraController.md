# Game.OrbitCameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Fields

- `public Unity.Mathematics.float2 m_ZoomRange`  
- `public System.Single m_FollowSmoothing`  
- `private Unity.Entities.Entity m_Entity`  
- `private System.Single m_FollowTimer`  
- `private Game.OrbitCameraController+Mode <mode>k__BackingField`  
- `private Unity.Mathematics.float2 m_Rotation`  
- `private UnityEngine.GameObject m_Anchor`  
- `private Cinemachine.CinemachineVirtualCamera m_VCam`  
- `private Cinemachine.CinemachineOrbitalTransposer m_Transposer`  
- `private Game.CinemachineRestrictToTerrain m_Collider`  
- `private Game.CameraInput m_CameraInput`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private System.Boolean <inputEnabled>k__BackingField`  
- `private System.Single <zoom>k__BackingField`  
- `private System.Single <yOffset>k__BackingField`  
- `private System.Single <xOffset>k__BackingField`  
- `private System.Action <EventCameraMove>k__BackingField`  
- `private static readonly System.Single kPivotVerticalOffset`  

## Properties

- `public Unity.Entities.Entity followedEntity { get; set }`  
- `public Game.OrbitCameraController+Mode mode { get; set }`  
- `public UnityEngine.Vector3 pivot { get; set }`  
- `public UnityEngine.Vector3 position { get; set }`  
- `public System.Boolean controllerEnabled { get; set }`  
- `public System.Boolean inputEnabled { get; set }`  
- `public UnityEngine.Vector3 rotation { get; set }`  
- `public System.Single zoom { get; set }`  
- `public System.Single yOffset { get; set }`  
- `public System.Single xOffset { get; set }`  
- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  
- `public Cinemachine.LensSettings& lens { get }`  
- `public System.Boolean collisionsEnabled { get; set }`  
- `public System.Action EventCameraMove { get; set }`  

## Constructors

- `public OrbitCameraController()`  

## Methods

- `private Awake() : System.Void`  
- `private OnDestroy() : System.Void`  
- `private OnDisable() : System.Void`  
- `private OnEnable() : System.Void`  
- `private RefreshAudioFollow(System.Boolean active) : System.Void`  
- `private static TryGetPosition(Unity.Entities.Entity e, Unity.Entities.EntityManager entityManager, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Single& radius) : System.Boolean`  
- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  
- `public UpdateCamera() : System.Void`  

## Nested types

- `Game.OrbitCameraController+Mode`  
- `Game.OrbitCameraController+<Awake>d__59`  


# Game.OrbitCameraController

**Assembly:**  
Assembly-CSharp (game runtime)

**Namespace:**  
Game

**Type:**  
class OrbitCameraController

**Base:**  
UnityEngine.MonoBehaviour, IGameCameraController

**Summary:** The OrbitCameraController is the game's general-purpose orbiting camera used by gameplay, photo mode and editor modes. It integrates with Cinemachine (virtual camera, orbital transposer and terrain collision helper), receives input from CameraInput, updates the AudioManager listener/follow target, and is registered with the game's CameraUpdateSystem. It supports following entities, free orbiting, zooming and panning while clamping to terrain and a configured zoom range. This class is intended for Cities: Skylines 2 modding to inspect or extend in-game camera behavior.
---

## Fields

- `private static readonly System.Single kPivotVerticalOffset`  
Constant vertical offset (10f) used to keep the pivot point above terrain center when clamping to terrain.

- `public Unity.Mathematics.float2 m_ZoomRange`  
Public zoom range (min,max) expressed as float2. Default is (10f, 10000f). Used to clamp zoom.

- `public System.Single m_FollowSmoothing`  
Smoothing factor for following targets (default ~0.01f). Controls interpolation when the camera follows an entity.

- `private Unity.Entities.Entity m_Entity`  
Backing field for the followed entity. Entity.Null means no follow target.

- `private System.Single m_FollowTimer`  
Internal timer used to modulate follow smoothing over time.

- `private Unity.Mathematics.float2 m_Rotation`  
Internal rotation state stored as (yaw, pitch) in degrees (x = yaw, y = pitch).

- `private UnityEngine.GameObject m_Anchor`  
A dynamically created anchor GameObject used as the LookAt/Follow target for the Cinemachine virtual camera.

- `private Cinemachine.CinemachineVirtualCamera m_VCam`  
Reference to the Cinemachine virtual camera component on the same GameObject.

- `private Cinemachine.CinemachineOrbitalTransposer m_Transposer`  
Reference to the Cinemachine orbital transposer component used to position the camera relative to the anchor.

- `private CinemachineRestrictToTerrain m_Collider`  
Helper component that clamps camera positions to terrain and optionally restricts to the map area.

- `private CameraInput m_CameraInput`  
Component that provides camera input (rotation, zoom, movement). May be null if not present.

- `private CameraUpdateSystem m_CameraUpdateSystem`  
Reference to the game's CameraUpdateSystem; the controller registers itself there so it can be updated by the game world.

## Properties

- `public Unity.Entities.Entity followedEntity { get; set; }`  
Gets or sets the entity the camera should follow. Setting this resets follow offsets/timer and refreshes audio follow target if the component is enabled. If the component is disabled the getter returns Entity.Null.

- `public Mode mode { get; set; }`  
Current mode of the orbit camera (Follow, PhotoMode, Editor). Mode affects how the camera is used by UI/scene flow but is otherwise a simple enum property.

- `public UnityEngine.Vector3 pivot { get; set; }`  
World-space pivot point used by the camera anchor. Getting/setting read/writes m_Anchor.transform.position.

- `public UnityEngine.Vector3 position { get; set; }`  
Camera GameObject position. Setting also positions the anchor along the camera's forward with respect to the current zoom so Cinemachine follows correctly.

- `public bool controllerEnabled { get; set; }`  
Enable/disable the controller GameObject. Setting toggles the GameObject active state. Getting returns isActiveAndEnabled.

- `public bool inputEnabled { get; set; }`  
Whether camera input is processed. Default true. When false user input (rotate/zoom/move) is ignored.

- `public UnityEngine.Vector3 rotation { get; set; }`  
World Euler rotation of the anchor (degrees). Setting writes to m_Rotation (yaw, pitch).

- `public System.Single zoom { get; set; }`  
Distance from the anchor pivot to the camera (used to set Cinemachine transposer offset). Clamped to m_ZoomRange during Awake and when applying input.

- `public System.Single yOffset { get; set; }`  
Vertical offset applied to the anchor when following a target.

- `public System.Single xOffset { get; set; }`  
Horizontal offset applied to the anchor when following a target.

- `public Cinemachine.ICinemachineCamera virtualCamera { get; }`  
Read-only accessor to the Cinemachine virtual camera instance.

- `public ref Cinemachine.LensSettings lens { get; }`  
Ref accessor to the Cinemachine lens settings on the virtual camera (m_VCam.m_Lens). Useful to read/modify FOV and other lens properties directly.

- `public bool collisionsEnabled { get; set; }`  
Wraps m_Collider.enableObjectCollisions; enables or disables object collision checks for the CinemachineRestrictToTerrain component.

- `public System.Action EventCameraMove { get; set; }`  
Event invoked when the camera is moved by input or when map tile view is active (used by UI to react to camera movement).

## Constructors

- `public OrbitCameraController()`  
Default Unity constructor. Instances are created by the engine when the MonoBehaviour is added to a GameObject. Initialization is performed asynchronously in Awake once the GameManager is ready.

## Methods

- `private async void Awake()`  
Async initialization executed after GameManager reports ready. Creates the anchor GameObject, finds and wires Cinemachine components (virtual camera, transposer, terrain collider), initializes CameraInput, registers with CameraUpdateSystem and clamps initial zoom. Also disables the controller GameObject by default until explicitly enabled.

- `private void OnEnable()`  
Enables audio follow target when the controller is enabled.

- `private void OnDisable()`  
Disables audio follow target when the controller is disabled.

- `private void RefreshAudioFollow(bool active)`  
Utility called from OnEnable/OnDisable and when changing followedEntity: sets AudioManager.instance.followed to the current followed entity or Entity.Null.

- `private void OnDestroy()`  
Cleanup: destroys the dynamically created anchor GameObject and clears references on CameraUpdateSystem.

- `public void TryMatchPosition(IGameCameraController other)`  
Copy rotation/zoom/pivot state from another IGameCameraController. For CinematicCameraController it computes pivot/zoom so the perspectives match by clamping to terrain and accounting for target height. For other camera types it copies zoom and pivot directly.

- `public void UpdateCamera()`  
Main update routine called by the CameraUpdateSystem. Refreshes collider/input, processes user input (rotation, zoom, movement), handles free panning or following an entity (with smoothing), updates Cinemachine transposer offset to reflect zoom + target radius, updates the AudioListener and fires EventCameraMove when appropriate.

- `private static bool TryGetPosition(Entity e, EntityManager entityManager, out Unity.Mathematics.float3 position, out Unity.Mathematics.quaternion rotation, out System.Single radius)`  
Helper to query selected entity position, rotation and bounding radius using SelectedInfoUISystem.TryGetPosition. Returns true when a valid position was retrieved; otherwise out parameters are zeroed and returns false.

```csharp
private async void Awake()
{
    if (await GameManager.instance.WaitForReadyState())
    {
        m_Anchor = new GameObject("OrbitCameraAnchor");
        Transform transform = m_Anchor.transform;
        m_VCam = GetComponent<CinemachineVirtualCamera>();
        m_Transposer = m_VCam.GetCinemachineComponent<CinemachineOrbitalTransposer>();
        m_Collider = GetComponent<CinemachineRestrictToTerrain>();
        if (m_VCam != null)
        {
            m_VCam.LookAt = transform;
            m_VCam.Follow = transform;
        }
        base.gameObject.SetActive(value: false);
        m_CameraInput = GetComponent<CameraInput>();
        if (m_CameraInput != null)
        {
            m_CameraInput.Initialize();
        }
        m_CameraUpdateSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraUpdateSystem>();
        m_CameraUpdateSystem.orbitCameraController = this;
        zoom = Mathf.Clamp(zoom, m_ZoomRange.x, m_ZoomRange.y);
    }
}
```


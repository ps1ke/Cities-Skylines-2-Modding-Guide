# Game.CinematicCameraController

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** class

**Base:** MonoBehaviour, IGameCameraController

**Summary:** A cinematic/free-roam camera controller used by the game for cutscenes or free camera movement. It drives a Cinemachine virtual camera by moving and rotating an internal anchor Transform, supports configurable move/zoom/rotation speeds, terrain clamping and simple collision handling, and integrates with the game's CameraUpdateSystem and AudioManager.
---

## Fields

- `private float m_MinMoveSpeed`  
Minimum lateral movement speed (when close to terrain). Serialized so it can be tweaked in the inspector.

- `private float m_MaxMoveSpeed`  
Maximum lateral movement speed (when high above terrain). Serialized.

- `private float m_MinZoomSpeed`  
Minimum zoom (vertical movement) speed. Serialized.

- `private float m_MaxZoomSpeed`  
Maximum zoom speed. Serialized.

- `private float m_RotateSpeed`  
Rotation sensitivity used to convert input to pitch/yaw changes. Serialized.

- `private float m_MaxHeight`  
Maximum height above terrain the camera anchor may reach.

- `private float m_MaxMovementSpeedHeight`  
Height used to lerp between min and max movement/zoom speeds; above this height movement uses the max speeds.

- `private Transform m_Anchor`  
Internal anchor Transform created at runtime. The Cinemachine virtual camera follows this anchor; the anchor holds the world position/rotation used by the cinematic camera.

- `private CinemachineVirtualCamera m_VCam`  
Reference to the Cinemachine virtual camera component on the same GameObject.

- `private CinemachineRestrictToTerrain m_RestrictToTerrain`  
Component used to clamp camera position to the terrain and optionally check collisions with scene objects.

- `private CameraInput m_CameraInput`  
Optional input helper used to read camera movement/rotation/zoom input and refresh input state.

- `private CameraUpdateSystem m_CameraUpdateSystem`  
Reference to the ECS-managed camera update system (obtained from the default World). The controller registers itself on that system so it can receive UpdateCamera calls.

## Properties

- `public ICinemachineCamera virtualCamera { get; }`  
Returns the Cinemachine virtual camera used by this controller (m_VCam).

- `public float zoom { get; set; }`  
Gets/sets the camera anchor's Y position (height) — used as the camera's "zoom" value.

- `public Vector3 pivot { get; set; }`  
Gets/sets the anchor position. Alias for position control of the camera.

- `public Vector3 position { get; set; }`  
Alias for pivot (maps to m_Anchor.position).

- `public Vector3 rotation { get; set; }`  
Gets/sets the anchor rotation as Euler angles (wraps m_Anchor.rotation).

- `public bool controllerEnabled { get; set; }`  
Maps to the GameObject activity: getter returns isActiveAndEnabled; setter calls gameObject.SetActive(value). Used to enable/disable the controller.

- `public bool collisionsEnabled { get; set; }`  
Controls whether object collisions are enabled on the CinemachineRestrictToTerrain component.

- `public ref LensSettings lens { get; }`  
Provides a reference to the virtual camera's LensSettings (m_VCam.m_Lens) so callers can read/modify lens parameters directly.

- `public Action eventCameraMove { get; set; }`  
Event invoked when input indicates the camera has been moved. External systems can subscribe to react to user-driven camera movement.

- `public float fov { get; set; }`  
Shortcut to get/set FieldOfView on the virtual camera lens.

- `public float dutch { get; set; }`  
Shortcut to get/set the Dutch (roll) angle on the virtual camera lens.

- `public bool inputEnabled { get; set; }`  
Whether the controller processes camera input. Defaults to true.

## Constructors

- `public CinematicCameraController()`  
No explicit user-defined constructor is present; the MonoBehaviour default constructor is used. Initialization of components and the runtime anchor happens in Awake after the GameManager signals ready.

## Methods

- `private async void Awake()`  
Initializes the controller once GameManager is ready. Creates the runtime anchor GameObject, binds the Cinemachine virtual camera to follow it, fetches required components (CinemachineRestrictToTerrain, CameraInput), initializes CameraInput if present, registers the controller on the CameraUpdateSystem (World.DefaultGameObjectInjectionWorld), and sets the controller GameObject inactive by default.

- `public void TryMatchPosition(IGameCameraController other)`  
Copies position and rotation from another IGameCameraController to this controller's anchor. Useful when switching cameras to maintain viewpoint continuity.

- `public void UpdateCamera()`  
Called (typically by CameraUpdateSystem) to refresh input and update the camera. If CameraInput exists it is refreshed; if any input was detected eventCameraMove is invoked. If inputEnabled is true, UpdateController is called to actually move the anchor. Also forwards the current transform to the AudioManager to update the audio listener.

- `private void UpdateController(CameraInput input)`  
Core movement logic. Steps:
  - Refresh terrain restriction state.
  - Compute a height-based t factor to lerp between min and max move/zoom speeds (higher altitude -> faster).
  - Read input move/rotate/zoom values and scale them by the lerped speeds.
  - Apply rotation to move vector so movement is in camera-local directions.
  - Clamp resulting position to terrain and cap maximum height above terrain.
  - Compute new quaternion (pitch/yaw) with clamped pitch and applied yaw/roll from input.
  - If object collisions are enabled, query the restrict-to-terrain component for collision and use the collision-corrected position if necessary; otherwise set anchor to computed position.
  - Apply anchor rotation.

- `private void OnDestroy()`  
Cleans up the runtime anchor GameObject and unregisters the controller from the CameraUpdateSystem.

```csharp
private async void Awake()
{
	if (await GameManager.instance.WaitForReadyState())
	{
		m_Anchor = new GameObject("CinematicCameraControllerAnchor").transform;
		m_VCam = GetComponent<CinemachineVirtualCamera>();
		m_VCam.Follow = m_Anchor;
		m_RestrictToTerrain = GetComponent<CinemachineRestrictToTerrain>();
		m_CameraInput = GetComponent<CameraInput>();
		if (m_CameraInput != null)
		{
			m_CameraInput.Initialize();
		}
		m_CameraUpdateSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_CameraUpdateSystem.cinematicCameraController = this;
		base.gameObject.SetActive(value: false);
	}
}
```

Notes / Integration tips:
- This controller assumes a CinemachineVirtualCamera and a CinemachineRestrictToTerrain component are present on the same GameObject.
- The camera movement speeds scale with altitude: close to terrain the controller uses m_MinMoveSpeed / m_MinZoomSpeed, and approaches m_Max* values as altitude increases (controlled by m_MaxMovementSpeedHeight).
- To enable/disable user control without destroying the camera, toggle controllerEnabled or set inputEnabled = false.
- Subscribing to eventCameraMove allows external UI/logic to hide or show cursor/UI when the user starts moving the camera.
- When switching from another camera, call TryMatchPosition to avoid abrupt jumps.
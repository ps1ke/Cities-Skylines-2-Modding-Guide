# Game.CameraController

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** class CameraController

**Base:** UnityEngine.MonoBehaviour, IGameCameraController

**Summary:** CameraController manages the in-game gameplay camera for Cities: Skylines 2. It reads player input (pan/rotate/zoom and edge-scrolling), computes camera transforms (pivot, angle, zoom), interacts with terrain and water height data, performs collision checking via the CameraCollisionSystem, and updates audio listener position. It also supports a special map-tile tool view with smooth transitions and exposes helpers to match or find the active gameplay camera for modding code to interact with. Intended for single main gameplay camera usage; many internal fields reference other game systems (InputManager, CameraUpdateSystem, CameraCollisionSystem, TerrainSystem, WaterSystem, AudioManager, MapTilesUISystem, Cinemachine).

---

## Fields

- `private float3 m_Pivot`  
Current pivot point (world-space) that the camera orbits around. Used as the main focal point for movement/zoom calculations.

- `private float2 m_Angle`  
Euler angles stored as float2 (x = yaw, y = pitch) used to compute camera orientation.

- `private float m_Zoom`  
Current zoom distance from pivot. Clamped against zoomRange and used to compute camera offset.

- `private Bounds1 m_ZoomRange = new Bounds1(10f, 10000f)`  
Allowed zoom range for gameplay camera. Switched to m_MapTileToolZoomRange when map tile view is active.

- `private Bounds1 m_MapTileToolZoomRange = new Bounds1(10f, 20000f)`  
Zoom limits when the map tile tool view is enabled.

- `private bool m_MapTileToolViewEnabled`  
Internal flag used to control map-tile tool view behaviour (set via MapTilesUISystem.mapTileViewActive externally).

- `private float m_MapTileToolFOV`  
Field of view used when transitioning to the map tile tool view.

- `private float m_MapTileToolFarclip`  
Far clip plane to use while the map tile tool view is active.

- `private float3 m_MapTileToolPivot`  
Target pivot for the map tile tool view.

- `private float2 m_MapTileToolAngle`  
Target angle for the map tile tool view.

- `private float m_MapTileToolZoom`  
Target zoom for the map tile tool view.

- `private float m_MapTileToolTransitionTime`  
Duration for the smooth transition between game view and map tile tool view.

- `private float m_MoveSmoothing = 1E-06f`  
Smoothing factor used when lerping pivot's Y toward terrain/water height.

- `private float m_CollisionSmoothing = 0.001f`  
Smoothing parameter passed into the CameraCollisionSystem for collision resolution.

- `private ProxyActionMap m_CameraMap`  
Input action map for camera controls (retrieved from InputManager).

- `private ProxyAction m_MoveAction`  
Input action used for camera panning.

- `private ProxyAction m_MoveFastAction`  
Input action for fast panning (e.g., modifier key held).

- `private ProxyAction m_RotateAction`  
Input action for camera rotation.

- `private ProxyAction m_ZoomAction`  
Input action for camera zoom.

- `private CinemachineVirtualCamera m_VCam`  
Reference to the Cinemachine virtual camera component attached to the same GameObject. Used to modify lens parameters (FOV, FarClip).

- `private float m_InitialFarClip`  
Stored initial far clip plane of the Cinemachine lens for transitions back from map view.

- `private float m_InitialFov`  
Stored initial field of view of the Cinemachine lens.

- `private float m_LastGameViewZoom`  
Used when toggling map-tile view: stores the previous game zoom to restore on exit.

- `private float2 m_LastGameViewAngle`  
Stores previous game view angle to restore after map-tile view.

- `private float3 m_LastGameViewPivot`  
Stores previous pivot to restore after map-tile view.

- `private float m_LastMapViewZoom`  
Stores map-view zoom when transitioning back to game view.

- `private float2 m_LastMapViewAngle`  
Stores map-view angle for the transition back.

- `private float3 m_LastMapViewPivot`  
Stores map-view pivot for the transition back.

- `private float m_MapViewTimer`  
Timer used to interpolate between game view and map-tile tool view.

- `private AudioManager m_AudioManager`  
Cached reference to audio manager (AudioManager.instance is used elsewhere). Present if needed for advanced audio updates.

- `private CameraUpdateSystem m_CameraSystem`  
Reference to ECS CameraUpdateSystem used to read activeCamera settings and to register this controller (gamePlayController).

- `private CameraCollisionSystem m_CollisionSystem`  
Reference to ECS CameraCollisionSystem used to test and resolve camera collisions against world geometry.

## Properties

- `public IEnumerable<ProxyAction> inputActions`  
Enumerates non-null input actions (Move, Move Fast, Rotate, Zoom). Useful for systems that need to register or enable/disable these actions.

- `public Action<bool> EventCameraMovingChanged { get; set; }`  
Event invoked when camera movement state changes (true = camera started moving, false = stopped). Mods can subscribe to react to camera motion.

- `public bool moving { get; private set; }`  
Indicates whether the controller currently considers the camera to be moving. Updated each UpdateCamera call.

- `public ref LensSettings lens => ref m_VCam.m_Lens`  
Direct reference to Cinemachine lens settings. Allows read/write access to lens properties (FieldOfView, FarClipPlane, etc.). Use with caution since it mutates Cinemachine state.

- `public ICinemachineCamera virtualCamera => m_VCam`  
Exposes the underlying Cinemachine virtual camera as an ICinemachineCamera.

- `public Vector3 rotation`  
Gets/sets camera rotation as a Unity Vector3 (x = pitch, y = yaw, z = 0). Setting updates internal m_Angle appropriately.

- `public TerrainSystem terrainSystem`  
Gets the ECS-managed TerrainSystem from the default World. Nullable; returns null if world not available. Used for sampling terrain heights and bounds.

- `public WaterSystem waterSystem`  
Gets the ECS-managed WaterSystem from the default World. Nullable; used to sample water surface heights.

- `public Vector3 pivot`  
Gets/sets camera pivot (converts internal float3 to Unity Vector3).

- `public Vector3 position`  
Getter returns transform.position. Setter is intentionally empty to prevent direct assignment through this property.

- `public float2 angle`  
Gets/sets raw internal angle (float2).

- `public float zoom`  
Gets/sets internal zoom distance.

- `public bool controllerEnabled`  
Gets if the controller GameObject is active and enabled; setting toggles the GameObject's active state.

- `public bool inputEnabled { get; set; } = true`  
Flag to enable/disable input handling at this controller level.

- `public Bounds1 zoomRange`  
Returns m_MapTileToolZoomRange if MapTilesUISystem.mapTileViewActive is true, otherwise returns m_ZoomRange. Used for clamping zoom and collision logic.

- `public float3 cameraPosition { get; private set; }`  
Computed camera local position used for transforms and collision checks.

- `public float velocity { get; private set; }`  
Approximate squared velocity (computed from position delta and Time.deltaTime). Useful for detecting movement speed.

- `public bool edgeScrolling { get; set; }`  
Toggle for edge-of-screen scrolling when using keyboard + mouse control scheme.

- `public float edgeScrollingSensitivity { get; set; }`  
Sensitivity multiplier for edge scrolling; loaded from GameplaySettings on Awake.

- `public float clipDistance { get; set; }`  
Public clip distance value (initialized to float.MaxValue in Awake). Not directly tied to Cinemachine lens; used by collision logic.

## Constructors

- `public CameraController()`  
Default MonoBehaviour constructor (implicit). Typical instantiation occurs via a GameObject in the scene tagged "GameplayCamera". Initialization logic is performed in Awake rather than constructor.

## Methods

- `public void TryMatchPosition(IGameCameraController other)`  
Attempts to match pivot/angle/zoom to another IGameCameraController instance. Computes a zoom value based on other camera position/rotation and terrain height, then sets pivot and rotation to match. Useful for syncing two camera controllers (e.g., when switching camera targets).

- `private async void Awake()`  
Initializes the controller: waits for GameManager ready state, reads edge-scrolling settings, caches Cinemachine camera and lens defaults, initializes input action references from InputManager, and registers this controller with the CameraUpdateSystem and CameraCollisionSystem. This method runs asynchronously and guards against usage until initialization completes.

- `public void UpdateCamera()`  
Main per-frame update called by CameraUpdateSystem. Reads input (move/rotate/zoom), applies edge-scrolling, clamps zoom, computes orientation and offsets, samples terrain/water heights to adjust pivot Y and camera Y and to clamp pivot inside terrain bounds, performs camera collision checks via CameraCollisionSystem (using active camera near/fov info from CameraUpdateSystem), updates transform, velocity, moving state, and audio listener. Also handles map tile tool view via HandleMapViewCamera early-out.

- `private float3 GetCameraPos(float3 cameraOffset)`  
Helper that returns pivot + offset, and adds a small Y offset based on zoomRange.min. Used consistently to compute the camera world position from pivot + direction * zoom.

- `private bool HandleMapViewCamera()`  
Handles smooth transition between game view and map tile tool view when MapTilesUISystem.mapTileViewActive changes. Interpolates pivot, angle (using LerpAngle), zoom and Cinemachine lens FOV/FarClip. Also samples terrain/water heights and clamps camera height similarly to UpdateCamera. Returns true when it handled the frame (so UpdateCamera should early-return).

- `public static float2 LerpAngle(float2 from, float2 to, float t)`  
Linearly interpolates between two angle pairs while properly taking the shortest path around the yaw wrap (handles 360-degree wrap-around). Pitch is interpolated linearly.

- `private bool TryGetTerrainHeight(Vector3 pos, out float terrainHeight)`  
Attempts to sample terrain or water height at pos using TerrainSystem and WaterSystem. Returns false and terrainHeight=0 if data unavailable. Completes any water deps before sampling.

- `public static bool TryGet(out CameraController cameraController)`  
Static helper that finds the GameObject tagged "GameplayCamera" and returns its CameraController component if present. Common pattern for mods to obtain the active camera controller.

---

## Usage notes and modding tips (YOUR_INFO)

- Typical access: use CameraController.TryGet(out var cam) to retrieve the active gameplay camera in your mod. Once obtained you can read or set pivot, angle, zoom, rotation and subscribe to EventCameraMovingChanged.
- Prefer using exposed properties (pivot, angle, zoom, rotation) and TryMatchPosition rather than directly manipulating transform to keep camera logic consistent with collision, terrain sampling, and Cinemachine lens.
- The controller relies on ECS systems (TerrainSystem, WaterSystem, CameraCollisionSystem, CameraUpdateSystem). When writing code that interacts with these systems, ensure the default World exists (World.DefaultGameObjectInjectionWorld) and that system features are initialized (this controller sets m_CameraSystem.gamePlayController = this on Awake).
- Input is read via InputManager action maps. Modifying input behavior should be done through the InputManager / ProxyAction system rather than altering this class directly.
- Map tile tool view: MapTilesUISystem.mapTileViewActive controls switching; m_MapTileToolTransitionTime is used for smooth interpolation. Cinemachine lens FOV and FarClipPlane are interpolated during the transition. If your mod changes FOV/FarClip, be aware of these transitions.
- Camera collision: CameraCollisionSystem.CheckCollisions is used to adjust cameraPos when geometry intersects. If you need custom collision behavior, consider hooking or extending CameraCollisionSystem rather than the controller.
- Performance: UpdateCamera performs terrain/water sampling and may call ECS system data methods that create dependencies. Avoid calling UpdateCamera yourself every frame; let CameraUpdateSystem drive updates. When sampling terrain/water directly in your mod, mimic how this controller completes dependencies (e.g., call deps.Complete() where appropriate).
- Thread-safety: All Unity API calls (transform, GameObject, Cinemachine) must be done on the main thread. This controller runs on the main thread via MonoBehaviour.Update loop orchestrated by CameraUpdateSystem.
- Edge scrolling: Edge-scrolling is enabled/disabled based on SharedSettings.gameplay.edgeScrolling and is only applied for the keyboard+mouse control scheme with mouse on screen. You can toggle edgeScrolling and edgeScrollingSensitivity at runtime.
- Saving/restoring camera: To persist camera state, store pivot, angle, and zoom. To smoothly apply stored state, call TryMatchPosition on a camera that has the stored position/rotation, or lerp the properties over time and let UpdateCamera resolve terrain and collisions.
- Compatibility: Many mods may want to modify Cinemachine lens values (FOV/far clip). Changing lens directly via cam.lens will be respected, but note the controller overwrites lens values during map view transitions. If you change lens values, consider re-applying after map view changes or hooking into MapTilesUISystem transitions.

```csharp
private async void Awake()
{
	if (!(await GameManager.instance.WaitForReadyState()))
	{
		return;
	}
	if (!Application.isEditor)
	{
		edgeScrolling = true;
		GameplaySettings gameplaySettings = SharedSettings.instance?.gameplay;
		if (gameplaySettings != null)
		{
			edgeScrolling = gameplaySettings.edgeScrolling;
			edgeScrollingSensitivity = gameplaySettings.edgeScrollingSensitivity;
		}
	}
	m_VCam = GetComponent<CinemachineVirtualCamera>();
	m_InitialFarClip = m_VCam.m_Lens.FarClipPlane;
	m_InitialFov = m_VCam.m_Lens.FieldOfView;
	clipDistance = float.MaxValue;
	m_CameraMap = InputManager.instance.FindActionMap("Camera");
	m_MoveAction = m_CameraMap.FindAction("Move");
	m_MoveFastAction = m_CameraMap.FindAction("Move Fast");
	m_RotateAction = m_CameraMap.FindAction("Rotate");
	m_ZoomAction = m_CameraMap.FindAction("Zoom");
	m_CameraSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraUpdateSystem>();
	m_CameraSystem.gamePlayController = this;
	m_CollisionSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraCollisionSystem>();
}
```

If you want, I can generate short example snippets showing:
- how to fetch the CameraController from a mod and read/write pivot/angle/zoom safely;
- how to subscribe to EventCameraMovingChanged;
- or how to force a smooth camera transition to a target position using TryMatchPosition. Which would you prefer?
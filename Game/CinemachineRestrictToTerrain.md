# Game.CinemachineRestrictToTerrain

**Assembly:** Game  
**Namespace:** Game

**Type:** class

**Base:** Cinemachine.CinemachineExtension

**Summary:** A Cinemachine extension used to keep the virtual camera above the terrain, optionally clamped to the map bounds, and optionally using the game's camera collision system to avoid intersecting scene geometry (buildings, props, terrain features). It integrates with the game's ECS systems (CameraCollisionSystem, CameraUpdateSystem, TerrainSystem and WaterSystem) to sample heights and perform collision checks. Typical use is to attach this component to a Cinemachine virtual camera to prevent the camera from going below the terrain or inside world geometry.
---

## Fields

- `public float m_MapSurfacePadding = 1f`  
  Vertical padding added above the sampled terrain/water surface so the camera remains slightly above the ground.

- `public bool m_RestrictToMapArea = true`  
  If true, camera position will be clamped to the map bounds (or to editor camera bounds when in editor mode).

- `private CameraCollisionSystem m_CollisionSystem`  
  Reference to the game's CameraCollisionSystem (Entity System) used to perform camera-object collision checks. Obtained from World.DefaultGameObjectInjectionWorld in Start().

- `private CameraUpdateSystem m_CameraSystem`  
  Reference to CameraUpdateSystem to access the active Camera (for near clip plane, FOV, aspect, etc.). Obtained in Start().

- `private TerrainSystem m_TerrainSystem`  
  Reference to the game's TerrainSystem used to query terrain height data. Obtained in Start().

- `private WaterSystem m_WaterSystem`  
  Reference to the game's WaterSystem to sample water surface heights when loaded. Obtained in Start().

- `public bool enableObjectCollisions { get; set; } = true`  
  If true, collision checks with scene geometry are performed to push the camera out of intersecting geometry.

- `public Vector3 previousPosition { get; set; }`  
  Stores the previous camera transform position and is used as the lastPosition parameter for collision checks. Call Refresh() to update this value (for example after instantaneous camera jumps).

## Properties

- `public Unity.Jobs.JobHandle producerHandle { get; private set }`  
  (Note: This class does not actually declare a producerHandle property in the provided source. If present in other classes it would represent a job handle used for scheduling/dep handling. In this class the relevant job handles are retrieved from subsystems such as WaterSystem when sampling surface data.)

## Constructors

- `public CinemachineRestrictToTerrain()`  
  No explicit constructor is defined in source; the MonoBehaviour default constructor is used. Initialization of the ECS system references is performed in Start().

## Methods

- `protected void Start()`  
  Initializes references to required Entity systems:
  - m_CollisionSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraCollisionSystem>()
  - m_CameraSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraUpdateSystem>()
  - m_TerrainSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<TerrainSystem>()
  - m_WaterSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<WaterSystem>()

  These systems must be present in the game's DefaultGameObjectInjectionWorld for collision and height sampling to work.

- `public void Refresh()`  
  Updates previousPosition to the current transform.position. Call this when the camera is moved instantly (teleport, snap) so collision checks have a correct lastPosition reference.

- `protected override void PostPipelineStageCallback(CinemachineVirtualCameraBase vcam, CinemachineCore.Stage stage, ref CameraState state, float deltaTime)`  
  Cinemachine hook executed during the Body stage. This implementation:
  - Clamps the raw camera position to terrain and optionally to map bounds via ClampToTerrain.
  - If enableObjectCollisions is true, calls CheckForCollision to adjust position to avoid geometry intersections.
  - Assigns the adjusted position back to state.RawPosition.

- `public bool CheckForCollision(Vector3 currentPosition, Vector3 lastPosition, Quaternion rotation, out Vector3 position)`  
  Uses CameraCollisionSystem together with CameraUpdateSystem.activeCamera to perform collision checks:
  - Converts inputs to float3 and computes near clip plane and horizontal FOV from the active Camera.
  - Calls m_CollisionSystem.CheckCollisions(...) with a configured set of parameters (max distances, near clip adjustments, small epsilon, and field of view).
  - Outputs the potentially adjusted camera position and returns true if the collision system was available and used. Returns false and Vector3.zero if required systems are missing.

- `public Vector3 ClampToTerrain(Vector3 position, bool restrictToMapArea, out float terrainHeight)`  
  Clamps the provided position to terrain/water surface and optionally to map bounds:
  - Gets TerrainHeightData from m_TerrainSystem; if not created, returns the original position and terrainHeight = 0.
  - If restrictToMapArea is true, clamps position to either editor camera bounds or full terrain bounds. The bounds' max Y is expanded to ensure adequate vertical range.
  - If WaterSystem is loaded, retrieves WaterSurfaceData and samples height via WaterUtils.SampleHeight; otherwise uses TerrainUtils.SampleHeight.
  - Applies m_MapSurfacePadding to sampled height and ensures position.y is at least that height.
  - Returns adjusted position and outputs terrainHeight.

Notes and usage tips for modders:
- Attach to a Cinemachine Virtual Camera to enforce being above terrain and avoid clipping through scene geometry.
- Adjust m_MapSurfacePadding if the camera should be further above the surface.
- Toggle m_RestrictToMapArea to allow free movement outside the playable terrain bounds (useful in editor camera scenarios).
- If you teleport the camera, call Refresh() so previousPosition is not stale (helps collision smoothing).
- The class depends on the presence of the game's ECS systems (CameraCollisionSystem, CameraUpdateSystem, TerrainSystem, WaterSystem) — ensure these systems are available in the World before relying on them.
- CheckForCollision returns true only when both m_CollisionSystem and m_CameraSystem are available and there is an active Camera.

```csharp
protected override void PostPipelineStageCallback(CinemachineVirtualCameraBase vcam, CinemachineCore.Stage stage, ref CameraState state, float deltaTime)
{
	if (stage == CinemachineCore.Stage.Body)
	{
		float terrainHeight;
		Vector3 rawPosition = ClampToTerrain(state.RawPosition, m_RestrictToMapArea, out terrainHeight);
		state.RawPosition = rawPosition;
		if (enableObjectCollisions && CheckForCollision(state.RawPosition, previousPosition, state.RawOrientation, out var position))
		{
			state.RawPosition = position;
		}
	}
}
```

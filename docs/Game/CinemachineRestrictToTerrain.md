# Game.CinemachineRestrictToTerrain

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Cinemachine.CinemachineExtension`  

## Fields

- `public System.Single m_MapSurfacePadding`  
- `public System.Boolean m_RestrictToMapArea`  
- `private System.Boolean <enableObjectCollisions>k__BackingField`  
- `private UnityEngine.Vector3 <previousPosition>k__BackingField`  
- `private Game.Rendering.CameraCollisionSystem m_CollisionSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  

## Properties

- `public System.Boolean enableObjectCollisions { get; set }`  
- `public UnityEngine.Vector3 previousPosition { get; set }`  

## Constructors

- `public CinemachineRestrictToTerrain()`  

## Methods

- `public CheckForCollision(UnityEngine.Vector3 currentPosition, UnityEngine.Vector3 lastPosition, UnityEngine.Quaternion rotation, UnityEngine.Vector3& position) : System.Boolean`  
- `public ClampToTerrain(UnityEngine.Vector3 position, System.Boolean restrictToMapArea, System.Single& terrainHeight) : UnityEngine.Vector3`  
- `protected virtual PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime) : System.Void`  
- `public Refresh() : System.Void`  
- `protected Start() : System.Void`  


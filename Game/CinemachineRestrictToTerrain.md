# Game.CinemachineRestrictToTerrain

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Cinemachine.CinemachineExtension`  

## Code

```csharp
public class CinemachineRestrictToTerrain : Cinemachine.CinemachineExtension
{
    public System.Single m_MapSurfacePadding;
    public System.Boolean m_RestrictToMapArea;
    private System.Boolean <enableObjectCollisions>k__BackingField;
    private UnityEngine.Vector3 <previousPosition>k__BackingField;
    private Game.Rendering.CameraCollisionSystem m_CollisionSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;

    public System.Boolean enableObjectCollisions { get; set; }
    public UnityEngine.Vector3 previousPosition { get; set; }

    public CinemachineRestrictToTerrain();

    public System.Boolean CheckForCollision(UnityEngine.Vector3 currentPosition, UnityEngine.Vector3 lastPosition, UnityEngine.Quaternion rotation, UnityEngine.Vector3& position);
    public UnityEngine.Vector3 ClampToTerrain(UnityEngine.Vector3 position, System.Boolean restrictToMapArea, System.Single& terrainHeight);
    protected virtual System.Void PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime);
    public System.Void Refresh();
    protected System.Void Start();
}
```


## Fields

- `public System.Single m_MapSurfacePadding`  

```csharp
public System.Single m_MapSurfacePadding;
```

- `public System.Boolean m_RestrictToMapArea`  

```csharp
public System.Boolean m_RestrictToMapArea;
```

- `private System.Boolean <enableObjectCollisions>k__BackingField`  

```csharp
private System.Boolean <enableObjectCollisions>k__BackingField;
```

- `private UnityEngine.Vector3 <previousPosition>k__BackingField`  

```csharp
private UnityEngine.Vector3 <previousPosition>k__BackingField;
```

- `private Game.Rendering.CameraCollisionSystem m_CollisionSystem`  

```csharp
private Game.Rendering.CameraCollisionSystem m_CollisionSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```


## Properties

- `public System.Boolean enableObjectCollisions { get; set }`  

```csharp
public System.Boolean enableObjectCollisions { get; set; }
```

- `public UnityEngine.Vector3 previousPosition { get; set }`  

```csharp
public UnityEngine.Vector3 previousPosition { get; set; }
```


## Constructors

- `public CinemachineRestrictToTerrain()`  

```csharp
public CinemachineRestrictToTerrain();
```


## Methods

- `public CheckForCollision(UnityEngine.Vector3 currentPosition, UnityEngine.Vector3 lastPosition, UnityEngine.Quaternion rotation, UnityEngine.Vector3& position) : System.Boolean`  

```csharp
public System.Boolean CheckForCollision(UnityEngine.Vector3 currentPosition, UnityEngine.Vector3 lastPosition, UnityEngine.Quaternion rotation, UnityEngine.Vector3& position);
```

- `public ClampToTerrain(UnityEngine.Vector3 position, System.Boolean restrictToMapArea, System.Single& terrainHeight) : UnityEngine.Vector3`  

```csharp
public UnityEngine.Vector3 ClampToTerrain(UnityEngine.Vector3 position, System.Boolean restrictToMapArea, System.Single& terrainHeight);
```

- `protected virtual PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime) : System.Void`  

```csharp
protected virtual System.Void PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime);
```

- `public Refresh() : System.Void`  

```csharp
public System.Void Refresh();
```

- `protected Start() : System.Void`  

```csharp
protected System.Void Start();
```



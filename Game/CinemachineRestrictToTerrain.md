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
public bool CheckForCollision(Vector3 currentPosition, Vector3 lastPosition, Quaternion rotation, out Vector3 position)
	{
		if (m_CollisionSystem != null && m_CameraSystem != null && m_CameraSystem.activeCamera != null)
		{
			float3 position2 = currentPosition;
			float3 @float = lastPosition;
			float nearClipPlane = m_CameraSystem.activeCamera.nearClipPlane;
			float2 fieldOfView = default(float2);
			fieldOfView.y = m_CameraSystem.activeCamera.fieldOfView;
			fieldOfView.x = Camera.VerticalToHorizontalFieldOfView(fieldOfView.y, m_CameraSystem.activeCamera.aspect);
			m_CollisionSystem.CheckCollisions(ref position2, @float, rotation, 200f, 200f, nearClipPlane * 2f + 1f, nearClipPlane, 0.001f, fieldOfView);
			position = position2;
			return true;
		}
		position = Vector3.zero;
		return false;
	}
```

- `public ClampToTerrain(UnityEngine.Vector3 position, System.Boolean restrictToMapArea, System.Single& terrainHeight) : UnityEngine.Vector3`  

```csharp
public Vector3 ClampToTerrain(Vector3 position, bool restrictToMapArea, out float terrainHeight)
	{
		terrainHeight = 0f;
		TerrainHeightData data = m_TerrainSystem.GetHeightData();
		if (data.isCreated)
		{
			if (restrictToMapArea)
			{
				Bounds3 bounds = (GameManager.instance.gameMode.IsEditor() ? TerrainUtils.GetEditorCameraBounds(m_TerrainSystem, ref data) : TerrainUtils.GetBounds(ref data));
				float3 max = bounds.max;
				max.y = bounds.min.y + math.max(bounds.max.y - bounds.min.y, 4096f);
				bounds.max = max;
				position = MathUtils.Clamp(position, bounds);
			}
			if (m_WaterSystem.Loaded)
			{
				JobHandle deps;
				WaterSurfaceData data2 = m_WaterSystem.GetSurfaceData(out deps);
				deps.Complete();
				if (data2.isCreated)
				{
					terrainHeight = WaterUtils.SampleHeight(ref data2, ref data, position);
				}
			}
			else
			{
				terrainHeight = TerrainUtils.SampleHeight(ref data, position);
			}
			position.y = Mathf.Max(position.y, terrainHeight += m_MapSurfacePadding);
		}
		return position;
	}
```

- `protected virtual PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime) : System.Void`  

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

- `public Refresh() : System.Void`  

```csharp
public void Refresh()
	{
		previousPosition = base.transform.position;
	}
```

- `protected Start() : System.Void`  

```csharp
protected void Start()
	{
		m_CollisionSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraCollisionSystem>();
		m_CameraSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_TerrainSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<WaterSystem>();
	}
```



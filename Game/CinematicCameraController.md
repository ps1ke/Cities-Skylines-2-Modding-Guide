# Game.CinematicCameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Code

```csharp
public class CinematicCameraController : UnityEngine.MonoBehaviour, Game.Rendering.IGameCameraController
{
    private System.Single m_MinMoveSpeed;
    private System.Single m_MaxMoveSpeed;
    private System.Single m_MinZoomSpeed;
    private System.Single m_MaxZoomSpeed;
    private System.Single m_RotateSpeed;
    private System.Single m_MaxHeight;
    private System.Single m_MaxMovementSpeedHeight;
    private UnityEngine.Transform m_Anchor;
    private Cinemachine.CinemachineVirtualCamera m_VCam;
    private Game.CinemachineRestrictToTerrain m_RestrictToTerrain;
    private Game.CameraInput m_CameraInput;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private System.Action <eventCameraMove>k__BackingField;
    private System.Boolean <inputEnabled>k__BackingField;

    public Cinemachine.ICinemachineCamera virtualCamera { get; }
    public System.Single zoom { get; set; }
    public UnityEngine.Vector3 pivot { get; set; }
    public UnityEngine.Vector3 position { get; set; }
    public UnityEngine.Vector3 rotation { get; set; }
    public System.Boolean controllerEnabled { get; set; }
    public System.Boolean collisionsEnabled { get; set; }
    public Cinemachine.LensSettings& lens { get; }
    public System.Action eventCameraMove { get; set; }
    public System.Single fov { get; set; }
    public System.Single dutch { get; set; }
    public System.Boolean inputEnabled { get; set; }

    public CinematicCameraController();

    private System.Void Awake();
    private System.Void OnDestroy();
    public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
    public System.Void UpdateCamera();
    private System.Void UpdateController(Game.CameraInput input);
}
```


## Fields

- `private System.Single m_MinMoveSpeed`  

```csharp
private System.Single m_MinMoveSpeed;
```

- `private System.Single m_MaxMoveSpeed`  

```csharp
private System.Single m_MaxMoveSpeed;
```

- `private System.Single m_MinZoomSpeed`  

```csharp
private System.Single m_MinZoomSpeed;
```

- `private System.Single m_MaxZoomSpeed`  

```csharp
private System.Single m_MaxZoomSpeed;
```

- `private System.Single m_RotateSpeed`  

```csharp
private System.Single m_RotateSpeed;
```

- `private System.Single m_MaxHeight`  

```csharp
private System.Single m_MaxHeight;
```

- `private System.Single m_MaxMovementSpeedHeight`  

```csharp
private System.Single m_MaxMovementSpeedHeight;
```

- `private UnityEngine.Transform m_Anchor`  

```csharp
private UnityEngine.Transform m_Anchor;
```

- `private Cinemachine.CinemachineVirtualCamera m_VCam`  

```csharp
private Cinemachine.CinemachineVirtualCamera m_VCam;
```

- `private Game.CinemachineRestrictToTerrain m_RestrictToTerrain`  

```csharp
private Game.CinemachineRestrictToTerrain m_RestrictToTerrain;
```

- `private Game.CameraInput m_CameraInput`  

```csharp
private Game.CameraInput m_CameraInput;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private System.Action <eventCameraMove>k__BackingField`  

```csharp
private System.Action <eventCameraMove>k__BackingField;
```

- `private System.Boolean <inputEnabled>k__BackingField`  

```csharp
private System.Boolean <inputEnabled>k__BackingField;
```


## Properties

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  

```csharp
public Cinemachine.ICinemachineCamera virtualCamera { get; }
```

- `public System.Single zoom { get; set }`  

```csharp
public System.Single zoom { get; set; }
```

- `public UnityEngine.Vector3 pivot { get; set }`  

```csharp
public UnityEngine.Vector3 pivot { get; set; }
```

- `public UnityEngine.Vector3 position { get; set }`  

```csharp
public UnityEngine.Vector3 position { get; set; }
```

- `public UnityEngine.Vector3 rotation { get; set }`  

```csharp
public UnityEngine.Vector3 rotation { get; set; }
```

- `public System.Boolean controllerEnabled { get; set }`  

```csharp
public System.Boolean controllerEnabled { get; set; }
```

- `public System.Boolean collisionsEnabled { get; set }`  

```csharp
public System.Boolean collisionsEnabled { get; set; }
```

- `public Cinemachine.LensSettings& lens { get }`  

```csharp
public Cinemachine.LensSettings& lens { get; }
```

- `public System.Action eventCameraMove { get; set }`  

```csharp
public System.Action eventCameraMove { get; set; }
```

- `public System.Single fov { get; set }`  

```csharp
public System.Single fov { get; set; }
```

- `public System.Single dutch { get; set }`  

```csharp
public System.Single dutch { get; set; }
```

- `public System.Boolean inputEnabled { get; set }`  

```csharp
public System.Boolean inputEnabled { get; set; }
```


## Constructors

- `public CinematicCameraController()`  

```csharp
public CinematicCameraController();
```


## Methods

- `private Awake() : System.Void`  

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

- `private OnDestroy() : System.Void`  

```csharp
private void OnDestroy()
	{
		if (m_Anchor != null)
		{
			UnityEngine.Object.Destroy(m_Anchor.gameObject);
		}
		if (m_CameraUpdateSystem != null)
		{
			m_CameraUpdateSystem.cinematicCameraController = null;
		}
	}
```

- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  

```csharp
public void TryMatchPosition(IGameCameraController other)
	{
		position = other.position;
		rotation = other.rotation;
	}
```

- `public UpdateCamera() : System.Void`  

```csharp
public void UpdateCamera()
	{
		if (m_CameraInput != null)
		{
			m_CameraInput.Refresh();
			if (m_CameraInput.any)
			{
				eventCameraMove?.Invoke();
			}
			if (inputEnabled)
			{
				UpdateController(m_CameraInput);
			}
		}
		AudioManager.instance?.UpdateAudioListener(base.transform.position, base.transform.rotation);
	}
```

- `private UpdateController(Game.CameraInput input) : System.Void`  

```csharp
private void UpdateController(CameraInput input)
	{
		m_RestrictToTerrain.Refresh();
		Vector3 vector = m_Anchor.position;
		m_RestrictToTerrain.ClampToTerrain(vector, restrictToMapArea: true, out var terrainHeight);
		float t = Mathf.Min(vector.y - terrainHeight, m_MaxMovementSpeedHeight) / m_MaxMovementSpeedHeight;
		Vector2 move = input.move;
		move *= Mathf.Lerp(m_MinMoveSpeed, m_MaxMoveSpeed, t);
		Vector2 vector2 = input.rotate * m_RotateSpeed;
		float num = input.zoom * Mathf.Lerp(m_MinZoomSpeed, m_MaxZoomSpeed, t);
		Vector3 eulerAngles = m_Anchor.rotation.eulerAngles;
		vector += Quaternion.AngleAxis(eulerAngles.y, Vector3.up) * new Vector3(move.x, 0f - num, move.y);
		vector = m_RestrictToTerrain.ClampToTerrain(vector, restrictToMapArea: true, out var terrainHeight2);
		vector.y = Mathf.Min(vector.y, terrainHeight2 + m_MaxHeight);
		Quaternion quaternion = Quaternion.Euler(Mathf.Clamp((eulerAngles.x + 90f) % 360f - vector2.y, 0f, 180f) - 90f, eulerAngles.y + vector2.x, 0f);
		if (m_RestrictToTerrain.enableObjectCollisions && m_RestrictToTerrain.CheckForCollision(vector, m_RestrictToTerrain.previousPosition, quaternion, out var vector3))
		{
			m_Anchor.position = vector3;
		}
		else
		{
			m_Anchor.position = vector;
		}
		m_Anchor.rotation = quaternion;
	}
```


## Nested types

- `Game.CinematicCameraController+<Awake>d__48`  


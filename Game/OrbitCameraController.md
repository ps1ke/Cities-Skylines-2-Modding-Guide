# Game.OrbitCameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Code

```csharp
public class OrbitCameraController : UnityEngine.MonoBehaviour, Game.Rendering.IGameCameraController
{
    public Unity.Mathematics.float2 m_ZoomRange;
    public System.Single m_FollowSmoothing;
    private Unity.Entities.Entity m_Entity;
    private System.Single m_FollowTimer;
    private Game.OrbitCameraController+Mode <mode>k__BackingField;
    private Unity.Mathematics.float2 m_Rotation;
    private UnityEngine.GameObject m_Anchor;
    private Cinemachine.CinemachineVirtualCamera m_VCam;
    private Cinemachine.CinemachineOrbitalTransposer m_Transposer;
    private Game.CinemachineRestrictToTerrain m_Collider;
    private Game.CameraInput m_CameraInput;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private System.Boolean <inputEnabled>k__BackingField;
    private System.Single <zoom>k__BackingField;
    private System.Single <yOffset>k__BackingField;
    private System.Single <xOffset>k__BackingField;
    private System.Action <EventCameraMove>k__BackingField;
    private static readonly System.Single kPivotVerticalOffset;

    public Unity.Entities.Entity followedEntity { get; set; }
    public Game.OrbitCameraController+Mode mode { get; set; }
    public UnityEngine.Vector3 pivot { get; set; }
    public UnityEngine.Vector3 position { get; set; }
    public System.Boolean controllerEnabled { get; set; }
    public System.Boolean inputEnabled { get; set; }
    public UnityEngine.Vector3 rotation { get; set; }
    public System.Single zoom { get; set; }
    public System.Single yOffset { get; set; }
    public System.Single xOffset { get; set; }
    public Cinemachine.ICinemachineCamera virtualCamera { get; }
    public Cinemachine.LensSettings& lens { get; }
    public System.Boolean collisionsEnabled { get; set; }
    public System.Action EventCameraMove { get; set; }

    public OrbitCameraController();

    private System.Void Awake();
    private System.Void OnDestroy();
    private System.Void OnDisable();
    private System.Void OnEnable();
    private System.Void RefreshAudioFollow(System.Boolean active);
    private static System.Boolean TryGetPosition(Unity.Entities.Entity e, Unity.Entities.EntityManager entityManager, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Single& radius);
    public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
    public System.Void UpdateCamera();
}
```


## Fields

- `public Unity.Mathematics.float2 m_ZoomRange`  

```csharp
public Unity.Mathematics.float2 m_ZoomRange;
```

- `public System.Single m_FollowSmoothing`  

```csharp
public System.Single m_FollowSmoothing;
```

- `private Unity.Entities.Entity m_Entity`  

```csharp
private Unity.Entities.Entity m_Entity;
```

- `private System.Single m_FollowTimer`  

```csharp
private System.Single m_FollowTimer;
```

- `private Game.OrbitCameraController+Mode <mode>k__BackingField`  

```csharp
private Game.OrbitCameraController+Mode <mode>k__BackingField;
```

- `private Unity.Mathematics.float2 m_Rotation`  

```csharp
private Unity.Mathematics.float2 m_Rotation;
```

- `private UnityEngine.GameObject m_Anchor`  

```csharp
private UnityEngine.GameObject m_Anchor;
```

- `private Cinemachine.CinemachineVirtualCamera m_VCam`  

```csharp
private Cinemachine.CinemachineVirtualCamera m_VCam;
```

- `private Cinemachine.CinemachineOrbitalTransposer m_Transposer`  

```csharp
private Cinemachine.CinemachineOrbitalTransposer m_Transposer;
```

- `private Game.CinemachineRestrictToTerrain m_Collider`  

```csharp
private Game.CinemachineRestrictToTerrain m_Collider;
```

- `private Game.CameraInput m_CameraInput`  

```csharp
private Game.CameraInput m_CameraInput;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private System.Boolean <inputEnabled>k__BackingField`  

```csharp
private System.Boolean <inputEnabled>k__BackingField;
```

- `private System.Single <zoom>k__BackingField`  

```csharp
private System.Single <zoom>k__BackingField;
```

- `private System.Single <yOffset>k__BackingField`  

```csharp
private System.Single <yOffset>k__BackingField;
```

- `private System.Single <xOffset>k__BackingField`  

```csharp
private System.Single <xOffset>k__BackingField;
```

- `private System.Action <EventCameraMove>k__BackingField`  

```csharp
private System.Action <EventCameraMove>k__BackingField;
```

- `private static readonly System.Single kPivotVerticalOffset`  

```csharp
private static readonly System.Single kPivotVerticalOffset;
```


## Properties

- `public Unity.Entities.Entity followedEntity { get; set }`  

```csharp
public Unity.Entities.Entity followedEntity { get; set; }
```

- `public Game.OrbitCameraController+Mode mode { get; set }`  

```csharp
public Game.OrbitCameraController+Mode mode { get; set; }
```

- `public UnityEngine.Vector3 pivot { get; set }`  

```csharp
public UnityEngine.Vector3 pivot { get; set; }
```

- `public UnityEngine.Vector3 position { get; set }`  

```csharp
public UnityEngine.Vector3 position { get; set; }
```

- `public System.Boolean controllerEnabled { get; set }`  

```csharp
public System.Boolean controllerEnabled { get; set; }
```

- `public System.Boolean inputEnabled { get; set }`  

```csharp
public System.Boolean inputEnabled { get; set; }
```

- `public UnityEngine.Vector3 rotation { get; set }`  

```csharp
public UnityEngine.Vector3 rotation { get; set; }
```

- `public System.Single zoom { get; set }`  

```csharp
public System.Single zoom { get; set; }
```

- `public System.Single yOffset { get; set }`  

```csharp
public System.Single yOffset { get; set; }
```

- `public System.Single xOffset { get; set }`  

```csharp
public System.Single xOffset { get; set; }
```

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  

```csharp
public Cinemachine.ICinemachineCamera virtualCamera { get; }
```

- `public Cinemachine.LensSettings& lens { get }`  

```csharp
public Cinemachine.LensSettings& lens { get; }
```

- `public System.Boolean collisionsEnabled { get; set }`  

```csharp
public System.Boolean collisionsEnabled { get; set; }
```

- `public System.Action EventCameraMove { get; set }`  

```csharp
public System.Action EventCameraMove { get; set; }
```


## Constructors

- `public OrbitCameraController()`  

```csharp
public OrbitCameraController();
```


## Methods

- `private Awake() : System.Void`  

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

- `private OnDestroy() : System.Void`  

```csharp
private void OnDestroy()
	{
		if (m_Anchor != null)
		{
			UnityEngine.Object.Destroy(m_Anchor);
		}
		if (m_CameraUpdateSystem != null)
		{
			m_CameraUpdateSystem.cinematicCameraController = null;
		}
	}
```

- `private OnDisable() : System.Void`  

```csharp
private void OnDisable()
	{
		RefreshAudioFollow(active: false);
	}
```

- `private OnEnable() : System.Void`  

```csharp
private void OnEnable()
	{
		RefreshAudioFollow(active: true);
	}
```

- `private RefreshAudioFollow(System.Boolean active) : System.Void`  

```csharp
private void RefreshAudioFollow(bool active)
	{
		if (AudioManager.instance != null)
		{
			AudioManager.instance.followed = (active ? m_Entity : Entity.Null);
		}
	}
```

- `private static TryGetPosition(Unity.Entities.Entity e, Unity.Entities.EntityManager entityManager, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Single& radius) : System.Boolean`  

```csharp
private static bool TryGetPosition(Entity e, EntityManager entityManager, out float3 position, out quaternion rotation, out float radius)
	{
		int elementIndex = -1;
		if (e != Entity.Null && SelectedInfoUISystem.TryGetPosition(e, entityManager, ref elementIndex, out var _, out position, out var bounds, out rotation, reinterpolate: true))
		{
			position.y = MathUtils.Center(bounds.y);
			float3 @float = (bounds.max - bounds.min) / 2f;
			radius = Mathf.Min(@float.x, @float.y, @float.z);
			return true;
		}
		position = float3.zero;
		rotation = quaternion.identity;
		radius = 0f;
		return false;
	}
```

- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  

```csharp
public void TryMatchPosition(IGameCameraController other)
	{
		rotation = other.rotation;
		if (other is CinematicCameraController)
		{
			m_Collider.ClampToTerrain(other.position, restrictToMapArea: false, out var terrainHeight);
			float num = other.position.y - terrainHeight - kPivotVerticalOffset;
			zoom = Mathf.Clamp(num / Mathf.Sin(MathF.PI / 180f * Mathf.Abs(other.rotation.x)), m_ZoomRange.x, m_ZoomRange.y);
			pivot = new Vector3(other.position.x, num, other.position.z) + Quaternion.Euler(other.rotation) * new Vector3(0f, 0f, zoom);
		}
		else
		{
			zoom = Mathf.Clamp(other.zoom, m_ZoomRange.x, m_ZoomRange.y);
			pivot = other.pivot;
		}
	}
```

- `public UpdateCamera() : System.Void`  

```csharp
public void UpdateCamera()
	{
		m_Collider.Refresh();
		m_CameraInput.Refresh();
		if (inputEnabled && m_CameraInput != null)
		{
			Vector2 rotate = m_CameraInput.rotate;
			m_Rotation.x = (m_Rotation.x + rotate.x) % 360f;
			m_Rotation.y = Mathf.Clamp((m_Rotation.y + 90f) % 360f - rotate.y, 0f, 180f) - 90f;
			float num = m_CameraInput.zoom;
			zoom = Mathf.Clamp(math.pow(zoom, 1f + num), m_ZoomRange.x, m_ZoomRange.y);
			if (followedEntity == Entity.Null)
			{
				Vector2 move = m_CameraInput.move;
				Vector3 vector = m_Anchor.transform.position;
				vector = m_Collider.ClampToTerrain(vector, restrictToMapArea: true, out var _);
				Vector2 vector2 = move * zoom;
				Vector3 vector3 = vector + (Vector3)math.mul(quaternion.AxisAngle(new float3(0f, 1f, 0f), math.radians(m_Anchor.transform.rotation.eulerAngles.y)), new float3(vector2.x, 0f, vector2.y));
				vector3 = m_Collider.ClampToTerrain(vector3, restrictToMapArea: true, out var terrainHeight2);
				vector3.y = terrainHeight2 + kPivotVerticalOffset;
				m_Anchor.transform.position = vector3;
			}
			if (TryGetPosition(followedEntity, World.DefaultGameObjectInjectionWorld.EntityManager, out var @float, out var _, out var radius))
			{
				m_Anchor.transform.rotation = quaternion.Euler(math.radians(m_Rotation.y), math.radians(m_Rotation.x), 0f);
				float3 float2 = (float3)pivot - @float;
				m_FollowTimer += Time.deltaTime;
				float num2 = math.pow(m_FollowSmoothing, Time.deltaTime) * math.smoothstep(0.5f, 0f, m_FollowTimer);
				float2 *= num2;
				m_Anchor.transform.position = @float + float2 + math.mul(m_Anchor.transform.rotation, new float3(xOffset, yOffset, 0f));
			}
			else
			{
				m_Anchor.transform.rotation = quaternion.Euler(math.radians(m_Rotation.y), math.radians(m_Rotation.x), 0f);
			}
			m_Transposer.m_FollowOffset.z = 0f - zoom - radius;
		}
		Transform transform = base.transform;
		AudioManager.instance?.UpdateAudioListener(transform.position, transform.rotation);
		if (m_CameraInput.isMoving || MapTilesUISystem.mapTileViewActive)
		{
			EventCameraMove?.Invoke();
		}
	}
```


## Nested types

- `Game.OrbitCameraController+Mode`  
- `Game.OrbitCameraController+<Awake>d__59`  


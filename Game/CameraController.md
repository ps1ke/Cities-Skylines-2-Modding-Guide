# Game.CameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Code

```csharp
public class CameraController : UnityEngine.MonoBehaviour, Game.Rendering.IGameCameraController
{
    private Unity.Mathematics.float3 m_Pivot;
    private Unity.Mathematics.float2 m_Angle;
    private System.Single m_Zoom;
    private Colossal.Mathematics.Bounds1 m_ZoomRange;
    private Colossal.Mathematics.Bounds1 m_MapTileToolZoomRange;
    private System.Boolean m_MapTileToolViewEnabled;
    private System.Single m_MapTileToolFOV;
    private System.Single m_MapTileToolFarclip;
    private Unity.Mathematics.float3 m_MapTileToolPivot;
    private Unity.Mathematics.float2 m_MapTileToolAngle;
    private System.Single m_MapTileToolZoom;
    private System.Single m_MapTileToolTransitionTime;
    private System.Single m_MoveSmoothing;
    private System.Single m_CollisionSmoothing;
    private Game.Input.ProxyActionMap m_CameraMap;
    private Game.Input.ProxyAction m_MoveAction;
    private Game.Input.ProxyAction m_MoveFastAction;
    private Game.Input.ProxyAction m_RotateAction;
    private Game.Input.ProxyAction m_ZoomAction;
    private Cinemachine.CinemachineVirtualCamera m_VCam;
    private System.Single m_InitialFarClip;
    private System.Single m_InitialFov;
    private System.Single m_LastGameViewZoom;
    private Unity.Mathematics.float2 m_LastGameViewAngle;
    private Unity.Mathematics.float3 m_LastGameViewPivot;
    private System.Single m_LastMapViewZoom;
    private Unity.Mathematics.float2 m_LastMapViewAngle;
    private Unity.Mathematics.float3 m_LastMapViewPivot;
    private System.Action<System.Boolean> <EventCameraMovingChanged>k__BackingField;
    private System.Boolean <moving>k__BackingField;
    private System.Boolean <inputEnabled>k__BackingField;
    private Unity.Mathematics.float3 <cameraPosition>k__BackingField;
    private System.Single <velocity>k__BackingField;
    private System.Single m_MapViewTimer;
    private System.Boolean <edgeScrolling>k__BackingField;
    private System.Single <edgeScrollingSensitivity>k__BackingField;
    private System.Single <clipDistance>k__BackingField;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Rendering.CameraUpdateSystem m_CameraSystem;
    private Game.Rendering.CameraCollisionSystem m_CollisionSystem;

    public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> inputActions { get; }
    public System.Action<System.Boolean> EventCameraMovingChanged { get; set; }
    public System.Boolean moving { get; private set; }
    public Cinemachine.LensSettings& lens { get; }
    public Cinemachine.ICinemachineCamera virtualCamera { get; }
    public UnityEngine.Vector3 rotation { get; set; }
    public Game.Simulation.TerrainSystem terrainSystem { get; }
    public Game.Simulation.WaterSystem waterSystem { get; }
    public UnityEngine.Vector3 pivot { get; set; }
    public UnityEngine.Vector3 position { get; set; }
    public Unity.Mathematics.float2 angle { get; set; }
    public System.Single zoom { get; set; }
    public System.Boolean controllerEnabled { get; set; }
    public System.Boolean inputEnabled { get; set; }
    public Colossal.Mathematics.Bounds1 zoomRange { get; }
    public Unity.Mathematics.float3 cameraPosition { get; private set; }
    public System.Single velocity { get; private set; }
    public System.Boolean edgeScrolling { get; set; }
    public System.Single edgeScrollingSensitivity { get; set; }
    public System.Single clipDistance { get; set; }

    public CameraController();

    private System.Void Awake();
    private Unity.Mathematics.float3 GetCameraPos(Unity.Mathematics.float3 cameraOffset);
    private System.Boolean HandleMapViewCamera();
    public static Unity.Mathematics.float2 LerpAngle(Unity.Mathematics.float2 from, Unity.Mathematics.float2 to, System.Single t);
    public static System.Boolean TryGet(Game.CameraController& cameraController);
    private System.Boolean TryGetTerrainHeight(UnityEngine.Vector3 pos, System.Single& terrainHeight);
    public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
    public System.Void UpdateCamera();
}
```


## Fields

- `private Unity.Mathematics.float3 m_Pivot`  

```csharp
private Unity.Mathematics.float3 m_Pivot;
```

- `private Unity.Mathematics.float2 m_Angle`  

```csharp
private Unity.Mathematics.float2 m_Angle;
```

- `private System.Single m_Zoom`  

```csharp
private System.Single m_Zoom;
```

- `private Colossal.Mathematics.Bounds1 m_ZoomRange`  

```csharp
private Colossal.Mathematics.Bounds1 m_ZoomRange;
```

- `private Colossal.Mathematics.Bounds1 m_MapTileToolZoomRange`  

```csharp
private Colossal.Mathematics.Bounds1 m_MapTileToolZoomRange;
```

- `private System.Boolean m_MapTileToolViewEnabled`  

```csharp
private System.Boolean m_MapTileToolViewEnabled;
```

- `private System.Single m_MapTileToolFOV`  

```csharp
private System.Single m_MapTileToolFOV;
```

- `private System.Single m_MapTileToolFarclip`  

```csharp
private System.Single m_MapTileToolFarclip;
```

- `private Unity.Mathematics.float3 m_MapTileToolPivot`  

```csharp
private Unity.Mathematics.float3 m_MapTileToolPivot;
```

- `private Unity.Mathematics.float2 m_MapTileToolAngle`  

```csharp
private Unity.Mathematics.float2 m_MapTileToolAngle;
```

- `private System.Single m_MapTileToolZoom`  

```csharp
private System.Single m_MapTileToolZoom;
```

- `private System.Single m_MapTileToolTransitionTime`  

```csharp
private System.Single m_MapTileToolTransitionTime;
```

- `private System.Single m_MoveSmoothing`  

```csharp
private System.Single m_MoveSmoothing;
```

- `private System.Single m_CollisionSmoothing`  

```csharp
private System.Single m_CollisionSmoothing;
```

- `private Game.Input.ProxyActionMap m_CameraMap`  

```csharp
private Game.Input.ProxyActionMap m_CameraMap;
```

- `private Game.Input.ProxyAction m_MoveAction`  

```csharp
private Game.Input.ProxyAction m_MoveAction;
```

- `private Game.Input.ProxyAction m_MoveFastAction`  

```csharp
private Game.Input.ProxyAction m_MoveFastAction;
```

- `private Game.Input.ProxyAction m_RotateAction`  

```csharp
private Game.Input.ProxyAction m_RotateAction;
```

- `private Game.Input.ProxyAction m_ZoomAction`  

```csharp
private Game.Input.ProxyAction m_ZoomAction;
```

- `private Cinemachine.CinemachineVirtualCamera m_VCam`  

```csharp
private Cinemachine.CinemachineVirtualCamera m_VCam;
```

- `private System.Single m_InitialFarClip`  

```csharp
private System.Single m_InitialFarClip;
```

- `private System.Single m_InitialFov`  

```csharp
private System.Single m_InitialFov;
```

- `private System.Single m_LastGameViewZoom`  

```csharp
private System.Single m_LastGameViewZoom;
```

- `private Unity.Mathematics.float2 m_LastGameViewAngle`  

```csharp
private Unity.Mathematics.float2 m_LastGameViewAngle;
```

- `private Unity.Mathematics.float3 m_LastGameViewPivot`  

```csharp
private Unity.Mathematics.float3 m_LastGameViewPivot;
```

- `private System.Single m_LastMapViewZoom`  

```csharp
private System.Single m_LastMapViewZoom;
```

- `private Unity.Mathematics.float2 m_LastMapViewAngle`  

```csharp
private Unity.Mathematics.float2 m_LastMapViewAngle;
```

- `private Unity.Mathematics.float3 m_LastMapViewPivot`  

```csharp
private Unity.Mathematics.float3 m_LastMapViewPivot;
```

- `private System.Action<System.Boolean> <EventCameraMovingChanged>k__BackingField`  

```csharp
private System.Action<System.Boolean> <EventCameraMovingChanged>k__BackingField;
```

- `private System.Boolean <moving>k__BackingField`  

```csharp
private System.Boolean <moving>k__BackingField;
```

- `private System.Boolean <inputEnabled>k__BackingField`  

```csharp
private System.Boolean <inputEnabled>k__BackingField;
```

- `private Unity.Mathematics.float3 <cameraPosition>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <cameraPosition>k__BackingField;
```

- `private System.Single <velocity>k__BackingField`  

```csharp
private System.Single <velocity>k__BackingField;
```

- `private System.Single m_MapViewTimer`  

```csharp
private System.Single m_MapViewTimer;
```

- `private System.Boolean <edgeScrolling>k__BackingField`  

```csharp
private System.Boolean <edgeScrolling>k__BackingField;
```

- `private System.Single <edgeScrollingSensitivity>k__BackingField`  

```csharp
private System.Single <edgeScrollingSensitivity>k__BackingField;
```

- `private System.Single <clipDistance>k__BackingField`  

```csharp
private System.Single <clipDistance>k__BackingField;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraSystem;
```

- `private Game.Rendering.CameraCollisionSystem m_CollisionSystem`  

```csharp
private Game.Rendering.CameraCollisionSystem m_CollisionSystem;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> inputActions { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> inputActions { get; }
```

- `public System.Action<System.Boolean> EventCameraMovingChanged { get; set }`  

```csharp
public System.Action<System.Boolean> EventCameraMovingChanged { get; set; }
```

- `public System.Boolean moving { get; private set }`  

```csharp
public System.Boolean moving { get; private set; }
```

- `public Cinemachine.LensSettings& lens { get }`  

```csharp
public Cinemachine.LensSettings& lens { get; }
```

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  

```csharp
public Cinemachine.ICinemachineCamera virtualCamera { get; }
```

- `public UnityEngine.Vector3 rotation { get; set }`  

```csharp
public UnityEngine.Vector3 rotation { get; set; }
```

- `public Game.Simulation.TerrainSystem terrainSystem { get }`  

```csharp
public Game.Simulation.TerrainSystem terrainSystem { get; }
```

- `public Game.Simulation.WaterSystem waterSystem { get }`  

```csharp
public Game.Simulation.WaterSystem waterSystem { get; }
```

- `public UnityEngine.Vector3 pivot { get; set }`  

```csharp
public UnityEngine.Vector3 pivot { get; set; }
```

- `public UnityEngine.Vector3 position { get; set }`  

```csharp
public UnityEngine.Vector3 position { get; set; }
```

- `public Unity.Mathematics.float2 angle { get; set }`  

```csharp
public Unity.Mathematics.float2 angle { get; set; }
```

- `public System.Single zoom { get; set }`  

```csharp
public System.Single zoom { get; set; }
```

- `public System.Boolean controllerEnabled { get; set }`  

```csharp
public System.Boolean controllerEnabled { get; set; }
```

- `public System.Boolean inputEnabled { get; set }`  

```csharp
public System.Boolean inputEnabled { get; set; }
```

- `public Colossal.Mathematics.Bounds1 zoomRange { get }`  

```csharp
public Colossal.Mathematics.Bounds1 zoomRange { get; }
```

- `public Unity.Mathematics.float3 cameraPosition { get; private set }`  

```csharp
public Unity.Mathematics.float3 cameraPosition { get; private set; }
```

- `public System.Single velocity { get; private set }`  

```csharp
public System.Single velocity { get; private set; }
```

- `public System.Boolean edgeScrolling { get; set }`  

```csharp
public System.Boolean edgeScrolling { get; set; }
```

- `public System.Single edgeScrollingSensitivity { get; set }`  

```csharp
public System.Single edgeScrollingSensitivity { get; set; }
```

- `public System.Single clipDistance { get; set }`  

```csharp
public System.Single clipDistance { get; set; }
```


## Constructors

- `public CameraController()`  

```csharp
public CameraController();
```


## Methods

- `private Awake() : System.Void`  

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

- `private GetCameraPos(Unity.Mathematics.float3 cameraOffset) : Unity.Mathematics.float3`  

```csharp
private float3 GetCameraPos(float3 cameraOffset)
	{
		float3 result = m_Pivot + cameraOffset;
		result.y += zoomRange.min * 0.5f;
		return result;
	}
```

- `private HandleMapViewCamera() : System.Boolean`  

```csharp
private bool HandleMapViewCamera()
	{
		float end;
		float2 to;
		float3 @float;
		float num;
		if (!MapTilesUISystem.mapTileViewActive)
		{
			if (m_MapViewTimer == 0f)
			{
				return false;
			}
			if (Mathf.Abs(m_MapViewTimer - m_MapTileToolTransitionTime) < Mathf.Epsilon)
			{
				m_Zoom = m_LastGameViewZoom;
				m_Angle = m_LastGameViewAngle;
				m_Pivot = m_LastGameViewPivot;
			}
			end = m_LastMapViewZoom;
			to = m_LastMapViewAngle;
			@float = m_LastMapViewPivot;
			m_MapViewTimer = math.max(m_MapViewTimer - Time.deltaTime, 0f);
			num = ((m_MapTileToolTransitionTime > 0f) ? (m_MapViewTimer / m_MapTileToolTransitionTime) : 0f);
		}
		else
		{
			m_LastMapViewAngle = m_Angle;
			m_LastMapViewZoom = m_Zoom;
			m_LastMapViewPivot = m_Pivot;
			if (Mathf.Abs(m_MapViewTimer - m_MapTileToolTransitionTime) < Mathf.Epsilon)
			{
				return false;
			}
			m_MapViewTimer = math.min(m_MapViewTimer + Time.deltaTime, m_MapTileToolTransitionTime);
			num = ((m_MapTileToolTransitionTime > 0f) ? (m_MapViewTimer / m_MapTileToolTransitionTime) : 1f);
			if (Mathf.Abs(num - 1f) < Mathf.Epsilon)
			{
				m_LastGameViewZoom = m_Zoom;
				m_LastGameViewAngle = m_Angle;
				m_LastGameViewPivot = m_Pivot;
				m_Zoom = m_MapTileToolZoom;
				m_Angle = new float2(Mathf.Round(m_Angle.x / 90f) * 90f, m_MapTileToolAngle.y);
				m_Pivot = m_MapTileToolPivot;
			}
			end = m_MapTileToolZoom;
			to = new float2(Mathf.Round(m_Angle.x / 90f) * 90f, m_MapTileToolAngle.y);
			@float = m_MapTileToolPivot;
		}
		if (TryGetTerrainHeight(@float, out var terrainHeight))
		{
			@float.y = terrainHeight;
		}
		num = Mathf.SmoothStep(0f, 1f, num);
		float3 float2 = math.lerp(m_Pivot, @float, num);
		float2 x = LerpAngle(m_Angle, to, num);
		float num2 = math.lerp(m_Zoom, end, num);
		m_VCam.m_Lens.FarClipPlane = math.lerp(m_InitialFarClip, m_MapTileToolFarclip, num);
		m_VCam.m_Lens.FieldOfView = math.lerp(m_InitialFov, m_MapTileToolFOV, num);
		float2 float3 = math.radians(x);
		float3 float4 = default(float3);
		float4.x = 0f - math.sin(float3.x);
		float4.y = 0f;
		float4.z = 0f - math.cos(float3.x);
		float3 x2 = float4;
		float4 *= math.cos(float3.y);
		float4.y = math.sin(float3.y);
		float3 float5 = -float4;
		float4 *= num2;
		float3 float6 = float2 + float4;
		float6.y += zoomRange.min * 0.5f;
		float3 y = math.cross(x2, new float3(0f, 1f, 0f));
		float3 up = math.cross(float5, y);
		if (terrainSystem != null)
		{
			TerrainHeightData data = terrainSystem.GetHeightData();
			WaterSurfaceData data2 = default(WaterSurfaceData);
			if (waterSystem != null)
			{
				data2 = waterSystem.GetSurfaceData(out var deps);
				deps.Complete();
			}
			if (data.isCreated)
			{
				float num3 = ((!data2.isCreated) ? (TerrainUtils.SampleHeight(ref data, float6) + zoomRange.min * 0.5f + (num2 - zoomRange.min) * 0.1f) : (WaterUtils.SampleHeight(ref data2, ref data, float6) + zoomRange.min * 0.5f + (num2 - zoomRange.min) * 0.1f));
				float num4 = (float6.y - num3) / num2;
				num4 = (math.sqrt(num4 * num4 + 0.2f) - num4) * (0.5f * num2);
				float6.y += num4;
			}
		}
		base.transform.localPosition = float6;
		base.transform.localRotation = quaternion.LookRotation(float5, up);
		return true;
	}
```

- `public static LerpAngle(Unity.Mathematics.float2 from, Unity.Mathematics.float2 to, System.Single t) : Unity.Mathematics.float2`  

```csharp
public static float2 LerpAngle(float2 from, float2 to, float t)
	{
		float num = ((to.x - from.x) % 360f + 540f) % 360f - 180f;
		return new float2(from.x + num * t % 360f, math.lerp(from.y, to.y, t));
	}
```

- `public static TryGet(Game.CameraController& cameraController) : System.Boolean`  

```csharp
public static bool TryGet(out CameraController cameraController)
	{
		GameObject gameObject = GameObject.FindGameObjectWithTag("GameplayCamera");
		if (gameObject != null)
		{
			cameraController = gameObject.GetComponent<CameraController>();
			return cameraController != null;
		}
		cameraController = null;
		return false;
	}
```

- `private TryGetTerrainHeight(UnityEngine.Vector3 pos, System.Single& terrainHeight) : System.Boolean`  

```csharp
private bool TryGetTerrainHeight(Vector3 pos, out float terrainHeight)
	{
		if (terrainSystem != null)
		{
			TerrainHeightData data = terrainSystem.GetHeightData();
			WaterSurfaceData data2 = default(WaterSurfaceData);
			if (waterSystem != null)
			{
				data2 = waterSystem.GetSurfaceData(out var deps);
				deps.Complete();
			}
			if (data.isCreated)
			{
				if (data2.isCreated)
				{
					terrainHeight = WaterUtils.SampleHeight(ref data2, ref data, pos);
				}
				else
				{
					terrainHeight = TerrainUtils.SampleHeight(ref data, pos);
				}
				return true;
			}
		}
		terrainHeight = 0f;
		return false;
	}
```

- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  

```csharp
public void TryMatchPosition(IGameCameraController other)
	{
		if (TryGetTerrainHeight(other.position, out var terrainHeight))
		{
			float num = other.position.y - terrainHeight;
			float num2 = Mathf.Sin(MathF.PI / 180f * other.rotation.x);
			float num3 = 1f / (2f - 4f * num2);
			float num4 = (8f * zoomRange.min - 20f * num) * num2 + zoomRange.min - 2f * num;
			zoom = Mathf.Clamp(Mathf.Abs(num3 * (Mathf.Sqrt(num4 * num4 - (4f - 8f * num2) * (-4f * zoomRange.min * zoomRange.min + 18f * zoomRange.min * num - 20f * num * num)) + num4)), zoomRange.min, zoomRange.max);
			Quaternion quaternion = Quaternion.Euler(other.rotation.x, other.rotation.y, other.rotation.z);
			pivot = other.position + quaternion * new Vector3(0f, 0f, zoom);
			angle = new float2(other.rotation.y, (other.rotation.x > 90f) ? (other.rotation.x - 360f) : other.rotation.x);
			base.transform.rotation = quaternion;
			base.transform.position = other.position;
		}
	}
```

- `public UpdateCamera() : System.Void`  

```csharp
public void UpdateCamera()
	{
		if (m_MapTileToolViewEnabled && HandleMapViewCamera())
		{
			return;
		}
		float2 @float = float2.zero;
		float2 float2 = float2.zero;
		float num = 0f;
		bool flag = false;
		if (m_CameraMap.enabled)
		{
			@float = MathUtils.MaxAbs(m_MoveAction.ReadValue<Vector2>(), m_MoveFastAction.ReadValue<Vector2>());
			float2 = m_RotateAction.ReadValue<Vector2>();
			num = m_ZoomAction.ReadValue<float>();
			if (edgeScrolling && InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse && InputManager.instance.mouseOnScreen)
			{
				float num2 = edgeScrollingSensitivity;
				float2 xy = ((float3)InputManager.instance.mousePosition).xy;
				xy *= 2f / new float2(Screen.width, Screen.height);
				xy -= 1f;
				float num3 = 0.02f;
				float2 float3 = new float2((float)Screen.height / (float)Screen.width * num3, num3);
				num2 *= math.saturate(math.cmax((math.abs(xy) - (1f - float3)) / float3));
				num2 *= Time.deltaTime;
				@float += math.normalizesafe(xy) * num2;
			}
		}
		float num4 = m_Zoom;
		m_Zoom = MathUtils.Clamp(math.pow(m_Zoom, 1f + num), zoomRange);
		if (num4 != m_Zoom)
		{
			flag = true;
		}
		float2.y = 0f - float2.y;
		m_Angle += float2;
		m_Angle.y = math.clamp(m_Angle.y, -90f, 90f);
		if (m_Angle.x < -180f)
		{
			m_Angle.x += 360f;
		}
		if (m_Angle.x > 180f)
		{
			m_Angle.x -= 360f;
		}
		float2 float4 = math.radians(m_Angle);
		float3 float5 = default(float3);
		float5.x = 0f - math.sin(float4.x);
		float5.y = 0f;
		float5.z = 0f - math.cos(float4.x);
		float3 float6 = float5;
		float5 *= math.cos(float4.y);
		float5.y = math.sin(float4.y);
		float3 float7 = -float5;
		float5 *= m_Zoom;
		float3 float8 = math.cross(float6, new float3(0f, 1f, 0f));
		float3 up = math.cross(float7, float8);
		@float *= m_Zoom;
		m_Pivot += @float.x * float8;
		m_Pivot -= @float.y * float6;
		float3 cameraPos = GetCameraPos(float5);
		if (terrainSystem != null)
		{
			TerrainHeightData data = terrainSystem.GetHeightData();
			WaterSurfaceData data2 = default(WaterSurfaceData);
			if (waterSystem != null && waterSystem.Loaded)
			{
				data2 = waterSystem.GetSurfaceData(out var deps);
				deps.Complete();
			}
			if (data.isCreated)
			{
				if (data2.isCreated)
				{
					m_Pivot.y = math.lerp(WaterUtils.SampleHeight(ref data2, ref data, m_Pivot), m_Pivot.y, m_MoveSmoothing);
				}
				else
				{
					m_Pivot.y = math.lerp(TerrainUtils.SampleHeight(ref data, m_Pivot), m_Pivot.y, m_MoveSmoothing);
				}
				m_Pivot = MathUtils.Clamp(bounds: GameManager.instance.gameMode.IsEditor() ? TerrainUtils.GetEditorCameraBounds(terrainSystem, ref data) : TerrainUtils.GetBounds(ref data), position: m_Pivot);
				cameraPos = GetCameraPos(float5);
				float num5 = ((!data2.isCreated) ? (TerrainUtils.SampleHeight(ref data, cameraPos) + zoomRange.min * 0.5f + (m_Zoom - zoomRange.min) * 0.1f) : (WaterUtils.SampleHeight(ref data2, ref data, cameraPos) + zoomRange.min * 0.5f + (m_Zoom - zoomRange.min) * 0.1f));
				float num6 = (cameraPos.y - num5) / m_Zoom;
				num6 = (math.sqrt(num6 * num6 + 0.2f) - num6) * (0.5f * m_Zoom);
				cameraPos.y += num6;
			}
		}
		float3 float9 = cameraPosition;
		quaternion quaternion = quaternion.LookRotation(float7, up);
		if (m_CollisionSystem != null && m_CameraSystem != null && m_CameraSystem.activeCamera != null)
		{
			float nearClipPlane = m_CameraSystem.activeCamera.nearClipPlane;
			float2 fieldOfView = default(float2);
			fieldOfView.y = m_CameraSystem.activeCamera.fieldOfView;
			fieldOfView.x = Camera.VerticalToHorizontalFieldOfView(fieldOfView.y, m_CameraSystem.activeCamera.aspect);
			m_CollisionSystem.CheckCollisions(ref cameraPos, float9, quaternion, math.min(m_Zoom - zoomRange.min, 200f), math.min(zoomRange.max - m_Zoom, 200f), math.max(nearClipPlane * 2f, zoomRange.min * 0.5f), nearClipPlane, m_CollisionSmoothing, fieldOfView);
		}
		Quaternion localRotation = base.transform.localRotation;
		cameraPosition = cameraPos;
		base.transform.localPosition = cameraPos;
		base.transform.localRotation = quaternion;
		velocity = math.lengthsq(float9 - cameraPosition) / Time.deltaTime;
		if (!localRotation.Equals(base.transform.localRotation) || !float9.Equals(cameraPosition))
		{
			flag = true;
		}
		if (moving != flag)
		{
			EventCameraMovingChanged?.Invoke(flag);
			moving = flag;
		}
		AudioManager.instance?.UpdateAudioListener(base.transform.position, base.transform.rotation);
	}
```


## Nested types

- `Game.CameraController+<Awake>d__95`  
- `Game.CameraController+<get_inputActions>d__20`  


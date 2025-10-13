# Game.Rendering.CameraUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CameraUpdateSystem : Game.GameSystemBase
{
    private Game.Common.RaycastSystem m_RaycastSystem;
    private UnityEngine.Rendering.Volume m_Volume;
    private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField;
    private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings;
    private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance;
    private Unity.Mathematics.float4 m_StoredShadowBorders;
    private Game.Input.InputActivator[] m_CameraActionActivators;
    private Game.Input.InputBarrier[] m_CameraActionBarriers;
    private Game.Rendering.Viewer <activeViewer>k__BackingField;
    private Game.CameraController <gamePlayController>k__BackingField;
    private Game.CinematicCameraController <cinematicCameraController>k__BackingField;
    private Game.OrbitCameraController <orbitCameraController>k__BackingField;
    private System.Single <nearClipPlane>k__BackingField;
    private Unity.Mathematics.float3 <position>k__BackingField;
    private Unity.Mathematics.float3 <direction>k__BackingField;
    private System.Single <zoom>k__BackingField;

    public Game.Rendering.Viewer activeViewer { get; private set; }
    public Game.CameraController gamePlayController { get; set; }
    public Game.CinematicCameraController cinematicCameraController { get; set; }
    public Game.OrbitCameraController orbitCameraController { get; set; }
    public UnityEngine.Camera activeCamera { get; set; }
    public System.Single nearClipPlane { get; private set; }
    public Unity.Mathematics.float3 position { get; private set; }
    public Unity.Mathematics.float3 direction { get; private set; }
    public System.Single zoom { get; private set; }
    public Game.Rendering.IGameCameraController activeCameraController { get; set; }

    public CameraUpdateSystem();

    private System.Boolean CheckOrCacheViewer();
    public Game.Rendering.CameraBlend GetBlendWeight(System.Single& weight);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RefreshInput();
    public System.Boolean TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters);
    public System.Boolean TryGetViewer(Game.Rendering.Viewer& viewer);
    private System.Void UpdateDepthOfField(System.Single distance);
    private System.Void UpdateShadows(Game.Rendering.Viewer viewer);
}
```


## Fields

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private UnityEngine.Rendering.Volume m_Volume`  

```csharp
private UnityEngine.Rendering.Volume m_Volume;
```

- `private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField`  

```csharp
private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField;
```

- `private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings`  

```csharp
private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings;
```

- `private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance`  

```csharp
private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance;
```

- `private Unity.Mathematics.float4 m_StoredShadowBorders`  

```csharp
private Unity.Mathematics.float4 m_StoredShadowBorders;
```

- `private Game.Input.InputActivator[] m_CameraActionActivators`  

```csharp
private Game.Input.InputActivator[] m_CameraActionActivators;
```

- `private Game.Input.InputBarrier[] m_CameraActionBarriers`  

```csharp
private Game.Input.InputBarrier[] m_CameraActionBarriers;
```

- `private Game.Rendering.Viewer <activeViewer>k__BackingField`  

```csharp
private Game.Rendering.Viewer <activeViewer>k__BackingField;
```

- `private Game.CameraController <gamePlayController>k__BackingField`  

```csharp
private Game.CameraController <gamePlayController>k__BackingField;
```

- `private Game.CinematicCameraController <cinematicCameraController>k__BackingField`  

```csharp
private Game.CinematicCameraController <cinematicCameraController>k__BackingField;
```

- `private Game.OrbitCameraController <orbitCameraController>k__BackingField`  

```csharp
private Game.OrbitCameraController <orbitCameraController>k__BackingField;
```

- `private System.Single <nearClipPlane>k__BackingField`  

```csharp
private System.Single <nearClipPlane>k__BackingField;
```

- `private Unity.Mathematics.float3 <position>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <position>k__BackingField;
```

- `private Unity.Mathematics.float3 <direction>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <direction>k__BackingField;
```

- `private System.Single <zoom>k__BackingField`  

```csharp
private System.Single <zoom>k__BackingField;
```


## Properties

- `public Game.Rendering.Viewer activeViewer { get; private set }`  

```csharp
public Game.Rendering.Viewer activeViewer { get; private set; }
```

- `public Game.CameraController gamePlayController { get; set }`  

```csharp
public Game.CameraController gamePlayController { get; set; }
```

- `public Game.CinematicCameraController cinematicCameraController { get; set }`  

```csharp
public Game.CinematicCameraController cinematicCameraController { get; set; }
```

- `public Game.OrbitCameraController orbitCameraController { get; set }`  

```csharp
public Game.OrbitCameraController orbitCameraController { get; set; }
```

- `public UnityEngine.Camera activeCamera { get; set }`  

```csharp
public UnityEngine.Camera activeCamera { get; set; }
```

- `public System.Single nearClipPlane { get; private set }`  

```csharp
public System.Single nearClipPlane { get; private set; }
```

- `public Unity.Mathematics.float3 position { get; private set }`  

```csharp
public Unity.Mathematics.float3 position { get; private set; }
```

- `public Unity.Mathematics.float3 direction { get; private set }`  

```csharp
public Unity.Mathematics.float3 direction { get; private set; }
```

- `public System.Single zoom { get; private set }`  

```csharp
public System.Single zoom { get; private set; }
```

- `public Game.Rendering.IGameCameraController activeCameraController { get; set }`  

```csharp
public Game.Rendering.IGameCameraController activeCameraController { get; set; }
```


## Constructors

- `public CameraUpdateSystem()`  

```csharp
[Preserve]
	public CameraUpdateSystem()
	{
	}
```


## Methods

- `private CheckOrCacheViewer() : System.Boolean`  

```csharp
private bool CheckOrCacheViewer()
	{
		if (activeViewer != null && activeViewer.camera != null)
		{
			nearClipPlane = activeViewer.nearClipPlane;
			position = activeViewer.position;
			direction = activeViewer.forward;
			zoom = activeCameraController?.zoom ?? zoom;
			activeViewer.Raycast(m_RaycastSystem);
			return true;
		}
		nearClipPlane = 0f;
		position = float3.zero;
		direction = new float3(0f, 0f, 1f);
		activeCamera = null;
		zoom = 0f;
		return false;
	}
```

- `public GetBlendWeight(System.Single& weight) : Game.Rendering.CameraBlend`  

```csharp
public CameraBlend GetBlendWeight(out float weight)
	{
		if (CinemachineCore.Instance.BrainCount > 0)
		{
			CinemachineBrain activeBrain = CinemachineCore.Instance.GetActiveBrain(0);
			if (activeBrain != null && activeBrain.IsBlending)
			{
				CinemachineBlend activeBlend = activeBrain.ActiveBlend;
				if (activeBlend.IsValid && !activeBlend.IsComplete)
				{
					weight = activeBlend.BlendWeight;
					if (activeBlend.CamB == cinematicCameraController.virtualCamera)
					{
						return CameraBlend.ToCinematicCamera;
					}
					if (activeBlend.CamA == cinematicCameraController.virtualCamera)
					{
						return CameraBlend.FromCinematicCamera;
					}
				}
			}
		}
		weight = 1f;
		return CameraBlend.None;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RaycastSystem = base.World.GetOrCreateSystemManaged<RaycastSystem>();
		m_Volume = VolumeHelper.CreateVolume("CameraControllerVolume", 51);
		VolumeHelper.GetOrCreateVolumeComponent(m_Volume, ref m_DepthOfField);
		VolumeHelper.GetOrCreateVolumeComponent(m_Volume, ref m_ShadowSettings);
		ProxyActionMap proxyActionMap = InputManager.instance.FindActionMap("Camera");
		m_CameraActionActivators = proxyActionMap.actions.Values.Select((ProxyAction a) => new InputActivator(ignoreIsBuiltIn: true, "CameraUpdateSystem(" + a.name + ")", a)).ToArray();
		m_CameraActionBarriers = proxyActionMap.actions.Values.Select((ProxyAction a) => new InputBarrier("CameraUpdateSystem(" + a.name + ")", a, InputManager.DeviceType.Mouse)).ToArray();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		VolumeHelper.DestroyVolume(m_Volume);
		if (gamePlayController != null)
		{
			gamePlayController.controllerEnabled = false;
		}
		if (cinematicCameraController != null)
		{
			cinematicCameraController.controllerEnabled = false;
		}
		if (orbitCameraController != null)
		{
			orbitCameraController.controllerEnabled = false;
		}
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		activeCamera = Camera.main;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool num = activeViewer != null && activeViewer.camera != null;
		float distance = 0f;
		if (num)
		{
			activeViewer.UpdateRaycast(m_RaycastSystem, base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime);
			distance = activeViewer.viewerDistances.focus;
			UpdateShadows(activeViewer);
		}
		UpdateDepthOfField(distance);
		activeCameraController?.UpdateCamera();
		for (int i = 0; i < CinemachineCore.Instance.BrainCount; i++)
		{
			CinemachineCore.Instance.GetActiveBrain(i).ManualUpdate();
		}
		CheckOrCacheViewer();
		RefreshInput();
	}
```

- `private RefreshInput() : System.Void`  

```csharp
private void RefreshInput()
	{
		InputActivator[] array = m_CameraActionActivators;
		for (int i = 0; i < array.Length; i++)
		{
			array[i].enabled = activeCameraController != null;
		}
		InputBarrier[] array2 = m_CameraActionBarriers;
		foreach (InputBarrier inputBarrier in array2)
		{
			if (activeCameraController == null)
			{
				inputBarrier.blocked = false;
			}
			else if (!InputManager.instance.mouseOverUI)
			{
				inputBarrier.blocked = false;
			}
			else if (inputBarrier.actions.All((ProxyAction a) => !a.IsInProgress()))
			{
				inputBarrier.blocked = true;
			}
		}
	}
```

- `public TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters) : System.Boolean`  

```csharp
public bool TryGetLODParameters(out LODParameters lodParameters)
	{
		if (activeViewer != null)
		{
			return activeViewer.TryGetLODParameters(out lodParameters);
		}
		lodParameters = default(LODParameters);
		return false;
	}
```

- `public TryGetViewer(Game.Rendering.Viewer& viewer) : System.Boolean`  

```csharp
public bool TryGetViewer(out Viewer viewer)
	{
		viewer = activeViewer;
		return activeViewer != null;
	}
```

- `private UpdateDepthOfField(System.Single distance) : System.Void`  

```csharp
private void UpdateDepthOfField(float distance)
	{
		Game.Settings.GraphicsSettings graphicsSettings = SharedSettings.instance?.graphics;
		if (graphicsSettings != null)
		{
			if (graphicsSettings.depthOfFieldMode == Game.Settings.GraphicsSettings.DepthOfFieldMode.TiltShift)
			{
				m_DepthOfField.focusMode.Override(DepthOfFieldMode.Manual);
				m_DepthOfField.nearFocusStart.Override(distance - distance * graphicsSettings.tiltShiftNearStart);
				m_DepthOfField.nearFocusEnd.Override(distance - distance * graphicsSettings.tiltShiftNearEnd);
				m_DepthOfField.farFocusStart.Override(distance + distance * graphicsSettings.tiltShiftFarStart);
				m_DepthOfField.farFocusEnd.Override(distance + distance * graphicsSettings.tiltShiftFarEnd);
			}
			else if (graphicsSettings.depthOfFieldMode == Game.Settings.GraphicsSettings.DepthOfFieldMode.Physical)
			{
				m_DepthOfField.focusMode.Override(DepthOfFieldMode.UsePhysicalCamera);
				m_DepthOfField.focusDistanceMode.Override(FocusDistanceMode.Volume);
				m_DepthOfField.focusDistance.Override(distance);
			}
			else
			{
				m_DepthOfField.focusMode.Override(DepthOfFieldMode.Off);
			}
		}
	}
```

- `private UpdateShadows(Game.Rendering.Viewer viewer) : System.Void`  

```csharp
private void UpdateShadows(Viewer viewer)
	{
		Camera camera = viewer.camera;
		if (!camera)
		{
			return;
		}
		if (math.lengthsq(m_StoredShadowSplitsAndDistance) == 0f)
		{
			HDCamera orCreate = HDCamera.GetOrCreate(camera);
			if (orCreate != null)
			{
				HDShadowSettings component = orCreate.volumeStack.GetComponent<HDShadowSettings>();
				float value = component.maxShadowDistance.value;
				float[] cascadeShadowSplits = component.cascadeShadowSplits;
				float[] cascadeShadowBorders = component.cascadeShadowBorders;
				m_StoredShadowSplitsAndDistance = new float4(cascadeShadowSplits[0] * value, cascadeShadowSplits[1] * value, cascadeShadowSplits[2] * value, value);
				m_StoredShadowBorders = new float4(cascadeShadowBorders[0], cascadeShadowBorders[1], cascadeShadowBorders[2], cascadeShadowBorders[3]);
			}
		}
		if (!viewer.shadowsAdjustFarDistance)
		{
			m_ShadowSettings.maxShadowDistance.overrideState = false;
			m_ShadowSettings.cascadeShadowSplit0.overrideState = false;
			m_ShadowSettings.cascadeShadowSplit1.overrideState = false;
			m_ShadowSettings.cascadeShadowSplit2.overrideState = false;
			m_ShadowSettings.cascadeShadowBorder0.overrideState = false;
			m_ShadowSettings.cascadeShadowBorder1.overrideState = false;
			m_ShadowSettings.cascadeShadowBorder2.overrideState = false;
			m_ShadowSettings.cascadeShadowBorder3.overrideState = false;
			return;
		}
		float w = m_StoredShadowSplitsAndDistance.w;
		float y = math.lerp(viewer.viewerDistances.farthestSurface, viewer.viewerDistances.maxDistanceToSeaLevel, 0.2f) * 1.1f;
		w = math.min(w, y);
		float x = m_StoredShadowSplitsAndDistance.x;
		float y2 = m_StoredShadowSplitsAndDistance.y;
		float z = m_StoredShadowSplitsAndDistance.z;
		x = math.clamp(x, 15f, w * 0.15f);
		y2 = math.clamp(y2, 45f, w * 0.3f);
		z = math.clamp(z, 135f, w * 0.6f);
		float ground = viewer.viewerDistances.ground;
		x = math.min(x, ground * 5f);
		y2 = math.min(y2, ground * 30f);
		z = math.min(z, ground * 200f);
		w = math.max(w, z * 1.2f);
		m_ShadowSettings.maxShadowDistance.Override(w);
		m_ShadowSettings.cascadeShadowSplit0.Override(x / w);
		m_ShadowSettings.cascadeShadowSplit1.Override(y2 / w);
		m_ShadowSettings.cascadeShadowSplit2.Override(z / w);
		m_ShadowSettings.cascadeShadowBorder0.Override(m_StoredShadowBorders.x);
		m_ShadowSettings.cascadeShadowBorder1.Override(m_StoredShadowBorders.y);
		m_ShadowSettings.cascadeShadowBorder2.Override(m_StoredShadowBorders.z);
		m_ShadowSettings.cascadeShadowBorder3.Override(m_StoredShadowBorders.w);
	}
```


## Nested types

- `Game.Rendering.CameraUpdateSystem+<>c`  


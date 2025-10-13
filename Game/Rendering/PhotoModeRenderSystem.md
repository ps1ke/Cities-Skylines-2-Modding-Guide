# Game.Rendering.PhotoModeRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class PhotoModeRenderSystem : Game.GameSystemBase
{
    private UnityEngine.Rendering.Volume m_CameraControlVolume;
    private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments;
    private UnityEngine.Rendering.HighDefinition.WhiteBalance m_WhiteBalance;
    private UnityEngine.Rendering.HighDefinition.PaniniProjection m_PaniniProjection;
    private UnityEngine.Rendering.HighDefinition.Vignette m_Vignette;
    private UnityEngine.Rendering.HighDefinition.FilmGrain m_FilmGrain;
    private UnityEngine.Rendering.HighDefinition.ShadowsMidtonesHighlights m_ShadowsMidtonesHighlights;
    private UnityEngine.Rendering.HighDefinition.Bloom m_Bloom;
    private UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlur;
    private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField;
    private UnityEngine.Rendering.HighDefinition.CloudLayer m_DistanceClouds;
    private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds;
    private UnityEngine.Rendering.HighDefinition.Fog m_Fog;
    private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_Sky;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focalLength;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> sensorSize;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> aperture;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> iso;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> shutterSpeed;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Camera+GateFitMode> gateFitMode;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> bladeCount;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> curvature;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> barrelClipping;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> anamorphism;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focusDistance;
    private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> lensShift;
    private System.Boolean m_Active;
    private Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> <photoModeProperties>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUIPreset> m_Presets;
    private static readonly System.String[] kApertureFormatNames;
    private static readonly UnityEngine.Vector2[] kApertureFormatValues;
    private static const System.String kSensorTypePreset;
    private static const System.String kCameraApertureShape;
    private static const System.String kCameraBody;
    private static const System.String kCameraLens;
    private static const System.String kCamera;
    private static const System.String kColorGrading;
    private static const System.String kLens;
    private static const System.String kWeather;
    private static const System.String kEnvironment;

    public Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> photoModeProperties { get; private set; }
    public System.Collections.Generic.IReadOnlyCollection<Game.UI.InGame.PhotoModeUIPreset> presets { get; }

    public PhotoModeRenderSystem();

    private System.Void <InitializeProperties>b__56_111(System.Single value);
    private System.Single <InitializeProperties>b__56_112();
    private System.Void <InitializeProperties>b__56_113();
    private System.Void <InitializeProperties>b__56_114(System.Single value);
    private System.Single <InitializeProperties>b__56_115();
    private System.Void <InitializeProperties>b__56_118();
    private System.Void <InitializeProperties>b__56_119(System.Single value);
    private System.Single <InitializeProperties>b__56_120();
    private System.Void <InitializeProperties>b__56_123(System.Boolean enabled);
    private System.Boolean <InitializeProperties>b__56_124();
    private System.Void <InitializeProperties>b__56_125(System.Single value);
    private System.Single <InitializeProperties>b__56_126();
    private System.Void <InitializeProperties>b__56_129();
    private System.Boolean <InitializeProperties>b__56_19();
    private System.Boolean <InitializeProperties>b__56_21();
    private System.Boolean <InitializeProperties>b__56_23();
    private System.Boolean <InitializeProperties>b__56_25();
    private System.Boolean <InitializeProperties>b__56_27();
    private System.Boolean <InitializeProperties>b__56_29();
    private System.Boolean <InitializeProperties>b__56_31();
    private System.Single <InitializeProperties>g__FieldOfViewToFocalLength|56_1(System.Single v);
    private System.Single <InitializeProperties>g__FocalLengthToFieldOfView|56_0(System.Single v);
    private System.Single <InitializeProperties>g__MaxFieldOfViewToFocalLength|56_3();
    private System.Single <InitializeProperties>g__MaxFocalLength|56_5();
    private System.Single <InitializeProperties>g__MinFieldOfViewToFocalLength|56_2();
    private System.Single <InitializeProperties>g__MinFocalLength|56_4();
    private System.Void AddPreset(Game.UI.InGame.PhotoModeUIPreset preset);
    public System.Void AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty property);
    public System.Void AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty[] property);
    public System.Void DisableAllCameraProperties();
    public System.Void Enable(System.Boolean enabled);
    private System.Void InitializeProperties();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private UnityEngine.Rendering.Volume m_CameraControlVolume`  

```csharp
private UnityEngine.Rendering.Volume m_CameraControlVolume;
```

- `private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments`  

```csharp
private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments;
```

- `private UnityEngine.Rendering.HighDefinition.WhiteBalance m_WhiteBalance`  

```csharp
private UnityEngine.Rendering.HighDefinition.WhiteBalance m_WhiteBalance;
```

- `private UnityEngine.Rendering.HighDefinition.PaniniProjection m_PaniniProjection`  

```csharp
private UnityEngine.Rendering.HighDefinition.PaniniProjection m_PaniniProjection;
```

- `private UnityEngine.Rendering.HighDefinition.Vignette m_Vignette`  

```csharp
private UnityEngine.Rendering.HighDefinition.Vignette m_Vignette;
```

- `private UnityEngine.Rendering.HighDefinition.FilmGrain m_FilmGrain`  

```csharp
private UnityEngine.Rendering.HighDefinition.FilmGrain m_FilmGrain;
```

- `private UnityEngine.Rendering.HighDefinition.ShadowsMidtonesHighlights m_ShadowsMidtonesHighlights`  

```csharp
private UnityEngine.Rendering.HighDefinition.ShadowsMidtonesHighlights m_ShadowsMidtonesHighlights;
```

- `private UnityEngine.Rendering.HighDefinition.Bloom m_Bloom`  

```csharp
private UnityEngine.Rendering.HighDefinition.Bloom m_Bloom;
```

- `private UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlur`  

```csharp
private UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlur;
```

- `private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField`  

```csharp
private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField;
```

- `private UnityEngine.Rendering.HighDefinition.CloudLayer m_DistanceClouds`  

```csharp
private UnityEngine.Rendering.HighDefinition.CloudLayer m_DistanceClouds;
```

- `private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds`  

```csharp
private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds;
```

- `private UnityEngine.Rendering.HighDefinition.Fog m_Fog`  

```csharp
private UnityEngine.Rendering.HighDefinition.Fog m_Fog;
```

- `private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_Sky`  

```csharp
private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_Sky;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focalLength`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focalLength;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> sensorSize`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> sensorSize;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> aperture`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> aperture;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> iso`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> iso;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> shutterSpeed`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> shutterSpeed;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Camera+GateFitMode> gateFitMode`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Camera+GateFitMode> gateFitMode;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> bladeCount`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> bladeCount;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> curvature`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> curvature;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> barrelClipping`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> barrelClipping;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> anamorphism`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> anamorphism;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focusDistance`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focusDistance;
```

- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> lensShift`  

```csharp
private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> lensShift;
```

- `private System.Boolean m_Active`  

```csharp
private System.Boolean m_Active;
```

- `private Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> <photoModeProperties>k__BackingField`  

```csharp
private Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> <photoModeProperties>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUIPreset> m_Presets`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUIPreset> m_Presets;
```

- `private static readonly System.String[] kApertureFormatNames`  

```csharp
private static readonly System.String[] kApertureFormatNames;
```

- `private static readonly UnityEngine.Vector2[] kApertureFormatValues`  

```csharp
private static readonly UnityEngine.Vector2[] kApertureFormatValues;
```

- `private static const System.String kSensorTypePreset`  

```csharp
private static const System.String kSensorTypePreset;
```

- `private static const System.String kCameraApertureShape`  

```csharp
private static const System.String kCameraApertureShape;
```

- `private static const System.String kCameraBody`  

```csharp
private static const System.String kCameraBody;
```

- `private static const System.String kCameraLens`  

```csharp
private static const System.String kCameraLens;
```

- `private static const System.String kCamera`  

```csharp
private static const System.String kCamera;
```

- `private static const System.String kColorGrading`  

```csharp
private static const System.String kColorGrading;
```

- `private static const System.String kLens`  

```csharp
private static const System.String kLens;
```

- `private static const System.String kWeather`  

```csharp
private static const System.String kWeather;
```

- `private static const System.String kEnvironment`  

```csharp
private static const System.String kEnvironment;
```


## Properties

- `public Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> photoModeProperties { get; private set }`  

```csharp
public Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> photoModeProperties { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Game.UI.InGame.PhotoModeUIPreset> presets { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Game.UI.InGame.PhotoModeUIPreset> presets { get; }
```


## Constructors

- `public PhotoModeRenderSystem()`  

```csharp
[Preserve]
	public PhotoModeRenderSystem()
	{
	}
```


## Methods

- `private <InitializeProperties>b__56_111(System.Single value) : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_111(System.Single value);
```

- `private <InitializeProperties>b__56_112() : System.Single`  

```csharp
private System.Single <InitializeProperties>b__56_112();
```

- `private <InitializeProperties>b__56_113() : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_113();
```

- `private <InitializeProperties>b__56_114(System.Single value) : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_114(System.Single value);
```

- `private <InitializeProperties>b__56_115() : System.Single`  

```csharp
private System.Single <InitializeProperties>b__56_115();
```

- `private <InitializeProperties>b__56_118() : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_118();
```

- `private <InitializeProperties>b__56_119(System.Single value) : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_119(System.Single value);
```

- `private <InitializeProperties>b__56_120() : System.Single`  

```csharp
private System.Single <InitializeProperties>b__56_120();
```

- `private <InitializeProperties>b__56_123(System.Boolean enabled) : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_123(System.Boolean enabled);
```

- `private <InitializeProperties>b__56_124() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_124();
```

- `private <InitializeProperties>b__56_125(System.Single value) : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_125(System.Single value);
```

- `private <InitializeProperties>b__56_126() : System.Single`  

```csharp
private System.Single <InitializeProperties>b__56_126();
```

- `private <InitializeProperties>b__56_129() : System.Void`  

```csharp
private System.Void <InitializeProperties>b__56_129();
```

- `private <InitializeProperties>b__56_19() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_19();
```

- `private <InitializeProperties>b__56_21() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_21();
```

- `private <InitializeProperties>b__56_23() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_23();
```

- `private <InitializeProperties>b__56_25() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_25();
```

- `private <InitializeProperties>b__56_27() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_27();
```

- `private <InitializeProperties>b__56_29() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_29();
```

- `private <InitializeProperties>b__56_31() : System.Boolean`  

```csharp
private System.Boolean <InitializeProperties>b__56_31();
```

- `private <InitializeProperties>g__FieldOfViewToFocalLength|56_1(System.Single v) : System.Single`  

```csharp
private System.Single <InitializeProperties>g__FieldOfViewToFocalLength|56_1(System.Single v);
```

- `private <InitializeProperties>g__FocalLengthToFieldOfView|56_0(System.Single v) : System.Single`  

```csharp
private System.Single <InitializeProperties>g__FocalLengthToFieldOfView|56_0(System.Single v);
```

- `private <InitializeProperties>g__MaxFieldOfViewToFocalLength|56_3() : System.Single`  

```csharp
private System.Single <InitializeProperties>g__MaxFieldOfViewToFocalLength|56_3();
```

- `private <InitializeProperties>g__MaxFocalLength|56_5() : System.Single`  

```csharp
private System.Single <InitializeProperties>g__MaxFocalLength|56_5();
```

- `private <InitializeProperties>g__MinFieldOfViewToFocalLength|56_2() : System.Single`  

```csharp
private System.Single <InitializeProperties>g__MinFieldOfViewToFocalLength|56_2();
```

- `private <InitializeProperties>g__MinFocalLength|56_4() : System.Single`  

```csharp
private System.Single <InitializeProperties>g__MinFocalLength|56_4();
```

- `private AddPreset(Game.UI.InGame.PhotoModeUIPreset preset) : System.Void`  

```csharp
private void AddPreset(PhotoModeUIPreset preset)
	{
		m_Presets.Add(preset);
	}
```

- `public AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.Void`  

```csharp
AddProperty(new PhotoModeProperty
		{
			id = "Simulation Speed",
			group = "Environment",
			setValue = delegate(float value)
			{
				m_SimulationSystem.selectedSpeed = value;
			}
```

- `public AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty[] property) : System.Void`  

```csharp
AddProperty(new PhotoModeProperty
		{
			id = "Simulation Speed",
			group = "Environment",
			setValue = delegate(float value)
			{
				m_SimulationSystem.selectedSpeed = value;
			}
```

- `public DisableAllCameraProperties() : System.Void`  

```csharp
public void DisableAllCameraProperties()
	{
		foreach (KeyValuePair<string, PhotoModeProperty> photoModeProperty in photoModeProperties)
		{
			photoModeProperty.Value.setEnabled?.Invoke(obj: false);
		}
	}
```

- `public Enable(System.Boolean enabled) : System.Void`  

```csharp
public void Enable(bool enabled)
	{
		m_Active = enabled;
		if (m_Active)
		{
			base.Enabled = enabled;
		}
	}
```

- `private InitializeProperties() : System.Void`  

```csharp
private void InitializeProperties()
	{
		photoModeProperties = new OrderedDictionary<string, PhotoModeProperty>();
		AddProperty(PhotoModeUtils.GroupTitle("Camera", "CameraBody"));
		PhotoModeProperty[] array;
		AddProperty(array = PhotoModeUtils.BindProperty("Camera", () => sensorSize, 0.1f, 1000f));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => iso, 200));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => shutterSpeed, 0.000125f, 30f));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => gateFitMode));
		AddProperty(new PhotoModeProperty
		{
			id = "Camera collision",
			group = "Camera",
			setValue = delegate(float value)
			{
				bool collisionsEnabled = PhotoModeUtils.FloatToBoolean(value);
				if (m_CameraUpdateSystem.cinematicCameraController != null)
				{
					m_CameraUpdateSystem.cinematicCameraController.collisionsEnabled = collisionsEnabled;
				}
				if (m_CameraUpdateSystem.orbitCameraController != null)
				{
					m_CameraUpdateSystem.orbitCameraController.collisionsEnabled = collisionsEnabled;
				}
			},
			getValue = delegate
			{
				bool flag = false;
				if (m_CameraUpdateSystem.cinematicCameraController != null)
				{
					flag |= m_CameraUpdateSystem.cinematicCameraController.collisionsEnabled;
				}
				if (m_CameraUpdateSystem.orbitCameraController != null)
				{
					flag |= m_CameraUpdateSystem.orbitCameraController.collisionsEnabled;
				}
				return PhotoModeUtils.BooleanToFloat(flag);
			},
			reset = delegate
			{
				if (m_CameraUpdateSystem.cinematicCameraController != null)
				{
					m_CameraUpdateSystem.cinematicCameraController.collisionsEnabled = false;
				}
				if (m_CameraUpdateSystem.orbitCameraController != null)
				{
					m_CameraUpdateSystem.orbitCameraController.collisionsEnabled = false;
				}
			},
			overrideControl = PhotoModeProperty.OverrideControl.Checkbox
		});
		AddProperty(PhotoModeUtils.GroupTitle("Camera", "CameraLens"));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => focalLength, MinFocalLength, MaxFocalLength, FieldOfViewToFocalLength, FocalLengthToFieldOfView));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => lensShift));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => aperture, 0.7f, 32f));
		AddProperty(PhotoModeUtils.GroupTitle("Camera", "CameraApertureShape"));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => bladeCount, 3, 11));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => curvature, 0.7f, 32f));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => barrelClipping, 0f, 1f));
		AddProperty(PhotoModeUtils.BindProperty("Camera", () => anamorphism, -1f, 1f));
		AddProperty(new PhotoModeProperty
		{
			id = "Roll",
			group = "Camera",
			setValue = delegate(float value)
			{
				if (m_CameraUpdateSystem.cinematicCameraController != null)
				{
					m_CameraUpdateSystem.cinematicCameraController.dutch = value;
				}
			},
			getValue = () => (m_CameraUpdateSystem.cinematicCameraController != null) ? m_CameraUpdateSystem.cinematicCameraController.dutch : 0f,
			min = () => -45f,
			max = () => 45f,
			reset = delegate
			{
				if (m_CameraUpdateSystem.cinematicCameraController != null)
				{
					m_CameraUpdateSystem.cinematicCameraController.dutch = 0f;
				}
			}
		});
		AddProperty(PhotoModeUtils.GroupTitle("Lens", m_DepthOfField.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.focusMode));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.focusDistance, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode == DepthOfFieldMode.UsePhysicalCamera));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.nearFocusStart, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode == DepthOfFieldMode.Manual));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.nearFocusEnd, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode == DepthOfFieldMode.Manual));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.farFocusStart, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode == DepthOfFieldMode.Manual));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.farFocusEnd, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode == DepthOfFieldMode.Manual));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.m_NearMaxBlur, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode != DepthOfFieldMode.Off));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_DepthOfField.m_FarMaxBlur, () => m_DepthOfField.IsActive() && m_DepthOfField.focusMode != DepthOfFieldMode.Off));
		AddProperty(PhotoModeUtils.GroupTitle("Lens", m_MotionBlur.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_MotionBlur.intensity));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_MotionBlur.minimumVelocity));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_MotionBlur.maximumVelocity));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_MotionBlur.depthComparisonExtent));
		AddProperty(PhotoModeUtils.GroupTitle("Lens", m_Bloom.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Bloom.threshold));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Bloom.intensity));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Bloom.scatter));
		AddProperty(PhotoModeUtils.GroupTitle("Lens", m_Vignette.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Vignette.intensity));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Vignette.color));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Vignette.center, 0f, 1f));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Vignette.smoothness));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Vignette.roundness));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_Vignette.rounded));
		AddProperty(PhotoModeUtils.GroupTitle("Lens", m_FilmGrain.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_FilmGrain.type));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_FilmGrain.intensity));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_FilmGrain.response));
		AddProperty(PhotoModeUtils.GroupTitle("Lens", m_PaniniProjection.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_PaniniProjection.distance));
		AddProperty(PhotoModeUtils.BindProperty("Lens", () => m_PaniniProjection.cropToFit));
		AddProperty(PhotoModeUtils.GroupTitle("Color", m_ColorAdjustments.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_ColorAdjustments.postExposure));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_ColorAdjustments.contrast));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_ColorAdjustments.colorFilter));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_ColorAdjustments.hueShift));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_ColorAdjustments.saturation));
		AddProperty(PhotoModeUtils.GroupTitle("Color", m_WhiteBalance.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_WhiteBalance.temperature));
		AddProperty(PhotoModeUtils.BindProperty("Color", () => m_WhiteBalance.tint));
		AddProperty(PhotoModeUtils.GroupTitle("Color", m_ShadowsMidtonesHighlights.GetType().Name));
		AddProperty(PhotoModeUtils.BindPropertyW("Color", () => m_ShadowsMidtonesHighlights.shadows, -1f, 1f));
		AddProperty(PhotoModeUtils.BindPropertyW("Color", () => m_ShadowsMidtonesHighlights.midtones, -1f, 1f));
		AddProperty(PhotoModeUtils.BindPropertyW("Color", () => m_ShadowsMidtonesHighlights.highlights, -1f, 1f));
		AddProperty(PhotoModeUtils.GroupTitle("Weather", m_DistanceClouds.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.opacity));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.altitude));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.tint));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.exposure));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.rotation));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.thickness));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.opacityR));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.opacityG));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.opacityB));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_DistanceClouds.layerA.opacityA));
		AddProperty(PhotoModeUtils.GroupTitle("Weather", m_VolumetricClouds.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.densityMultiplier));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.shapeFactor));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.shapeScale));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.shapeOffset));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.erosionFactor));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.erosionScale));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.erosionNoiseType));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.bottomAltitude));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.altitudeRange));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.numPrimarySteps));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.numLightSteps));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.sunLightDimmer));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.erosionOcclusion));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.scatteringTint));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.powderEffectIntensity));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.multiScattering));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_VolumetricClouds.shadowOpacity));
		AddProperty(PhotoModeUtils.GroupTitle("Weather", m_Fog.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.meanFreePath));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.baseHeight));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.maximumHeight));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.maxFogDistance));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.tint));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.albedo));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.depthExtent));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Fog.anisotropy));
		AddProperty(PhotoModeUtils.GroupTitle("Weather", m_Sky.GetType().Name));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.auroraBorealisEmissionMultiplier));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.airMaximumAltitude));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.airDensityR));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.airDensityG));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.airDensityB));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.airTint));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.aerosolMaximumAltitude));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.aerosolDensity));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.aerosolTint));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.aerosolAnisotropy));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.colorSaturation));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.alphaSaturation));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.alphaMultiplier));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.horizonTint));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.horizonZenithShift));
		AddProperty(PhotoModeUtils.BindProperty("Weather", () => m_Sky.zenithTint));
		AddProperty(new PhotoModeProperty
		{
			id = "Time of Day",
			group = "Environment",
			setValue = delegate(float value)
			{
				m_PlanetarySystem.time = value;
				m_PlanetarySystem.overrideTime = true;
				m_PlanetarySystem.Update();
			},
			getValue = () => m_PlanetarySystem.time,
			min = () => 0f,
			max = () => 24f,
			setEnabled = delegate(bool enabled)
			{
				m_PlanetarySystem.overrideTime = enabled;
				m_PlanetarySystem.Update();
			},
			isEnabled = () => m_PlanetarySystem.overrideTime
		});
		AddProperty(new PhotoModeProperty
		{
			id = "Simulation Speed",
			group = "Environment",
			setValue = delegate(float value)
			{
				m_SimulationSystem.selectedSpeed = value;
			},
			getValue = () => m_SimulationSystem.selectedSpeed,
			min = () => 0f,
			max = () => 8f,
			reset = delegate
			{
				m_SimulationSystem.selectedSpeed = 0f;
			}
		});
		AddPreset(PhotoModeUtils.CreatePreset("SensorTypePreset", array[0], array, kApertureFormatNames, kApertureFormatValues));
		float FieldOfViewToFocalLength(float v)
		{
			return Camera.FieldOfViewToFocalLength(v, sensorSize.currentValue.y);
		}
		float FocalLengthToFieldOfView(float v)
		{
			return Mathf.Clamp(Camera.FocalLengthToFieldOfView(Mathf.Max(v, 0.0001f), sensorSize.currentValue.y), 1f, 179f);
		}
		float MaxFieldOfViewToFocalLength()
		{
			return FieldOfViewToFocalLength(179f);
		}
		float MaxFocalLength()
		{
			if (!(MinFieldOfViewToFocalLength() > MaxFieldOfViewToFocalLength()))
			{
				return MaxFieldOfViewToFocalLength();
			}
			return MinFieldOfViewToFocalLength();
		}
		float MinFieldOfViewToFocalLength()
		{
			return FieldOfViewToFocalLength(1f);
		}
		float MinFocalLength()
		{
			if (!(MinFieldOfViewToFocalLength() > MaxFieldOfViewToFocalLength()))
			{
				return MinFieldOfViewToFocalLength();
			}
			return MaxFieldOfViewToFocalLength();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		base.Enabled = false;
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_CameraControlVolume = VolumeHelper.CreateVolume("CinematicControlVolume", 2000);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_ColorAdjustments);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_WhiteBalance);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_PaniniProjection);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_ShadowsMidtonesHighlights);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_Vignette);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_Bloom);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_MotionBlur);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_DepthOfField);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_DistanceClouds);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_VolumetricClouds);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_Fog);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_Sky);
		m_Vignette.mode.Override(VignetteMode.Procedural);
		VolumeHelper.GetOrCreateVolumeComponent(m_CameraControlVolume, ref m_FilmGrain);
		m_CameraControlVolume.weight = 0f;
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		focalLength = new OverridableLensProperty<float>(m_CameraUpdateSystem, delegate(IGameCameraController c, float v)
		{
			c.lens.FieldOfView = v;
		}, (IGameCameraController c) => c.lens.FieldOfView);
		sensorSize = new OverridableLensProperty<Vector2>(m_CameraUpdateSystem, delegate(IGameCameraController c, Vector2 v)
		{
			c.lens.SensorSize = v;
		}, (IGameCameraController c) => c.lens.SensorSize);
		aperture = new OverridableLensProperty<float>(m_CameraUpdateSystem, delegate(IGameCameraController c, float v)
		{
			c.lens.Aperture = v;
		}, (IGameCameraController c) => c.lens.Aperture);
		iso = new OverridableLensProperty<int>(m_CameraUpdateSystem, delegate(IGameCameraController c, int v)
		{
			c.lens.Iso = v;
		}, (IGameCameraController c) => c.lens.Iso);
		shutterSpeed = new OverridableLensProperty<float>(m_CameraUpdateSystem, delegate(IGameCameraController c, float v)
		{
			c.lens.ShutterSpeed = v;
		}, (IGameCameraController c) => c.lens.ShutterSpeed);
		gateFitMode = new OverridableLensProperty<Camera.GateFitMode>(m_CameraUpdateSystem, delegate(IGameCameraController c, Camera.GateFitMode v)
		{
			c.lens.GateFit = v;
		}, (IGameCameraController c) => c.lens.GateFit);
		bladeCount = new OverridableLensProperty<int>(m_CameraUpdateSystem, delegate(IGameCameraController c, int v)
		{
			c.lens.BladeCount = v;
		}, (IGameCameraController c) => c.lens.BladeCount);
		curvature = new OverridableLensProperty<Vector2>(m_CameraUpdateSystem, delegate(IGameCameraController c, Vector2 v)
		{
			c.lens.Curvature = v;
		}, (IGameCameraController c) => c.lens.Curvature);
		barrelClipping = new OverridableLensProperty<float>(m_CameraUpdateSystem, delegate(IGameCameraController c, float v)
		{
			c.lens.BarrelClipping = v;
		}, (IGameCameraController c) => c.lens.BarrelClipping);
		anamorphism = new OverridableLensProperty<float>(m_CameraUpdateSystem, delegate(IGameCameraController c, float v)
		{
			c.lens.Anamorphism = v;
		}, (IGameCameraController c) => c.lens.Anamorphism);
		focusDistance = new OverridableLensProperty<float>(m_CameraUpdateSystem, delegate(IGameCameraController c, float v)
		{
			c.lens.FocusDistance = v;
		}, (IGameCameraController c) => c.lens.FocusDistance);
		lensShift = new OverridableLensProperty<Vector2>(m_CameraUpdateSystem, delegate(IGameCameraController c, Vector2 v)
		{
			c.lens.LensShift = v;
		}, (IGameCameraController c) => c.lens.LensShift);
		InitializeProperties();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		VolumeHelper.DestroyVolume(m_CameraControlVolume);
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		focalLength.Sync();
		sensorSize.Sync();
		aperture.Sync();
		iso.Sync();
		shutterSpeed.Sync();
		gateFitMode.Sync();
		bladeCount.Sync();
		curvature.Sync();
		barrelClipping.Sync();
		anamorphism.Sync();
		focusDistance.Sync();
		lensShift.Sync();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		float weight;
		CameraBlend blendWeight = m_CameraUpdateSystem.GetBlendWeight(out weight);
		if (blendWeight == CameraBlend.ToCinematicCamera)
		{
			m_CameraControlVolume.weight = weight;
		}
		if (blendWeight == CameraBlend.FromCinematicCamera)
		{
			m_CameraControlVolume.weight = 1f - weight;
		}
		if (blendWeight == CameraBlend.None)
		{
			if (m_Active)
			{
				m_CameraControlVolume.weight = 1f;
				return;
			}
			m_CameraControlVolume.weight = 0f;
			base.Enabled = false;
		}
	}
```


## Nested types

- `Game.Rendering.PhotoModeRenderSystem+<>c`  


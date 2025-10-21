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
public PhotoModeRenderSystem();
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
private System.Void AddPreset(Game.UI.InGame.PhotoModeUIPreset preset);
```

- `public AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.Void`  

```csharp
public System.Void AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty property);
```

- `public AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty[] property) : System.Void`  

```csharp
public System.Void AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty[] property);
```

- `public DisableAllCameraProperties() : System.Void`  

```csharp
public System.Void DisableAllCameraProperties();
```

- `public Enable(System.Boolean enabled) : System.Void`  

```csharp
public System.Void Enable(System.Boolean enabled);
```

- `private InitializeProperties() : System.Void`  

```csharp
private System.Void InitializeProperties();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Rendering.PhotoModeRenderSystem+<>c`  


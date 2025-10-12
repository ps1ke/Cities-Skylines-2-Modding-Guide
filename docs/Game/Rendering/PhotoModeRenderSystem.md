# Game.Rendering.PhotoModeRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private UnityEngine.Rendering.Volume m_CameraControlVolume`  
- `private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments`  
- `private UnityEngine.Rendering.HighDefinition.WhiteBalance m_WhiteBalance`  
- `private UnityEngine.Rendering.HighDefinition.PaniniProjection m_PaniniProjection`  
- `private UnityEngine.Rendering.HighDefinition.Vignette m_Vignette`  
- `private UnityEngine.Rendering.HighDefinition.FilmGrain m_FilmGrain`  
- `private UnityEngine.Rendering.HighDefinition.ShadowsMidtonesHighlights m_ShadowsMidtonesHighlights`  
- `private UnityEngine.Rendering.HighDefinition.Bloom m_Bloom`  
- `private UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlur`  
- `private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField`  
- `private UnityEngine.Rendering.HighDefinition.CloudLayer m_DistanceClouds`  
- `private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds`  
- `private UnityEngine.Rendering.HighDefinition.Fog m_Fog`  
- `private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_Sky`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focalLength`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> sensorSize`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> aperture`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> iso`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> shutterSpeed`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Camera+GateFitMode> gateFitMode`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32> bladeCount`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> curvature`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> barrelClipping`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> anamorphism`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single> focusDistance`  
- `private Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2> lensShift`  
- `private System.Boolean m_Active`  
- `private Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> <photoModeProperties>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUIPreset> m_Presets`  
- `private static readonly System.String[] kApertureFormatNames`  
- `private static readonly UnityEngine.Vector2[] kApertureFormatValues`  
- `private static const System.String kSensorTypePreset`  
- `private static const System.String kCameraApertureShape`  
- `private static const System.String kCameraBody`  
- `private static const System.String kCameraLens`  
- `private static const System.String kCamera`  
- `private static const System.String kColorGrading`  
- `private static const System.String kLens`  
- `private static const System.String kWeather`  
- `private static const System.String kEnvironment`  

## Properties

- `public Colossal.Collections.Generic.OrderedDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> photoModeProperties { get; private set }`  
- `public System.Collections.Generic.IReadOnlyCollection<Game.UI.InGame.PhotoModeUIPreset> presets { get }`  

## Constructors

- `public PhotoModeRenderSystem()`  

## Methods

- `private <InitializeProperties>b__56_111(System.Single value) : System.Void`  
- `private <InitializeProperties>b__56_112() : System.Single`  
- `private <InitializeProperties>b__56_113() : System.Void`  
- `private <InitializeProperties>b__56_114(System.Single value) : System.Void`  
- `private <InitializeProperties>b__56_115() : System.Single`  
- `private <InitializeProperties>b__56_118() : System.Void`  
- `private <InitializeProperties>b__56_119(System.Single value) : System.Void`  
- `private <InitializeProperties>b__56_120() : System.Single`  
- `private <InitializeProperties>b__56_123(System.Boolean enabled) : System.Void`  
- `private <InitializeProperties>b__56_124() : System.Boolean`  
- `private <InitializeProperties>b__56_125(System.Single value) : System.Void`  
- `private <InitializeProperties>b__56_126() : System.Single`  
- `private <InitializeProperties>b__56_129() : System.Void`  
- `private <InitializeProperties>b__56_19() : System.Boolean`  
- `private <InitializeProperties>b__56_21() : System.Boolean`  
- `private <InitializeProperties>b__56_23() : System.Boolean`  
- `private <InitializeProperties>b__56_25() : System.Boolean`  
- `private <InitializeProperties>b__56_27() : System.Boolean`  
- `private <InitializeProperties>b__56_29() : System.Boolean`  
- `private <InitializeProperties>b__56_31() : System.Boolean`  
- `private <InitializeProperties>g__FieldOfViewToFocalLength|56_1(System.Single v) : System.Single`  
- `private <InitializeProperties>g__FocalLengthToFieldOfView|56_0(System.Single v) : System.Single`  
- `private <InitializeProperties>g__MaxFieldOfViewToFocalLength|56_3() : System.Single`  
- `private <InitializeProperties>g__MaxFocalLength|56_5() : System.Single`  
- `private <InitializeProperties>g__MinFieldOfViewToFocalLength|56_2() : System.Single`  
- `private <InitializeProperties>g__MinFocalLength|56_4() : System.Single`  
- `private AddPreset(Game.UI.InGame.PhotoModeUIPreset preset) : System.Void`  
- `public AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.Void`  
- `public AddProperty(Game.Rendering.CinematicCamera.PhotoModeProperty[] property) : System.Void`  
- `public DisableAllCameraProperties() : System.Void`  
- `public Enable(System.Boolean enabled) : System.Void`  
- `private InitializeProperties() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.PhotoModeRenderSystem+<>c`  


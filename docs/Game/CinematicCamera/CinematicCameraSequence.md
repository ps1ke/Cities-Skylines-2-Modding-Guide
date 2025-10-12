# Game.CinematicCamera.CinematicCameraSequence

**Assembly:** `Game`  
**Namespace:** `Game.CinematicCamera`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`  

## Fields

- `private System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> <modifiers>k__BackingField`  
- `private Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] <transforms>k__BackingField`  
- `private System.Single <playbackDuration>k__BackingField`  
- `private System.Boolean m_Loop`  

## Properties

- `public System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> modifiers { get; set }`  
- `public Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] transforms { get; set }`  
- `public System.Single playbackDuration { get; set }`  
- `public System.Boolean loop { get; set }`  
- `public System.Single timelineLength { get }`  
- `public System.Int32 transformCount { get }`  

## Constructors

- `public CinematicCameraSequence()`  

## Methods

- `public AddCameraTransform(System.Single t, UnityEngine.Vector3 position, UnityEngine.Vector3 rotation) : System.Int32`  
- `public AddModifierKey(System.String id, System.Single t, System.Single value, System.Single min, System.Single max) : System.Int32`  
- `public AddModifierKey(System.String id, System.Single t, System.Single value) : System.Int32`  
- `public AfterModifications(System.Boolean rotationsChanged = False) : System.Void`  
- `private EnsureLoop() : System.Boolean`  
- `private EnsureLoop(UnityEngine.AnimationCurve curve) : System.Boolean`  
- `public MoveKeyframe(Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier modifier, System.Int32 index, UnityEngine.Keyframe keyframe) : System.Int32`  
- `private PatchRotations() : System.Void`  
- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  
- `public Refresh(System.Single t, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> properties, Game.Rendering.IGameCameraController controller) : System.Void`  
- `public RemoveCameraTransform(System.Int32 curveIndex, System.Int32 index) : System.Void`  
- `public RemoveModifier(System.String id) : System.Void`  
- `public RemoveModifierKey(System.String id, System.Int32 idx) : System.Void`  
- `public Reset() : System.Void`  
- `public SampleTransform(Game.Rendering.IGameCameraController controller, System.Single t, UnityEngine.Vector3& position, UnityEngine.Vector3& rotation) : System.Boolean`  
- `private static SupportValueTypesForAOT() : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.CinematicCamera.CinematicCameraSequence+TransformCurveKey`  
- `Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass21_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass26_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass27_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass28_0`  


# Game.CinematicCamera.CinematicCameraSequence

**Assembly:** `Game`  
**Namespace:** `Game.CinematicCamera`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`  

## Code

```csharp
public class CinematicCameraSequence : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable
{
    private System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> <modifiers>k__BackingField;
    private Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] <transforms>k__BackingField;
    private System.Single <playbackDuration>k__BackingField;
    private System.Boolean m_Loop;

    public System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> modifiers { get; set; }
    public Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] transforms { get; set; }
    public System.Single playbackDuration { get; set; }
    public System.Boolean loop { get; set; }
    public System.Single timelineLength { get; }
    public System.Int32 transformCount { get; }

    public CinematicCameraSequence();

    public System.Int32 AddCameraTransform(System.Single t, UnityEngine.Vector3 position, UnityEngine.Vector3 rotation);
    public System.Int32 AddModifierKey(System.String id, System.Single t, System.Single value, System.Single min, System.Single max);
    public System.Int32 AddModifierKey(System.String id, System.Single t, System.Single value);
    public System.Void AfterModifications(System.Boolean rotationsChanged);
    private System.Boolean EnsureLoop();
    private System.Boolean EnsureLoop(UnityEngine.AnimationCurve curve);
    public System.Int32 MoveKeyframe(Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier modifier, System.Int32 index, UnityEngine.Keyframe keyframe);
    private System.Void PatchRotations();
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Refresh(System.Single t, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> properties, Game.Rendering.IGameCameraController controller);
    public System.Void RemoveCameraTransform(System.Int32 curveIndex, System.Int32 index);
    public System.Void RemoveModifier(System.String id);
    public System.Void RemoveModifierKey(System.String id, System.Int32 idx);
    public System.Void Reset();
    public System.Boolean SampleTransform(Game.Rendering.IGameCameraController controller, System.Single t, UnityEngine.Vector3& position, UnityEngine.Vector3& rotation);
    private static System.Void SupportValueTypesForAOT();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> <modifiers>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> <modifiers>k__BackingField;
```

- `private Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] <transforms>k__BackingField`  

```csharp
private Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] <transforms>k__BackingField;
```

- `private System.Single <playbackDuration>k__BackingField`  

```csharp
private System.Single <playbackDuration>k__BackingField;
```

- `private System.Boolean m_Loop`  

```csharp
private System.Boolean m_Loop;
```


## Properties

- `public System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> modifiers { get; set }`  

```csharp
public System.Collections.Generic.List<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier> modifiers { get; set; }
```

- `public Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] transforms { get; set }`  

```csharp
public Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] transforms { get; set; }
```

- `public System.Single playbackDuration { get; set }`  

```csharp
public System.Single playbackDuration { get; set; }
```

- `public System.Boolean loop { get; set }`  

```csharp
public System.Boolean loop { get; set; }
```

- `public System.Single timelineLength { get }`  

```csharp
public System.Single timelineLength { get; }
```

- `public System.Int32 transformCount { get }`  

```csharp
public System.Int32 transformCount { get; }
```


## Constructors

- `public CinematicCameraSequence()`  

```csharp
public CinematicCameraSequence();
```


## Methods

- `public AddCameraTransform(System.Single t, UnityEngine.Vector3 position, UnityEngine.Vector3 rotation) : System.Int32`  

```csharp
public System.Int32 AddCameraTransform(System.Single t, UnityEngine.Vector3 position, UnityEngine.Vector3 rotation);
```

- `public AddModifierKey(System.String id, System.Single t, System.Single value, System.Single min, System.Single max) : System.Int32`  

```csharp
public System.Int32 AddModifierKey(System.String id, System.Single t, System.Single value, System.Single min, System.Single max);
```

- `public AddModifierKey(System.String id, System.Single t, System.Single value) : System.Int32`  

```csharp
public System.Int32 AddModifierKey(System.String id, System.Single t, System.Single value);
```

- `public AfterModifications(System.Boolean rotationsChanged = False) : System.Void`  

```csharp
public System.Void AfterModifications(System.Boolean rotationsChanged);
```

- `private EnsureLoop() : System.Boolean`  

```csharp
private System.Boolean EnsureLoop();
```

- `private EnsureLoop(UnityEngine.AnimationCurve curve) : System.Boolean`  

```csharp
private System.Boolean EnsureLoop(UnityEngine.AnimationCurve curve);
```

- `public MoveKeyframe(Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier modifier, System.Int32 index, UnityEngine.Keyframe keyframe) : System.Int32`  

```csharp
public System.Int32 MoveKeyframe(Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier modifier, System.Int32 index, UnityEngine.Keyframe keyframe);
```

- `private PatchRotations() : System.Void`  

```csharp
private System.Void PatchRotations();
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `public Refresh(System.Single t, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> properties, Game.Rendering.IGameCameraController controller) : System.Void`  

```csharp
public System.Void Refresh(System.Single t, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> properties, Game.Rendering.IGameCameraController controller);
```

- `public RemoveCameraTransform(System.Int32 curveIndex, System.Int32 index) : System.Void`  

```csharp
public System.Void RemoveCameraTransform(System.Int32 curveIndex, System.Int32 index);
```

- `public RemoveModifier(System.String id) : System.Void`  

```csharp
public System.Void RemoveModifier(System.String id);
```

- `public RemoveModifierKey(System.String id, System.Int32 idx) : System.Void`  

```csharp
public System.Void RemoveModifierKey(System.String id, System.Int32 idx);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public SampleTransform(Game.Rendering.IGameCameraController controller, System.Single t, UnityEngine.Vector3& position, UnityEngine.Vector3& rotation) : System.Boolean`  

```csharp
public System.Boolean SampleTransform(Game.Rendering.IGameCameraController controller, System.Single t, UnityEngine.Vector3& position, UnityEngine.Vector3& rotation);
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static System.Void SupportValueTypesForAOT();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.CinematicCamera.CinematicCameraSequence+TransformCurveKey`  
- `Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass21_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass26_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass27_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass28_0`  


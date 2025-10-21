# Game.UI.InGame.CinematicCameraUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CinematicCameraUISystem : Game.UI.UISystemBase
{
    private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
    private Game.Tutorials.TutorialUITriggerSystem m_TutorialUITriggerSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Colossal.UI.Binding.GetterValueBinding<Game.Assets.CinematicCameraAsset[]> m_Assets;
    private Colossal.UI.Binding.ValueBinding<Game.Assets.CinematicCameraAsset> m_LastLoaded;
    private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_TransformAnimationCurveBinding;
    private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_ModifierAnimationCurveBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding;
    private Game.CinematicCamera.CinematicCameraSequence <activeSequence>k__BackingField;
    private Game.CinematicCamera.CinematicCameraSequence m_ActiveAutoplaySequence;
    private Game.Rendering.IGameCameraController m_PreviousController;
    private Game.Input.ProxyAction m_MoveAction;
    private Game.Input.ProxyAction m_ZoomAction;
    private Game.Input.ProxyAction m_RotateAction;
    private System.Single <t>k__BackingField;
    private System.Boolean m_Playing;
    private static readonly System.String kGroup;
    private static readonly Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] kEmptyModifierArray;
    private static readonly System.String kCaptureKeyframeTutorialTag;

    public Game.CinematicCamera.CinematicCameraSequence activeSequence { get; set; }
    private System.Single m_TimelinePositionBindingValue { private get; }
    private System.Single t { private get; private set; }
    private System.Boolean playing { private get; private set; }

    public CinematicCameraUISystem();

    private System.Void <OnAssetsChanged>b__46_0();
    private System.Void <OnCloudTargetsChanged>b__47_0();
    private System.Boolean <OnCreate>b__31_0();
    private System.Single <OnCreate>b__31_1();
    private System.Void <OnCreate>b__31_2();
    private System.Single <OnCreate>b__31_3();
    private System.Single <OnCreate>b__31_4();
    private System.Boolean <OnCreate>b__31_5();
    public System.Void Autoplay(Game.Assets.CinematicCameraAsset sequence);
    private System.Void Delete(System.String hash, System.String storage);
    private System.Single[] GetControllerDelta();
    private System.Single[] GetControllerPanDelta();
    private System.Single GetControllerZoomDelta();
    private System.Void GetData(System.String id, Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]& modifiers, Colossal.UI.Binding.ValueBinding`1[[Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[], Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& binding);
    private Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] GetTransformCurves();
    private System.Void Load(System.String hash, System.String storage);
    private System.Int32 OnAddKeyFrame(System.String id, System.Single time, System.Single value, System.Int32 curveIndex);
    private System.Void OnAssetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    private System.Void OnCapture(System.String id, System.String property);
    private System.Void OnCaptureTransform();
    private System.Void OnCloudTargetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    protected virtual System.Void OnCreate();
    private System.Void OnCurveEditorFocusChange(System.Boolean focused);
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Int32 OnMoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index, UnityEngine.Keyframe keyframe);
    private System.Void OnRemoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index);
    private System.Void OnRemoveSelectedTransform(System.Int32 curveIndex, System.Int32 index);
    private System.Void OnSetPlaybackDuration(System.Single duration);
    private System.Void OnSetTimelinePosition(System.Single position);
    private System.Void OnToggleLoop(System.Boolean loop);
    protected virtual System.Void OnUpdate();
    private System.Void PausePlayback();
    private System.Void Reset();
    private System.Void Save(System.String name, System.String hash);
    public System.Void StopAutoplay();
    private System.Void StopPlayback();
    public System.Void ToggleModifier(Game.Rendering.CinematicCamera.PhotoModeProperty p);
    private System.Void TogglePlayback();
    private Game.Assets.CinematicCameraAsset[] UpdateAssets();
    private System.Void UpdatePlayback();
}
```


## Fields

- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  

```csharp
private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
```

- `private Game.Tutorials.TutorialUITriggerSystem m_TutorialUITriggerSystem`  

```csharp
private Game.Tutorials.TutorialUITriggerSystem m_TutorialUITriggerSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Assets.CinematicCameraAsset[]> m_Assets`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Assets.CinematicCameraAsset[]> m_Assets;
```

- `private Colossal.UI.Binding.ValueBinding<Game.Assets.CinematicCameraAsset> m_LastLoaded`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.Assets.CinematicCameraAsset> m_LastLoaded;
```

- `private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_TransformAnimationCurveBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_TransformAnimationCurveBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_ModifierAnimationCurveBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_ModifierAnimationCurveBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding;
```

- `private Game.CinematicCamera.CinematicCameraSequence <activeSequence>k__BackingField`  

```csharp
private Game.CinematicCamera.CinematicCameraSequence <activeSequence>k__BackingField;
```

- `private Game.CinematicCamera.CinematicCameraSequence m_ActiveAutoplaySequence`  

```csharp
private Game.CinematicCamera.CinematicCameraSequence m_ActiveAutoplaySequence;
```

- `private Game.Rendering.IGameCameraController m_PreviousController`  

```csharp
private Game.Rendering.IGameCameraController m_PreviousController;
```

- `private Game.Input.ProxyAction m_MoveAction`  

```csharp
private Game.Input.ProxyAction m_MoveAction;
```

- `private Game.Input.ProxyAction m_ZoomAction`  

```csharp
private Game.Input.ProxyAction m_ZoomAction;
```

- `private Game.Input.ProxyAction m_RotateAction`  

```csharp
private Game.Input.ProxyAction m_RotateAction;
```

- `private System.Single <t>k__BackingField`  

```csharp
private System.Single <t>k__BackingField;
```

- `private System.Boolean m_Playing`  

```csharp
private System.Boolean m_Playing;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```

- `private static readonly Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] kEmptyModifierArray`  

```csharp
private static readonly Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] kEmptyModifierArray;
```

- `private static readonly System.String kCaptureKeyframeTutorialTag`  

```csharp
private static readonly System.String kCaptureKeyframeTutorialTag;
```


## Properties

- `public Game.CinematicCamera.CinematicCameraSequence activeSequence { get; set }`  

```csharp
public Game.CinematicCamera.CinematicCameraSequence activeSequence { get; set; }
```

- `private System.Single m_TimelinePositionBindingValue { private get }`  

```csharp
private System.Single m_TimelinePositionBindingValue { private get; }
```

- `private System.Single t { private get; private set }`  

```csharp
private System.Single t { private get; private set; }
```

- `private System.Boolean playing { private get; private set }`  

```csharp
private System.Boolean playing { private get; private set; }
```


## Constructors

- `public CinematicCameraUISystem()`  

```csharp
public CinematicCameraUISystem();
```


## Methods

- `private <OnAssetsChanged>b__46_0() : System.Void`  

```csharp
private System.Void <OnAssetsChanged>b__46_0();
```

- `private <OnCloudTargetsChanged>b__47_0() : System.Void`  

```csharp
private System.Void <OnCloudTargetsChanged>b__47_0();
```

- `private <OnCreate>b__31_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__31_0();
```

- `private <OnCreate>b__31_1() : System.Single`  

```csharp
private System.Single <OnCreate>b__31_1();
```

- `private <OnCreate>b__31_2() : System.Void`  

```csharp
private System.Void <OnCreate>b__31_2();
```

- `private <OnCreate>b__31_3() : System.Single`  

```csharp
private System.Single <OnCreate>b__31_3();
```

- `private <OnCreate>b__31_4() : System.Single`  

```csharp
private System.Single <OnCreate>b__31_4();
```

- `private <OnCreate>b__31_5() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__31_5();
```

- `public Autoplay(Game.Assets.CinematicCameraAsset sequence) : System.Void`  

```csharp
public System.Void Autoplay(Game.Assets.CinematicCameraAsset sequence);
```

- `private Delete(System.String hash, System.String storage) : System.Void`  

```csharp
private System.Void Delete(System.String hash, System.String storage);
```

- `private GetControllerDelta() : System.Single[]`  

```csharp
private System.Single[] GetControllerDelta();
```

- `private GetControllerPanDelta() : System.Single[]`  

```csharp
private System.Single[] GetControllerPanDelta();
```

- `private GetControllerZoomDelta() : System.Single`  

```csharp
private System.Single GetControllerZoomDelta();
```

- `private GetData(System.String id, Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]& modifiers, Colossal.UI.Binding.ValueBinding`1[[Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[], Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& binding) : System.Void`  

```csharp
private System.Void GetData(System.String id, Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]& modifiers, Colossal.UI.Binding.ValueBinding`1[[Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[], Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& binding);
```

- `private GetTransformCurves() : Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]`  

```csharp
private Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] GetTransformCurves();
```

- `private Load(System.String hash, System.String storage) : System.Void`  

```csharp
private System.Void Load(System.String hash, System.String storage);
```

- `private OnAddKeyFrame(System.String id, System.Single time, System.Single value, System.Int32 curveIndex) : System.Int32`  

```csharp
private System.Int32 OnAddKeyFrame(System.String id, System.Single time, System.Single value, System.Int32 curveIndex);
```

- `private OnAssetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void OnAssetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `private OnCapture(System.String id, System.String property) : System.Void`  

```csharp
private System.Void OnCapture(System.String id, System.String property);
```

- `private OnCaptureTransform() : System.Void`  

```csharp
private System.Void OnCaptureTransform();
```

- `private OnCloudTargetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void OnCloudTargetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `private OnCurveEditorFocusChange(System.Boolean focused) : System.Void`  

```csharp
private System.Void OnCurveEditorFocusChange(System.Boolean focused);
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnMoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index, UnityEngine.Keyframe keyframe) : System.Int32`  

```csharp
private System.Int32 OnMoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index, UnityEngine.Keyframe keyframe);
```

- `private OnRemoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index) : System.Void`  

```csharp
private System.Void OnRemoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index);
```

- `private OnRemoveSelectedTransform(System.Int32 curveIndex, System.Int32 index) : System.Void`  

```csharp
private System.Void OnRemoveSelectedTransform(System.Int32 curveIndex, System.Int32 index);
```

- `private OnSetPlaybackDuration(System.Single duration) : System.Void`  

```csharp
private System.Void OnSetPlaybackDuration(System.Single duration);
```

- `private OnSetTimelinePosition(System.Single position) : System.Void`  

```csharp
private System.Void OnSetTimelinePosition(System.Single position);
```

- `private OnToggleLoop(System.Boolean loop) : System.Void`  

```csharp
private System.Void OnToggleLoop(System.Boolean loop);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PausePlayback() : System.Void`  

```csharp
private System.Void PausePlayback();
```

- `private Reset() : System.Void`  

```csharp
private System.Void Reset();
```

- `private Save(System.String name, System.String hash = null) : System.Void`  

```csharp
private System.Void Save(System.String name, System.String hash);
```

- `public StopAutoplay() : System.Void`  

```csharp
public System.Void StopAutoplay();
```

- `private StopPlayback() : System.Void`  

```csharp
private System.Void StopPlayback();
```

- `public ToggleModifier(Game.Rendering.CinematicCamera.PhotoModeProperty p) : System.Void`  

```csharp
public System.Void ToggleModifier(Game.Rendering.CinematicCamera.PhotoModeProperty p);
```

- `private TogglePlayback() : System.Void`  

```csharp
private System.Void TogglePlayback();
```

- `private UpdateAssets() : Game.Assets.CinematicCameraAsset[]`  

```csharp
private Game.Assets.CinematicCameraAsset[] UpdateAssets();
```

- `private UpdatePlayback() : System.Void`  

```csharp
private System.Void UpdatePlayback();
```


## Nested types

- `Game.UI.InGame.CinematicCameraUISystem+<>c`  


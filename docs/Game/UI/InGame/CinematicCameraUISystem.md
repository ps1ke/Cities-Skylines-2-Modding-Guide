# Game.UI.InGame.CinematicCameraUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  
- `private Game.Tutorials.TutorialUITriggerSystem m_TutorialUITriggerSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.Assets.CinematicCameraAsset[]> m_Assets`  
- `private Colossal.UI.Binding.ValueBinding<Game.Assets.CinematicCameraAsset> m_LastLoaded`  
- `private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_TransformAnimationCurveBinding`  
- `private Colossal.UI.Binding.ValueBinding<Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]> m_ModifierAnimationCurveBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<System.String>> m_AvailableCloudTargetsBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_SelectedCloudTargetBinding`  
- `private Game.CinematicCamera.CinematicCameraSequence <activeSequence>k__BackingField`  
- `private Game.CinematicCamera.CinematicCameraSequence m_ActiveAutoplaySequence`  
- `private Game.Rendering.IGameCameraController m_PreviousController`  
- `private Game.Input.ProxyAction m_MoveAction`  
- `private Game.Input.ProxyAction m_ZoomAction`  
- `private Game.Input.ProxyAction m_RotateAction`  
- `private System.Single <t>k__BackingField`  
- `private System.Boolean m_Playing`  
- `private static readonly System.String kGroup`  
- `private static readonly Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[] kEmptyModifierArray`  
- `private static readonly System.String kCaptureKeyframeTutorialTag`  

## Properties

- `public Game.CinematicCamera.CinematicCameraSequence activeSequence { get; set }`  
- `private System.Single m_TimelinePositionBindingValue { private get }`  
- `private System.Single t { private get; private set }`  
- `private System.Boolean playing { private get; private set }`  

## Constructors

- `public CinematicCameraUISystem()`  

## Methods

- `private <OnAssetsChanged>b__46_0() : System.Void`  
- `private <OnCloudTargetsChanged>b__47_0() : System.Void`  
- `private <OnCreate>b__31_0() : System.Boolean`  
- `private <OnCreate>b__31_1() : System.Single`  
- `private <OnCreate>b__31_2() : System.Void`  
- `private <OnCreate>b__31_3() : System.Single`  
- `private <OnCreate>b__31_4() : System.Single`  
- `private <OnCreate>b__31_5() : System.Boolean`  
- `public Autoplay(Game.Assets.CinematicCameraAsset sequence) : System.Void`  
- `private Delete(System.String hash, System.String storage) : System.Void`  
- `private GetControllerDelta() : System.Single[]`  
- `private GetControllerPanDelta() : System.Single[]`  
- `private GetControllerZoomDelta() : System.Single`  
- `private GetData(System.String id, Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]& modifiers, Colossal.UI.Binding.ValueBinding`1[[Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[], Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& binding) : System.Void`  
- `private GetTransformCurves() : Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]`  
- `private Load(System.String hash, System.String storage) : System.Void`  
- `private OnAddKeyFrame(System.String id, System.Single time, System.Single value, System.Int32 curveIndex) : System.Int32`  
- `private OnAssetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `private OnCapture(System.String id, System.String property) : System.Void`  
- `private OnCaptureTransform() : System.Void`  
- `private OnCloudTargetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `private OnCurveEditorFocusChange(System.Boolean focused) : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnMoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index, UnityEngine.Keyframe keyframe) : System.Int32`  
- `private OnRemoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index) : System.Void`  
- `private OnRemoveSelectedTransform(System.Int32 curveIndex, System.Int32 index) : System.Void`  
- `private OnSetPlaybackDuration(System.Single duration) : System.Void`  
- `private OnSetTimelinePosition(System.Single position) : System.Void`  
- `private OnToggleLoop(System.Boolean loop) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PausePlayback() : System.Void`  
- `private Reset() : System.Void`  
- `private Save(System.String name, System.String hash = null) : System.Void`  
- `public StopAutoplay() : System.Void`  
- `private StopPlayback() : System.Void`  
- `public ToggleModifier(Game.Rendering.CinematicCamera.PhotoModeProperty p) : System.Void`  
- `private TogglePlayback() : System.Void`  
- `private UpdateAssets() : Game.Assets.CinematicCameraAsset[]`  
- `private UpdatePlayback() : System.Void`  

## Nested types

- `Game.UI.InGame.CinematicCameraUISystem+<>c`  


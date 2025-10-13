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
[Preserve]
	public CinematicCameraUISystem()
	{
	}
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
public void Autoplay(CinematicCameraAsset sequence)
	{
		m_ActiveAutoplaySequence = sequence.target;
		m_ActiveAutoplaySequence.loop = true;
		t = 0f;
		playing = true;
	}
```

- `private Delete(System.String hash, System.String storage) : System.Void`  

```csharp
private void Delete(string hash, string storage)
	{
		Colossal.Hash128 guid = new Colossal.Hash128(hash);
		MenuHelpers.GetSanitizedCloudTarget(storage).db.DeleteAsset(guid);
		m_Assets.Update();
	}
```

- `private GetControllerDelta() : System.Single[]`  

```csharp
private float[] GetControllerDelta()
	{
		Vector2 vector = m_MoveAction.ReadValue<Vector2>() * UnityEngine.Time.deltaTime;
		return new float[2] { vector.x, vector.y };
	}
```

- `private GetControllerPanDelta() : System.Single[]`  

```csharp
private float[] GetControllerPanDelta()
	{
		Vector2 vector = m_RotateAction.ReadValue<Vector2>() * UnityEngine.Time.deltaTime;
		return new float[2] { vector.x, vector.y };
	}
```

- `private GetControllerZoomDelta() : System.Single`  

```csharp
private float GetControllerZoomDelta()
	{
		return m_ZoomAction.ReadValue<float>() * UnityEngine.Time.deltaTime;
	}
```

- `private GetData(System.String id, Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]& modifiers, Colossal.UI.Binding.ValueBinding`1[[Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[], Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& binding) : System.Void`  

```csharp
private void GetData(string id, out CinematicCameraSequence.CinematicCameraCurveModifier[] modifiers, out ValueBinding<CinematicCameraSequence.CinematicCameraCurveModifier[]> binding)
	{
		if (id == "Position")
		{
			modifiers = activeSequence.transforms.ToArray();
			binding = m_TransformAnimationCurveBinding;
		}
		else
		{
			modifiers = activeSequence.modifiers.ToArray();
			binding = m_ModifierAnimationCurveBinding;
		}
	}
```

- `private GetTransformCurves() : Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier[]`  

```csharp
private CinematicCameraSequence.CinematicCameraCurveModifier[] GetTransformCurves()
	{
		if (activeSequence.transformCount > 0)
		{
			List<CinematicCameraSequence.CinematicCameraCurveModifier> list = new List<CinematicCameraSequence.CinematicCameraCurveModifier>();
			CinematicCameraSequence.CinematicCameraCurveModifier[] transforms = activeSequence.transforms;
			for (int i = 0; i < transforms.Length; i++)
			{
				CinematicCameraSequence.CinematicCameraCurveModifier item = transforms[i];
				if (item.curve != null)
				{
					list.Add(item);
				}
			}
			return list.ToArray();
		}
		return kEmptyModifierArray;
	}
```

- `private Load(System.String hash, System.String storage) : System.Void`  

```csharp
private void Load(string hash, string storage)
	{
		Colossal.Hash128 guid = new Colossal.Hash128(hash);
		CinematicCameraAsset asset = MenuHelpers.GetSanitizedCloudTarget(storage).db.GetAsset<CinematicCameraAsset>(guid);
		if (asset != null)
		{
			asset.Load();
			if (asset.target != null)
			{
				activeSequence = asset.target;
				m_LastLoaded.Update(asset);
				m_TransformAnimationCurveBinding.Update(GetTransformCurves());
				m_ModifierAnimationCurveBinding.Update(activeSequence.modifiers.ToArray());
			}
		}
	}
```

- `private OnAddKeyFrame(System.String id, System.Single time, System.Single value, System.Int32 curveIndex) : System.Int32`  

```csharp
private int OnAddKeyFrame(string id, float time, float value, int curveIndex)
	{
		if (id == "Property")
		{
			CinematicCameraSequence.CinematicCameraCurveModifier cinematicCameraCurveModifier = activeSequence.modifiers[curveIndex];
			string id2 = cinematicCameraCurveModifier.id;
			int result = activeSequence.AddModifierKey(id2, time, value, cinematicCameraCurveModifier.min, cinematicCameraCurveModifier.max);
			m_ModifierAnimationCurveBinding.Update(activeSequence.modifiers.ToArray());
			return result;
		}
		int result2 = activeSequence.transforms[curveIndex].curve.AddKey(time, value);
		m_TransformAnimationCurveBinding.Update(GetTransformCurves());
		return result2;
	}
```

- `private OnAssetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private void OnAssetsChanged(AssetChangedEventArgs args)
	{
		GameManager.instance.RunOnMainThread(delegate
		{
			m_Assets.Update();
		});
	}
```

- `private OnCapture(System.String id, System.String property) : System.Void`  

```csharp
private void OnCapture(string id, string property)
	{
		if (id == "Property")
		{
			foreach (PhotoModeProperty value in m_PhotoModeRenderSystem.photoModeProperties.Values)
			{
				if (PhotoModeUtils.ExtractPropertyID(value) == property)
				{
					ToggleModifier(value);
					break;
				}
			}
			return;
		}
		OnCaptureTransform();
	}
```

- `private OnCaptureTransform() : System.Void`  

```csharp
private void OnCaptureTransform()
	{
		m_TutorialUITriggerSystem.ActivateTrigger(kCaptureKeyframeTutorialTag);
		Vector3 position = m_CameraUpdateSystem.activeCameraController.position;
		Vector3 rotation = m_CameraUpdateSystem.activeCameraController.rotation;
		activeSequence.AddCameraTransform(t, position, rotation);
		m_TransformAnimationCurveBinding.Update(GetTransformCurves());
	}
```

- `private OnCloudTargetsChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private void OnCloudTargetsChanged(AssetChangedEventArgs args)
	{
		GameManager.instance.RunOnMainThread(delegate
		{
			m_AvailableCloudTargetsBinding.Update();
			m_SelectedCloudTargetBinding.Update();
		});
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddBinding(new TriggerBinding<float>(kGroup, "setPlaybackDuration", OnSetPlaybackDuration));
		AddBinding(new TriggerBinding<float>(kGroup, "setTimelinePosition", OnSetTimelinePosition));
		AddBinding(new TriggerBinding(kGroup, "togglePlayback", TogglePlayback));
		AddBinding(new TriggerBinding(kGroup, "stopPlayback", StopPlayback));
		AddBinding(new TriggerBinding<string, string>(kGroup, "captureKey", OnCapture));
		AddBinding(new TriggerBinding<int, int>(kGroup, "removeCameraTransformKey", OnRemoveSelectedTransform));
		AddBinding(new CallBinding<string, int, int, Keyframe, int>(kGroup, "moveKeyFrame", OnMoveKeyFrame));
		AddBinding(new TriggerBinding<string, int, int>(kGroup, "removeKeyFrame", OnRemoveKeyFrame));
		AddBinding(new CallBinding<string, float, float, int, int>(kGroup, "addKeyFrame", OnAddKeyFrame));
		AddBinding(new TriggerBinding(kGroup, "reset", Reset));
		AddUpdateBinding(new GetterValueBinding<bool>(kGroup, "loop", () => activeSequence.loop));
		AddBinding(new TriggerBinding<bool>(kGroup, "toggleLoop", OnToggleLoop));
		AddBinding(new CallBinding<float[]>(kGroup, "getControllerDelta", GetControllerDelta));
		AddBinding(new CallBinding<float[]>(kGroup, "getControllerPanDelta", GetControllerPanDelta));
		AddBinding(new CallBinding<float>(kGroup, "getControllerZoomDelta", GetControllerZoomDelta));
		AddBinding(new TriggerBinding<bool>(kGroup, "toggleCurveEditorFocus", OnCurveEditorFocusChange));
		AddUpdateBinding(new GetterValueBinding<float>(kGroup, "playbackDuration", () => activeSequence.playbackDuration));
		AddBinding(new TriggerBinding(kGroup, "onAfterPlaybackDurationChange", delegate
		{
			activeSequence.AfterModifications();
		}));
		AddUpdateBinding(new GetterValueBinding<float>(kGroup, "timelinePosition", () => m_TimelinePositionBindingValue));
		AddUpdateBinding(new GetterValueBinding<float>(kGroup, "timelineLength", () => activeSequence.timelineLength));
		AddUpdateBinding(new GetterValueBinding<bool>(kGroup, "playing", () => playing));
		AddBinding(new TriggerBinding<string, string>(kGroup, "save", Save));
		AddBinding(new TriggerBinding<string, string>(kGroup, "load", Load));
		AddBinding(m_LastLoaded = new ValueBinding<CinematicCameraAsset>(kGroup, "lastLoaded", null, ValueWriters.Nullable(new ValueWriter<CinematicCameraAsset>())));
		AddBinding(m_Assets = new GetterValueBinding<CinematicCameraAsset[]>(kGroup, "assets", UpdateAssets, new ArrayWriter<CinematicCameraAsset>(new ValueWriter<CinematicCameraAsset>())));
		AddBinding(new TriggerBinding<string, string>(kGroup, "delete", Delete));
		AddBinding(m_TransformAnimationCurveBinding = new ValueBinding<CinematicCameraSequence.CinematicCameraCurveModifier[]>(kGroup, "transformAnimationCurves", kEmptyModifierArray, new ListWriter<CinematicCameraSequence.CinematicCameraCurveModifier>(new ValueWriter<CinematicCameraSequence.CinematicCameraCurveModifier>())));
		AddBinding(m_ModifierAnimationCurveBinding = new ValueBinding<CinematicCameraSequence.CinematicCameraCurveModifier[]>(kGroup, "modifierAnimationCurves", kEmptyModifierArray, new ListWriter<CinematicCameraSequence.CinematicCameraCurveModifier>(new ValueWriter<CinematicCameraSequence.CinematicCameraCurveModifier>())));
		AddBinding(m_AvailableCloudTargetsBinding = new GetterValueBinding<List<string>>(kGroup, "availableCloudTargets", MenuHelpers.GetAvailableCloudTargets, new ListWriter<string>()));
		AddUpdateBinding(m_SelectedCloudTargetBinding = new GetterValueBinding<string>(kGroup, "selectedCloudTarget", () => MenuHelpers.GetSanitizedCloudTarget(SharedSettings.instance.userState.lastCloudTarget).name));
		AddBinding(new TriggerBinding<string>(kGroup, "selectCloudTarget", delegate(string cloudTarget)
		{
			SharedSettings.instance.userState.lastCloudTarget = cloudTarget;
		}));
		m_TutorialUITriggerSystem = base.World.GetOrCreateSystemManaged<TutorialUITriggerSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_PhotoModeRenderSystem = base.World.GetOrCreateSystemManaged<PhotoModeRenderSystem>();
		m_MoveAction = InputManager.instance.FindAction("Camera", "Move");
		m_ZoomAction = InputManager.instance.FindAction("Camera", "Zoom");
		m_RotateAction = InputManager.instance.FindAction("Camera", "Rotate");
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe(OnCloudTargetsChanged, delegate(AssetChangedEventArgs args)
		{
			ChangeType change = args.change;
			return change == ChangeType.DatabaseRegistered || change == ChangeType.DatabaseUnregistered || change == ChangeType.BulkAssetsChange;
		}, AssetChangedEventArgs.Default);
		AssetDatabase.global.onAssetDatabaseChanged.Subscribe<CinematicCameraAsset>(OnAssetsChanged, AssetChangedEventArgs.Default);
		Reset();
	}
```

- `private OnCurveEditorFocusChange(System.Boolean focused) : System.Void`  

```csharp
private void OnCurveEditorFocusChange(bool focused)
	{
		m_CameraUpdateSystem.orbitCameraController.inputEnabled = !focused;
		m_CameraUpdateSystem.cinematicCameraController.inputEnabled = !focused;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (m_CameraUpdateSystem?.cinematicCameraController != null)
		{
			CinematicCameraController cinematicCameraController = m_CameraUpdateSystem.cinematicCameraController;
			cinematicCameraController.eventCameraMove = (Action)Delegate.Remove(cinematicCameraController.eventCameraMove, new Action(PausePlayback));
		}
		if (m_CameraUpdateSystem?.orbitCameraController != null)
		{
			OrbitCameraController orbitCameraController = m_CameraUpdateSystem.orbitCameraController;
			orbitCameraController.EventCameraMove = (Action)Delegate.Remove(orbitCameraController.EventCameraMove, new Action(PausePlayback));
		}
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (m_CameraUpdateSystem.cinematicCameraController != null)
		{
			CinematicCameraController cinematicCameraController = m_CameraUpdateSystem.cinematicCameraController;
			cinematicCameraController.eventCameraMove = (Action)Delegate.Remove(cinematicCameraController.eventCameraMove, new Action(PausePlayback));
			CinematicCameraController cinematicCameraController2 = m_CameraUpdateSystem.cinematicCameraController;
			cinematicCameraController2.eventCameraMove = (Action)Delegate.Combine(cinematicCameraController2.eventCameraMove, new Action(PausePlayback));
		}
		if (m_CameraUpdateSystem.orbitCameraController != null)
		{
			OrbitCameraController orbitCameraController = m_CameraUpdateSystem.orbitCameraController;
			orbitCameraController.EventCameraMove = (Action)Delegate.Remove(orbitCameraController.EventCameraMove, new Action(PausePlayback));
			OrbitCameraController orbitCameraController2 = m_CameraUpdateSystem.orbitCameraController;
			orbitCameraController2.EventCameraMove = (Action)Delegate.Combine(orbitCameraController2.EventCameraMove, new Action(PausePlayback));
		}
		if (serializationContext.purpose != Purpose.Cleanup)
		{
			m_ActiveAutoplaySequence = null;
		}
		m_Playing = false;
		Reset();
	}
```

- `private OnMoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index, UnityEngine.Keyframe keyframe) : System.Int32`  

```csharp
private int OnMoveKeyFrame(string id, int curveIndex, int index, Keyframe keyframe)
	{
		GetData(id, out var modifiers, out var binding);
		CinematicCameraSequence.CinematicCameraCurveModifier modifier = modifiers[curveIndex];
		int result = activeSequence.MoveKeyframe(modifier, index, keyframe);
		binding.Update(modifiers);
		activeSequence.Refresh(t, m_PhotoModeRenderSystem.photoModeProperties, m_CameraUpdateSystem.activeCameraController);
		return result;
	}
```

- `private OnRemoveKeyFrame(System.String id, System.Int32 curveIndex, System.Int32 index) : System.Void`  

```csharp
private void OnRemoveKeyFrame(string id, int curveIndex, int index)
	{
		if (id == "Property")
		{
			string id2 = activeSequence.modifiers[curveIndex].id;
			activeSequence.RemoveModifierKey(id2, index);
			m_ModifierAnimationCurveBinding.Update(activeSequence.modifiers.ToArray());
		}
		else
		{
			activeSequence.RemoveCameraTransform(curveIndex, index);
			m_TransformAnimationCurveBinding.Update(GetTransformCurves());
		}
	}
```

- `private OnRemoveSelectedTransform(System.Int32 curveIndex, System.Int32 index) : System.Void`  

```csharp
private void OnRemoveSelectedTransform(int curveIndex, int index)
	{
		OnRemoveKeyFrame("Transform", curveIndex, index);
	}
```

- `private OnSetPlaybackDuration(System.Single duration) : System.Void`  

```csharp
private void OnSetPlaybackDuration(float duration)
	{
		activeSequence.playbackDuration = Mathf.Max(duration, activeSequence.timelineLength);
	}
```

- `private OnSetTimelinePosition(System.Single position) : System.Void`  

```csharp
private void OnSetTimelinePosition(float position)
	{
		playing = false;
		t = position;
		activeSequence.Refresh(position, m_PhotoModeRenderSystem.photoModeProperties, m_CameraUpdateSystem.activeCameraController);
	}
```

- `private OnToggleLoop(System.Boolean loop) : System.Void`  

```csharp
private void OnToggleLoop(bool loop)
	{
		activeSequence.loop = loop;
		if (loop)
		{
			m_ModifierAnimationCurveBinding.Update(activeSequence.modifiers.ToArray());
			m_TransformAnimationCurveBinding.Update(GetTransformCurves());
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (playing)
		{
			UpdatePlayback();
		}
	}
```

- `private PausePlayback() : System.Void`  

```csharp
private void PausePlayback()
	{
		if (playing && (m_CameraUpdateSystem.activeCameraController is CinematicCameraController || (m_CameraUpdateSystem.activeCameraController is OrbitCameraController && m_CameraUpdateSystem.orbitCameraController.mode == OrbitCameraController.Mode.PhotoMode)))
		{
			playing = false;
		}
	}
```

- `private Reset() : System.Void`  

```csharp
private void Reset()
	{
		activeSequence.Reset();
		m_TransformAnimationCurveBinding.Update(GetTransformCurves());
		m_ModifierAnimationCurveBinding.Update(activeSequence.modifiers.ToArray());
	}
```

- `private Save(System.String name, System.String hash = null) : System.Void`  

```csharp
private void Save(string name, string hash = null)
	{
		ILocalAssetDatabase item = MenuHelpers.GetSanitizedCloudTarget(SharedSettings.instance.userState.lastCloudTarget).db;
		if (string.IsNullOrEmpty(hash))
		{
			AssetDataPath name2 = name;
			if (!item.dataSource.isRemoteStorageSource)
			{
				string specialPath = EnvPath.GetSpecialPath<CinematicCameraAsset>();
				if (specialPath != null)
				{
					name2 = AssetDataPath.Create(specialPath, name);
				}
			}
			CinematicCameraAsset cinematicCameraAsset = item.AddAsset<CinematicCameraAsset>(name2);
			cinematicCameraAsset.target = activeSequence;
			cinematicCameraAsset.Save();
			m_LastLoaded.Update(cinematicCameraAsset);
			m_Assets.Update();
		}
		else
		{
			Colossal.Hash128 guid = new Colossal.Hash128(hash);
			CinematicCameraAsset asset = item.GetAsset<CinematicCameraAsset>(guid);
			if (asset != null)
			{
				asset.target = activeSequence;
				asset.Save();
				m_LastLoaded.Update(asset);
				m_Assets.Update();
			}
		}
	}
```

- `public StopAutoplay() : System.Void`  

```csharp
public void StopAutoplay()
	{
		m_ActiveAutoplaySequence = null;
		t = 0f;
		playing = false;
	}
```

- `private StopPlayback() : System.Void`  

```csharp
private void StopPlayback()
	{
		t = 0f;
		activeSequence.Refresh(t, m_PhotoModeRenderSystem.photoModeProperties, m_CameraUpdateSystem.activeCameraController);
		playing = false;
	}
```

- `public ToggleModifier(Game.Rendering.CinematicCamera.PhotoModeProperty p) : System.Void`  

```csharp
public void ToggleModifier(PhotoModeProperty p)
	{
		m_TutorialUITriggerSystem.ActivateTrigger(kCaptureKeyframeTutorialTag);
		foreach (PhotoModeProperty item in PhotoModeUtils.ExtractMultiPropertyComponents(p, m_PhotoModeRenderSystem.photoModeProperties))
		{
			float min = item.min?.Invoke() ?? (-10000f);
			float max = item.max?.Invoke() ?? 10000f;
			activeSequence.AddModifierKey(item.id, t, item.getValue(), min, max);
		}
		m_ModifierAnimationCurveBinding.Update(activeSequence.modifiers.ToArray());
	}
```

- `private TogglePlayback() : System.Void`  

```csharp
private void TogglePlayback()
	{
		playing = !playing;
		if (t > activeSequence.playbackDuration - 0.1f)
		{
			t = 0f;
		}
	}
```

- `private UpdateAssets() : Game.Assets.CinematicCameraAsset[]`  

```csharp
private CinematicCameraAsset[] UpdateAssets()
	{
		return AssetDatabase.global.GetAssets(default(SearchFilter<CinematicCameraAsset>)).ToArray();
	}
```

- `private UpdatePlayback() : System.Void`  

```csharp
private void UpdatePlayback()
	{
		t += UnityEngine.Time.unscaledDeltaTime;
		CinematicCameraSequence cinematicCameraSequence = m_ActiveAutoplaySequence ?? activeSequence;
		if (t >= cinematicCameraSequence.playbackDuration)
		{
			if (cinematicCameraSequence.loop)
			{
				t -= cinematicCameraSequence.playbackDuration;
			}
			else
			{
				playing = false;
			}
		}
		t = Mathf.Min(t, cinematicCameraSequence.playbackDuration);
		cinematicCameraSequence.Refresh(t, m_PhotoModeRenderSystem.photoModeProperties, m_CameraUpdateSystem.activeCameraController);
	}
```


## Nested types

- `Game.UI.InGame.CinematicCameraUISystem+<>c`  


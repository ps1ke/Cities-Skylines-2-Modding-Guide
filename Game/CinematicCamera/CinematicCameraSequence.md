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
public CinematicCameraSequence()
	{
		Reset();
	}
```


## Methods

- `public AddCameraTransform(System.Single t, UnityEngine.Vector3 position, UnityEngine.Vector3 rotation) : System.Int32`  

```csharp
public int AddCameraTransform(float t, Vector3 position, Vector3 rotation)
	{
		int result = transforms[0].AddKey(t, position.x);
		transforms[1].AddKey(t, position.y);
		transforms[2].AddKey(t, position.z);
		transforms[3].AddKey(t, (rotation.x > 90f) ? (rotation.x - 360f) : rotation.x);
		transforms[4].AddKey(t, rotation.y);
		AfterModifications(rotationsChanged: true);
		return result;
	}
```

- `public AddModifierKey(System.String id, System.Single t, System.Single value, System.Single min, System.Single max) : System.Int32`  

```csharp
public int AddModifierKey(string id, float t, float value)
	{
		int num = modifiers.FindIndex((CinematicCameraCurveModifier m) => m.id == id);
		if (num >= 0)
		{
			return modifiers[num].curve.AddKey(t, value);
		}
		modifiers.Add(new CinematicCameraCurveModifier
		{
			curve = new AnimationCurve(new Keyframe(t, value)),
			id = id
		});
		AfterModifications();
		return 0;
	}
```

- `public AddModifierKey(System.String id, System.Single t, System.Single value) : System.Int32`  

```csharp
public int AddModifierKey(string id, float t, float value)
	{
		int num = modifiers.FindIndex((CinematicCameraCurveModifier m) => m.id == id);
		if (num >= 0)
		{
			return modifiers[num].curve.AddKey(t, value);
		}
		modifiers.Add(new CinematicCameraCurveModifier
		{
			curve = new AnimationCurve(new Keyframe(t, value)),
			id = id
		});
		AfterModifications();
		return 0;
	}
```

- `public AfterModifications(System.Boolean rotationsChanged = False) : System.Void`  

```csharp
public void AfterModifications(bool rotationsChanged = false)
	{
		bool flag = EnsureLoop();
		if (rotationsChanged || flag)
		{
			PatchRotations();
		}
	}
```

- `private EnsureLoop() : System.Boolean`  

```csharp
private bool EnsureLoop(AnimationCurve curve)
	{
		bool flag = false;
		if (curve.keys.Length != 0)
		{
			float num = curve.Evaluate(0f);
			if (curve.keys[0].time > 0.1f)
			{
				curve.AddKey(0f, num);
				flag = true;
			}
			if (curve.keys[curve.keys.Length - 1].time < playbackDuration)
			{
				flag = true;
				curve.AddKey(playbackDuration, num);
			}
			if (curve.keys[curve.keys.Length - 1].time == playbackDuration)
			{
				Keyframe key = curve.keys[curve.keys.Length - 1];
				flag |= key.value != num;
				key.time = playbackDuration;
				key.value = num;
				curve.MoveKey(curve.keys.Length - 1, key);
			}
		}
		return flag;
	}
```

- `private EnsureLoop(UnityEngine.AnimationCurve curve) : System.Boolean`  

```csharp
private bool EnsureLoop(AnimationCurve curve)
	{
		bool flag = false;
		if (curve.keys.Length != 0)
		{
			float num = curve.Evaluate(0f);
			if (curve.keys[0].time > 0.1f)
			{
				curve.AddKey(0f, num);
				flag = true;
			}
			if (curve.keys[curve.keys.Length - 1].time < playbackDuration)
			{
				flag = true;
				curve.AddKey(playbackDuration, num);
			}
			if (curve.keys[curve.keys.Length - 1].time == playbackDuration)
			{
				Keyframe key = curve.keys[curve.keys.Length - 1];
				flag |= key.value != num;
				key.time = playbackDuration;
				key.value = num;
				curve.MoveKey(curve.keys.Length - 1, key);
			}
		}
		return flag;
	}
```

- `public MoveKeyframe(Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier modifier, System.Int32 index, UnityEngine.Keyframe keyframe) : System.Int32`  

```csharp
public int MoveKeyframe(CinematicCameraCurveModifier modifier, int index, Keyframe keyframe)
	{
		if (modifier.curve == null)
		{
			return -1;
		}
		AnimationCurve curve = modifier.curve;
		if (modifier.min != modifier.max)
		{
			keyframe.value = Mathf.Clamp(keyframe.value, modifier.min, modifier.max);
		}
		keyframe.weightedMode = WeightedMode.Both;
		Keyframe keyframe2 = curve[index];
		if (keyframe2.time != keyframe.time || keyframe2.value != keyframe.value || keyframe2.inTangent != keyframe.inTangent || keyframe2.outTangent != keyframe.outTangent || keyframe2.inWeight != keyframe.inWeight || keyframe2.outWeight != keyframe.outWeight)
		{
			index = curve.MoveKey(index, keyframe);
		}
		AfterModifications(modifier.id.StartsWith("Rotation"));
		return index;
	}
```

- `private PatchRotations() : System.Void`  

```csharp
private void PatchRotations()
	{
		for (int i = 1; i < transforms[4].curve.keys.Length; i++)
		{
			float time = transforms[4].curve.keys[i].time;
			float value = transforms[4].curve.keys[i - 1].value;
			float num = (transforms[4].curve.keys[i].value - value + 180f) % 360f - 180f;
			float num2 = ((num < -180f) ? (num + 360f) : num);
			transforms[4].curve.MoveKey(i, new Keyframe(time, value + num2));
		}
	}
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public void Read(IJsonReader reader)
	{
		reader.ReadMapBegin();
		reader.ReadProperty("modifiers");
		ulong num = reader.ReadArrayBegin();
		modifiers = new List<CinematicCameraCurveModifier>((int)num);
		for (ulong num2 = 0uL; num2 < num; num2++)
		{
			CinematicCameraCurveModifier item = default(CinematicCameraCurveModifier);
			item.Read(reader);
			modifiers.Add(item);
		}
		reader.ReadArrayEnd();
		reader.ReadProperty("transforms");
		num = reader.ReadArrayBegin();
		transforms = new CinematicCameraCurveModifier[num];
		for (ulong num3 = 0uL; num3 < num; num3++)
		{
			CinematicCameraCurveModifier cinematicCameraCurveModifier = default(CinematicCameraCurveModifier);
			cinematicCameraCurveModifier.Read(reader);
			transforms[num3] = cinematicCameraCurveModifier;
		}
		reader.ReadArrayEnd();
	}
```

- `public Refresh(System.Single t, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> properties, Game.Rendering.IGameCameraController controller) : System.Void`  

```csharp
public void Refresh(float t, IDictionary<string, PhotoModeProperty> properties, IGameCameraController controller)
	{
		foreach (CinematicCameraCurveModifier modifier in modifiers)
		{
			if (properties.TryGetValue(modifier.id, out var value))
			{
				float value2 = modifier.curve.Evaluate(t);
				float min = value.min?.Invoke() ?? float.MinValue;
				float max = value.max?.Invoke() ?? float.MaxValue;
				float obj = Math.Clamp(value2, min, max);
				value.setValue(obj);
			}
		}
		if (SampleTransform(controller, t, out var position, out var rotation))
		{
			controller.rotation = rotation;
			controller.position = position;
		}
	}
```

- `public RemoveCameraTransform(System.Int32 curveIndex, System.Int32 index) : System.Void`  

```csharp
public void RemoveCameraTransform(int curveIndex, int index)
	{
		if (curveIndex < transforms.Length && curveIndex >= 0 && index < transforms[curveIndex].curve.keys.Length && index >= 0)
		{
			if (transforms[curveIndex].curve.keys.Length == 1)
			{
				CinematicCameraCurveModifier cinematicCameraCurveModifier = default(CinematicCameraCurveModifier);
				TransformCurveKey transformCurveKey = (TransformCurveKey)curveIndex;
				cinematicCameraCurveModifier.id = transformCurveKey.ToString();
				cinematicCameraCurveModifier.curve = new AnimationCurve();
				transforms[curveIndex] = cinematicCameraCurveModifier;
			}
			else
			{
				transforms[curveIndex].curve.RemoveKey(index);
				AfterModifications(curveIndex == 4);
			}
		}
	}
```

- `public RemoveModifier(System.String id) : System.Void`  

```csharp
public void RemoveModifier(string id)
	{
		int num = modifiers.FindIndex((CinematicCameraCurveModifier m) => m.id == id);
		if (num >= 0)
		{
			modifiers.RemoveAt(num);
		}
	}
```

- `public RemoveModifierKey(System.String id, System.Int32 idx) : System.Void`  

```csharp
public void RemoveModifierKey(string id, int idx)
	{
		int num = modifiers.FindIndex((CinematicCameraCurveModifier m) => m.id == id);
		if (num >= 0)
		{
			if (idx < modifiers[num].curve.length)
			{
				modifiers[num].curve.RemoveKey(idx);
			}
			if (modifiers[num].curve.length == 0)
			{
				RemoveModifier(id);
			}
			AfterModifications();
		}
	}
```

- `public Reset() : System.Void`  

```csharp
public void Reset()
	{
		modifiers.Clear();
		for (int i = 0; i < transforms.Length; i++)
		{
			CinematicCameraCurveModifier[] array = transforms;
			int num = i;
			CinematicCameraCurveModifier cinematicCameraCurveModifier = default(CinematicCameraCurveModifier);
			TransformCurveKey transformCurveKey = (TransformCurveKey)i;
			cinematicCameraCurveModifier.id = transformCurveKey.ToString();
			cinematicCameraCurveModifier.curve = new AnimationCurve();
			array[num] = cinematicCameraCurveModifier;
		}
	}
```

- `public SampleTransform(Game.Rendering.IGameCameraController controller, System.Single t, UnityEngine.Vector3& position, UnityEngine.Vector3& rotation) : System.Boolean`  

```csharp
public bool SampleTransform(IGameCameraController controller, float t, out Vector3 position, out Vector3 rotation)
	{
		if (transformCount == 0)
		{
			position = Vector3.zero;
			rotation = Vector3.zero;
			return false;
		}
		position = controller.position;
		rotation = controller.rotation;
		if (transforms[0].curve.keys.Length != 0)
		{
			position.x = transforms[0].curve.Evaluate(t);
		}
		if (transforms[1].curve.keys.Length != 0)
		{
			position.y = transforms[1].curve.Evaluate(t);
		}
		if (transforms[2].curve.keys.Length != 0)
		{
			position.z = transforms[2].curve.Evaluate(t);
		}
		if (transforms[3].curve.keys.Length != 0)
		{
			rotation.x = transforms[3].curve.Evaluate(t);
		}
		if (transforms[4].curve.keys.Length != 0)
		{
			rotation.y = transforms[4].curve.Evaluate(t);
		}
		rotation.z = 0f;
		return true;
	}
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static void SupportValueTypesForAOT()
	{
		JSON.SupportTypeForAOT<CinematicCameraSequence>();
		JSON.SupportTypeForAOT<CinematicCameraCurveModifier>();
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("modifiers");
		writer.Write((IList<CinematicCameraCurveModifier>)modifiers);
		writer.PropertyName("transforms");
		writer.Write((IList<CinematicCameraCurveModifier>)transforms);
		writer.TypeEnd();
	}
```


## Nested types

- `Game.CinematicCamera.CinematicCameraSequence+TransformCurveKey`  
- `Game.CinematicCamera.CinematicCameraSequence+CinematicCameraCurveModifier`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass21_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass26_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass27_0`  
- `Game.CinematicCamera.CinematicCameraSequence+<>c__DisplayClass28_0`  


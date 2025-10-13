# Game.Rendering.VolumeHelper

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class VolumeHelper
{
    private static System.Collections.Generic.List<UnityEngine.Rendering.Volume> m_Volumes;
    public static const System.Int32 kQualityVolumePriority;
    public static const System.Int32 kGameVolumePriority;
    public static const System.Int32 kOverrideVolumePriority;
    private static const System.String kSectionName;

    public static UnityEngine.Rendering.Volume CreateVolume(System.String name, System.Int32 priority);
    private static UnityEngine.Rendering.VolumeProfile CreateVolumeProfile(System.String overrideName);
    public static System.Void DestroyVolume(UnityEngine.Rendering.Volume volume);
    public static System.Void Dispose();
    public static System.Void GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.Volume volume, PT& component);
    public static System.Void GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.VolumeProfile profile, PT& component);
}
```


## Fields

- `private static System.Collections.Generic.List<UnityEngine.Rendering.Volume> m_Volumes`  

```csharp
private static System.Collections.Generic.List<UnityEngine.Rendering.Volume> m_Volumes;
```

- `public static const System.Int32 kQualityVolumePriority`  

```csharp
public static const System.Int32 kQualityVolumePriority;
```

- `public static const System.Int32 kGameVolumePriority`  

```csharp
public static const System.Int32 kGameVolumePriority;
```

- `public static const System.Int32 kOverrideVolumePriority`  

```csharp
public static const System.Int32 kOverrideVolumePriority;
```

- `private static const System.String kSectionName`  

```csharp
private static const System.String kSectionName;
```


## Methods

- `public static CreateVolume(System.String name, System.Int32 priority) : UnityEngine.Rendering.Volume`  

```csharp
public static Volume CreateVolume(string name, int priority)
	{
		GameObject gameObject = OrderedGameObjectSpawner.Get("======Volumes======").Create(name);
		gameObject.hideFlags = HideFlags.DontSave;
		Volume component = gameObject.GetComponent<Volume>();
		component.priority = priority;
		component.sharedProfile = CreateVolumeProfile(name);
		m_Volumes.Add(component);
		return component;
	}
```

- `private static CreateVolumeProfile(System.String overrideName) : UnityEngine.Rendering.VolumeProfile`  

```csharp
private static VolumeProfile CreateVolumeProfile(string overrideName)
	{
		VolumeProfile volumeProfile = ScriptableObject.CreateInstance<VolumeProfile>();
		volumeProfile.name = overrideName + "Profile";
		volumeProfile.hideFlags = HideFlags.DontSave;
		return volumeProfile;
	}
```

- `public static DestroyVolume(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
public static void DestroyVolume(Volume volume)
	{
		m_Volumes.Remove(volume);
		if (volume.sharedProfile != null)
		{
			CoreUtils.Destroy(volume.sharedProfile);
		}
		if (volume != null)
		{
			CoreUtils.Destroy(volume.gameObject);
		}
	}
```

- `public static Dispose() : System.Void`  

```csharp
public static void Dispose()
	{
		for (int num = m_Volumes.Count - 1; num >= 0; num--)
		{
			DestroyVolume(m_Volumes[num]);
		}
	}
```

- `public static GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.Volume volume, PT& component) : System.Void`  

```csharp
public static System.Void GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.Volume volume, PT& component);
```

- `public static GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.VolumeProfile profile, PT& component) : System.Void`  

```csharp
public static System.Void GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.VolumeProfile profile, PT& component);
```



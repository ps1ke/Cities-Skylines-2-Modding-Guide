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
public static UnityEngine.Rendering.Volume CreateVolume(System.String name, System.Int32 priority);
```

- `private static CreateVolumeProfile(System.String overrideName) : UnityEngine.Rendering.VolumeProfile`  

```csharp
private static UnityEngine.Rendering.VolumeProfile CreateVolumeProfile(System.String overrideName);
```

- `public static DestroyVolume(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
public static System.Void DestroyVolume(UnityEngine.Rendering.Volume volume);
```

- `public static Dispose() : System.Void`  

```csharp
public static System.Void Dispose();
```

- `public static GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.Volume volume, PT& component) : System.Void`  

```csharp
public static System.Void GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.Volume volume, PT& component);
```

- `public static GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.VolumeProfile profile, PT& component) : System.Void`  

```csharp
public static System.Void GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.VolumeProfile profile, PT& component);
```



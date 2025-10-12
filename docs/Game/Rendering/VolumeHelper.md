# Game.Rendering.VolumeHelper

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static System.Collections.Generic.List<UnityEngine.Rendering.Volume> m_Volumes`  
- `public static const System.Int32 kQualityVolumePriority`  
- `public static const System.Int32 kGameVolumePriority`  
- `public static const System.Int32 kOverrideVolumePriority`  
- `private static const System.String kSectionName`  

## Methods

- `public static CreateVolume(System.String name, System.Int32 priority) : UnityEngine.Rendering.Volume`  
- `private static CreateVolumeProfile(System.String overrideName) : UnityEngine.Rendering.VolumeProfile`  
- `public static DestroyVolume(UnityEngine.Rendering.Volume volume) : System.Void`  
- `public static Dispose() : System.Void`  
- `public static GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.Volume volume, PT& component) : System.Void`  
- `public static GetOrCreateVolumeComponent<PT>(UnityEngine.Rendering.VolumeProfile profile, PT& component) : System.Void`  


# Game.Settings.CloudsQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.CloudsQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class CloudsQualitySettings : Game.Settings.QualitySetting<Game.Settings.CloudsQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <volumetricCloudsEnabled>k__BackingField;
    private System.Boolean <distanceCloudsEnabled>k__BackingField;
    private System.Boolean <volumetricCloudsShadows>k__BackingField;
    private System.Boolean <distanceCloudsShadows>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds;
    private static UnityEngine.Rendering.HighDefinition.VisualEnvironment m_VisualEnvironment;
    private static UnityEngine.Rendering.HighDefinition.CloudLayer m_CloudLayer;

    public System.Boolean volumetricCloudsEnabled { get; set; }
    public System.Boolean distanceCloudsEnabled { get; set; }
    public System.Boolean volumetricCloudsShadows { get; set; }
    public System.Boolean distanceCloudsShadows { get; set; }
    private static Game.Settings.CloudsQualitySettings highQuality { private get; }
    private static Game.Settings.CloudsQualitySettings mediumQuality { private get; }
    private static Game.Settings.CloudsQualitySettings lowQuality { private get; }
    private static Game.Settings.CloudsQualitySettings disabled { private get; }

    public CloudsQualitySettings();
    public CloudsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
}
```


## Fields

- `private System.Boolean <volumetricCloudsEnabled>k__BackingField`  

```csharp
private System.Boolean <volumetricCloudsEnabled>k__BackingField;
```

- `private System.Boolean <distanceCloudsEnabled>k__BackingField`  

```csharp
private System.Boolean <distanceCloudsEnabled>k__BackingField;
```

- `private System.Boolean <volumetricCloudsShadows>k__BackingField`  

```csharp
private System.Boolean <volumetricCloudsShadows>k__BackingField;
```

- `private System.Boolean <distanceCloudsShadows>k__BackingField`  

```csharp
private System.Boolean <distanceCloudsShadows>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds`  

```csharp
private static UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds;
```

- `private static UnityEngine.Rendering.HighDefinition.VisualEnvironment m_VisualEnvironment`  

```csharp
private static UnityEngine.Rendering.HighDefinition.VisualEnvironment m_VisualEnvironment;
```

- `private static UnityEngine.Rendering.HighDefinition.CloudLayer m_CloudLayer`  

```csharp
private static UnityEngine.Rendering.HighDefinition.CloudLayer m_CloudLayer;
```


## Properties

- `public System.Boolean volumetricCloudsEnabled { get; set }`  

```csharp
public System.Boolean volumetricCloudsEnabled { get; set; }
```

- `public System.Boolean distanceCloudsEnabled { get; set }`  

```csharp
public System.Boolean distanceCloudsEnabled { get; set; }
```

- `public System.Boolean volumetricCloudsShadows { get; set }`  

```csharp
public System.Boolean volumetricCloudsShadows { get; set; }
```

- `public System.Boolean distanceCloudsShadows { get; set }`  

```csharp
public System.Boolean distanceCloudsShadows { get; set; }
```

- `private static Game.Settings.CloudsQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.CloudsQualitySettings highQuality { private get; }
```

- `private static Game.Settings.CloudsQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.CloudsQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.CloudsQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.CloudsQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.CloudsQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.CloudsQualitySettings disabled { private get; }
```


## Constructors

- `public CloudsQualitySettings()`  

```csharp
public CloudsQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_VolumetricClouds);
		CreateVolumeComponent(profile, ref m_VisualEnvironment);
		CreateVolumeComponent(profile, ref m_CloudLayer);
		SetLevel(quality, apply: false);
	}
```

- `public CloudsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public CloudsQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_VolumetricClouds);
		CreateVolumeComponent(profile, ref m_VisualEnvironment);
		CreateVolumeComponent(profile, ref m_CloudLayer);
		SetLevel(quality, apply: false);
	}
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		if (m_VolumetricClouds != null)
		{
			ApplyState(m_VolumetricClouds.enable, volumetricCloudsEnabled);
			ApplyState(m_VolumetricClouds.shadows, volumetricCloudsShadows);
			ApplyState(m_VisualEnvironment.cloudType, distanceCloudsEnabled ? 1 : 0);
			ApplyState(m_CloudLayer.layerA.castShadows, distanceCloudsShadows);
		}
	}
```



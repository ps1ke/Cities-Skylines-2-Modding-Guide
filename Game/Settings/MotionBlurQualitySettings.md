# Game.Settings.MotionBlurQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.MotionBlurQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class MotionBlurQualitySettings : Game.Settings.QualitySetting<Game.Settings.MotionBlurQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Int32 <sampleCount>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlurComponent;

    public System.Boolean enabled { get; set; }
    public System.Int32 sampleCount { get; set; }
    private static Game.Settings.MotionBlurQualitySettings highQuality { private get; }
    private static Game.Settings.MotionBlurQualitySettings mediumQuality { private get; }
    private static Game.Settings.MotionBlurQualitySettings lowQuality { private get; }
    private static Game.Settings.MotionBlurQualitySettings disabled { private get; }

    public MotionBlurQualitySettings();
    public MotionBlurQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Int32 <sampleCount>k__BackingField`  

```csharp
private System.Int32 <sampleCount>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlurComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlurComponent;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Int32 sampleCount { get; set }`  

```csharp
public System.Int32 sampleCount { get; set; }
```

- `private static Game.Settings.MotionBlurQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.MotionBlurQualitySettings highQuality { private get; }
```

- `private static Game.Settings.MotionBlurQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.MotionBlurQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.MotionBlurQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.MotionBlurQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.MotionBlurQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.MotionBlurQualitySettings disabled { private get; }
```


## Constructors

- `public MotionBlurQualitySettings()`  

```csharp
public MotionBlurQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_MotionBlurComponent);
		SetLevel(quality, apply: false);
	}
```

- `public MotionBlurQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public MotionBlurQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_MotionBlurComponent);
		SetLevel(quality, apply: false);
	}
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		if (m_MotionBlurComponent != null)
		{
			ApplyState(m_MotionBlurComponent.intensity, 0f, !enabled);
			ApplyState(m_MotionBlurComponent.m_SampleCount, sampleCount);
		}
	}
```

- `public virtual IsOptionsDisabled() : System.Boolean`  

```csharp
public override bool IsOptionsDisabled()
	{
		if (!IsOptionFullyDisabled())
		{
			return !enabled;
		}
		return true;
	}
```



# Game.Settings.SSRQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.SSRQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class SSRQualitySettings : Game.Settings.QualitySetting<Game.Settings.SSRQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Boolean <enabledTransparent>k__BackingField;
    private System.Int32 <maxRaySteps>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.ScreenSpaceReflection m_SSRComponent;

    public System.Boolean enabled { get; set; }
    public System.Boolean enabledTransparent { get; set; }
    public System.Int32 maxRaySteps { get; set; }
    private static Game.Settings.SSRQualitySettings highQuality { private get; }
    private static Game.Settings.SSRQualitySettings mediumQuality { private get; }
    private static Game.Settings.SSRQualitySettings lowQuality { private get; }
    private static Game.Settings.SSRQualitySettings disabled { private get; }

    public SSRQualitySettings();
    public SSRQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Boolean <enabledTransparent>k__BackingField`  

```csharp
private System.Boolean <enabledTransparent>k__BackingField;
```

- `private System.Int32 <maxRaySteps>k__BackingField`  

```csharp
private System.Int32 <maxRaySteps>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.ScreenSpaceReflection m_SSRComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.ScreenSpaceReflection m_SSRComponent;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Boolean enabledTransparent { get; set }`  

```csharp
public System.Boolean enabledTransparent { get; set; }
```

- `public System.Int32 maxRaySteps { get; set }`  

```csharp
public System.Int32 maxRaySteps { get; set; }
```

- `private static Game.Settings.SSRQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.SSRQualitySettings highQuality { private get; }
```

- `private static Game.Settings.SSRQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.SSRQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.SSRQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.SSRQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.SSRQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.SSRQualitySettings disabled { private get; }
```


## Constructors

- `public SSRQualitySettings()`  

```csharp
public SSRQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_SSRComponent);
		SetLevel(quality, apply: false);
	}
```

- `public SSRQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public SSRQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_SSRComponent);
		SetLevel(quality, apply: false);
	}
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		if (m_SSRComponent != null)
		{
			ApplyState(m_SSRComponent.enabled, enabled);
			ApplyState(m_SSRComponent.enabledTransparent, enabled && enabledTransparent);
			ApplyState(m_SSRComponent.m_RayMaxIterations, maxRaySteps);
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



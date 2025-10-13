# Game.Settings.WaterQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.WaterQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class WaterQualitySettings : Game.Settings.QualitySetting<Game.Settings.WaterQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <waterflow>k__BackingField;
    private System.Single <maxTessellationFactor>k__BackingField;
    private System.Single <tessellationFactorFadeStart>k__BackingField;
    private System.Single <tessellationFactorFadeRange>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.WaterRendering m_WaterRenderingComponent;

    public System.Boolean waterflow { get; set; }
    public System.Single maxTessellationFactor { get; set; }
    public System.Single tessellationFactorFadeStart { get; set; }
    public System.Single tessellationFactorFadeRange { get; set; }
    private static Game.Settings.WaterQualitySettings highQuality { private get; }
    private static Game.Settings.WaterQualitySettings mediumQuality { private get; }
    private static Game.Settings.WaterQualitySettings lowQuality { private get; }

    public WaterQualitySettings();
    public WaterQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
}
```


## Fields

- `private System.Boolean <waterflow>k__BackingField`  

```csharp
private System.Boolean <waterflow>k__BackingField;
```

- `private System.Single <maxTessellationFactor>k__BackingField`  

```csharp
private System.Single <maxTessellationFactor>k__BackingField;
```

- `private System.Single <tessellationFactorFadeStart>k__BackingField`  

```csharp
private System.Single <tessellationFactorFadeStart>k__BackingField;
```

- `private System.Single <tessellationFactorFadeRange>k__BackingField`  

```csharp
private System.Single <tessellationFactorFadeRange>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.WaterRendering m_WaterRenderingComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.WaterRendering m_WaterRenderingComponent;
```


## Properties

- `public System.Boolean waterflow { get; set }`  

```csharp
public System.Boolean waterflow { get; set; }
```

- `public System.Single maxTessellationFactor { get; set }`  

```csharp
public System.Single maxTessellationFactor { get; set; }
```

- `public System.Single tessellationFactorFadeStart { get; set }`  

```csharp
public System.Single tessellationFactorFadeStart { get; set; }
```

- `public System.Single tessellationFactorFadeRange { get; set }`  

```csharp
public System.Single tessellationFactorFadeRange { get; set; }
```

- `private static Game.Settings.WaterQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.WaterQualitySettings highQuality { private get; }
```

- `private static Game.Settings.WaterQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.WaterQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.WaterQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.WaterQualitySettings lowQuality { private get; }
```


## Constructors

- `public WaterQualitySettings()`  

```csharp
public WaterQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_WaterRenderingComponent);
		SetLevel(quality, apply: false);
	}
```

- `public WaterQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public WaterQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_WaterRenderingComponent);
		SetLevel(quality, apply: false);
	}
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		if (m_WaterRenderingComponent != null)
		{
			ApplyState(m_WaterRenderingComponent.maxTessellationFactor, maxTessellationFactor);
			ApplyState(m_WaterRenderingComponent.tessellationFactorFadeStart, tessellationFactorFadeStart);
			ApplyState(m_WaterRenderingComponent.tessellationFactorFadeRange, tessellationFactorFadeRange);
		}
		foreach (WaterSurface instance in WaterSurface.instances)
		{
			instance.waterFlow = waterflow;
		}
	}
```



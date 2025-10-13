# Game.Settings.DynamicResolutionScaleSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.DynamicResolutionScaleSettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class DynamicResolutionScaleSettings : Game.Settings.QualitySetting<Game.Settings.DynamicResolutionScaleSettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Boolean <isAdaptive>k__BackingField;
    private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField;
    private System.Single <minScale>k__BackingField;
    private static UnityEngine.Camera m_Camera;

    public System.Boolean enabled { get; set; }
    public System.Boolean isAdaptive { get; set; }
    public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; set; }
    public System.Single minScale { get; set; }
    private static Game.Settings.DynamicResolutionScaleSettings constantQuality { private get; }
    private static Game.Settings.DynamicResolutionScaleSettings automaticQuality { private get; }
    private static Game.Settings.DynamicResolutionScaleSettings disabledQuality { private get; }

    public DynamicResolutionScaleSettings();
    public DynamicResolutionScaleSettings(Game.Settings.QualitySetting+Level quality);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionFullyDisabled();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Boolean <isAdaptive>k__BackingField`  

```csharp
private System.Boolean <isAdaptive>k__BackingField;
```

- `private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField`  

```csharp
private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField;
```

- `private System.Single <minScale>k__BackingField`  

```csharp
private System.Single <minScale>k__BackingField;
```

- `private static UnityEngine.Camera m_Camera`  

```csharp
private static UnityEngine.Camera m_Camera;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Boolean isAdaptive { get; set }`  

```csharp
public System.Boolean isAdaptive { get; set; }
```

- `public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; set }`  

```csharp
public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; set; }
```

- `public System.Single minScale { get; set }`  

```csharp
public System.Single minScale { get; set; }
```

- `private static Game.Settings.DynamicResolutionScaleSettings constantQuality { private get }`  

```csharp
private static Game.Settings.DynamicResolutionScaleSettings constantQuality { private get; }
```

- `private static Game.Settings.DynamicResolutionScaleSettings automaticQuality { private get }`  

```csharp
private static Game.Settings.DynamicResolutionScaleSettings automaticQuality { private get; }
```

- `private static Game.Settings.DynamicResolutionScaleSettings disabledQuality { private get }`  

```csharp
private static Game.Settings.DynamicResolutionScaleSettings disabledQuality { private get; }
```


## Constructors

- `public DynamicResolutionScaleSettings()`  

```csharp
public DynamicResolutionScaleSettings(Level quality)
	{
		SetLevel(quality, apply: false);
	}
```

- `public DynamicResolutionScaleSettings(Game.Settings.QualitySetting+Level quality)`  

```csharp
public DynamicResolutionScaleSettings(Level quality)
	{
		SetLevel(quality, apply: false);
	}
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		if (TryGetGameplayCamera(ref m_Camera))
		{
			AdaptiveDynamicResolutionScale.instance.SetParams(enabled, isAdaptive, minScale, upscaleFilter, m_Camera);
		}
	}
```

- `public virtual IsOptionFullyDisabled() : System.Boolean`  

```csharp
public override bool IsOptionFullyDisabled()
	{
		if (!base.IsOptionFullyDisabled() && !SharedSettings.instance.graphics.isDlssActive)
		{
			return SharedSettings.instance.graphics.isFsr2Active;
		}
		return true;
	}
```

- `public virtual IsOptionsDisabled() : System.Boolean`  

```csharp
public override bool IsOptionsDisabled()
	{
		if (enabled)
		{
			return IsOptionFullyDisabled();
		}
		return true;
	}
```



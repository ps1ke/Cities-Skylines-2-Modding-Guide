# Game.Settings.AnimationQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.AnimationQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class AnimationQualitySettings : Game.Settings.QualitySetting<Game.Settings.AnimationQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private Game.Settings.AnimationQualitySettings+Skinning <maxBoneInfuence>k__BackingField;

    public Game.Settings.AnimationQualitySettings+Skinning maxBoneInfuence { get; set; }
    private static Game.Settings.AnimationQualitySettings highQuality { private get; }
    private static Game.Settings.AnimationQualitySettings mediumQuality { private get; }

    public AnimationQualitySettings();
    public AnimationQualitySettings(Game.Settings.QualitySetting+Level quality);

    public virtual System.Void Apply();
}
```


## Fields

- `private Game.Settings.AnimationQualitySettings+Skinning <maxBoneInfuence>k__BackingField`  

```csharp
private Game.Settings.AnimationQualitySettings+Skinning <maxBoneInfuence>k__BackingField;
```


## Properties

- `public Game.Settings.AnimationQualitySettings+Skinning maxBoneInfuence { get; set }`  

```csharp
public Game.Settings.AnimationQualitySettings+Skinning maxBoneInfuence { get; set; }
```

- `private static Game.Settings.AnimationQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.AnimationQualitySettings highQuality { private get; }
```

- `private static Game.Settings.AnimationQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.AnimationQualitySettings mediumQuality { private get; }
```


## Constructors

- `public AnimationQualitySettings()`  

```csharp
public AnimationQualitySettings(Level quality)
	{
		SetLevel(quality, apply: false);
	}
```

- `public AnimationQualitySettings(Game.Settings.QualitySetting+Level quality)`  

```csharp
public AnimationQualitySettings(Level quality)
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
		if (maxBoneInfuence == Skinning.FourBones)
		{
			Shader.DisableKeyword("TWO_BONES_INFLUENCE");
		}
		else if (maxBoneInfuence == Skinning.TwoBones)
		{
			Shader.EnableKeyword("TWO_BONES_INFLUENCE");
		}
	}
```


## Nested types

- `Game.Settings.AnimationQualitySettings+Skinning`  


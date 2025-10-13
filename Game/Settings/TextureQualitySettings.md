# Game.Settings.TextureQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.TextureQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class TextureQualitySettings : Game.Settings.QualitySetting<Game.Settings.TextureQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Int32 <mipbias>k__BackingField;
    private UnityEngine.Rendering.VirtualTexturing.FilterMode <filterMode>k__BackingField;

    public System.Int32 mipbias { get; set; }
    public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode { get; set; }
    private static Game.Settings.TextureQualitySettings highQuality { private get; }
    private static Game.Settings.TextureQualitySettings mediumQuality { private get; }
    private static Game.Settings.TextureQualitySettings lowQuality { private get; }
    private static Game.Settings.TextureQualitySettings veryLowQuality { private get; }

    public TextureQualitySettings();
    public TextureQualitySettings(Game.Settings.QualitySetting+Level quality);

    public virtual System.Void Apply();
}
```


## Fields

- `private System.Int32 <mipbias>k__BackingField`  

```csharp
private System.Int32 <mipbias>k__BackingField;
```

- `private UnityEngine.Rendering.VirtualTexturing.FilterMode <filterMode>k__BackingField`  

```csharp
private UnityEngine.Rendering.VirtualTexturing.FilterMode <filterMode>k__BackingField;
```


## Properties

- `public System.Int32 mipbias { get; set }`  

```csharp
public System.Int32 mipbias { get; set; }
```

- `public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode { get; set }`  

```csharp
public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode { get; set; }
```

- `private static Game.Settings.TextureQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.TextureQualitySettings highQuality { private get; }
```

- `private static Game.Settings.TextureQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.TextureQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.TextureQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.TextureQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.TextureQualitySettings veryLowQuality { private get }`  

```csharp
private static Game.Settings.TextureQualitySettings veryLowQuality { private get; }
```


## Constructors

- `public TextureQualitySettings()`  

```csharp
public TextureQualitySettings(Level quality)
	{
		SetLevel(quality, apply: false);
	}
```

- `public TextureQualitySettings(Game.Settings.QualitySetting+Level quality)`  

```csharp
public TextureQualitySettings(Level quality)
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
		(World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<ManagedBatchSystem>())?.ResetVT(mipbias, filterMode);
	}
```



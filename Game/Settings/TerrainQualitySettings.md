# Game.Settings.TerrainQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.TerrainQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class TerrainQualitySettings : Game.Settings.QualitySetting<Game.Settings.TerrainQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Int32 <finalTessellation>k__BackingField;
    private System.Int32 <targetPatchSize>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.TerrainRendering m_TerrainRenderingComponent;

    public System.Int32 finalTessellation { get; set; }
    public System.Int32 targetPatchSize { get; set; }
    private static Game.Settings.TerrainQualitySettings highQuality { private get; }
    private static Game.Settings.TerrainQualitySettings mediumQuality { private get; }
    private static Game.Settings.TerrainQualitySettings lowQuality { private get; }

    public TerrainQualitySettings();
    public TerrainQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
}
```


## Fields

- `private System.Int32 <finalTessellation>k__BackingField`  

```csharp
private System.Int32 <finalTessellation>k__BackingField;
```

- `private System.Int32 <targetPatchSize>k__BackingField`  

```csharp
private System.Int32 <targetPatchSize>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.TerrainRendering m_TerrainRenderingComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.TerrainRendering m_TerrainRenderingComponent;
```


## Properties

- `public System.Int32 finalTessellation { get; set }`  

```csharp
public System.Int32 finalTessellation { get; set; }
```

- `public System.Int32 targetPatchSize { get; set }`  

```csharp
public System.Int32 targetPatchSize { get; set; }
```

- `private static Game.Settings.TerrainQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.TerrainQualitySettings highQuality { private get; }
```

- `private static Game.Settings.TerrainQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.TerrainQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.TerrainQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.TerrainQualitySettings lowQuality { private get; }
```


## Constructors

- `public TerrainQualitySettings()`  

```csharp
public TerrainQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_TerrainRenderingComponent);
		SetLevel(quality, apply: false);
	}
```

- `public TerrainQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public TerrainQualitySettings(Level quality, VolumeProfile profile)
	{
		CreateVolumeComponent(profile, ref m_TerrainRenderingComponent);
		SetLevel(quality, apply: false);
	}
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		if (m_TerrainRenderingComponent != null)
		{
			ApplyState(m_TerrainRenderingComponent.finalTessellation, finalTessellation);
			ApplyState(m_TerrainRenderingComponent.targetPatchSize, targetPatchSize);
		}
	}
```



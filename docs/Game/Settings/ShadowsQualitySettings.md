# Game.Settings.ShadowsQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.ShadowsQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class ShadowsQualitySettings : Game.Settings.QualitySetting<Game.Settings.ShadowsQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Int32 <directionalShadowResolution>k__BackingField;
    private System.Boolean <terrainCastShadows>k__BackingField;
    private System.Single <shadowCullingThresholdHeight>k__BackingField;
    private System.Single <shadowCullingThresholdVolume>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.HDShadowSettings m_CascadeShadows;
    private static UnityEngine.Rendering.HighDefinition.HDAdditionalLightData m_SunLightData;

    public System.Boolean enabled { get; set; }
    public System.Int32 directionalShadowResolution { get; set; }
    public System.Boolean terrainCastShadows { get; set; }
    public System.Single shadowCullingThresholdHeight { get; set; }
    public System.Single shadowCullingThresholdVolume { get; set; }
    private static Game.Settings.ShadowsQualitySettings highQuality { private get; }
    private static Game.Settings.ShadowsQualitySettings mediumQuality { private get; }
    private static Game.Settings.ShadowsQualitySettings lowQuality { private get; }
    private static Game.Settings.ShadowsQualitySettings disabled { private get; }

    public ShadowsQualitySettings();
    public ShadowsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Int32 <directionalShadowResolution>k__BackingField`  

```csharp
private System.Int32 <directionalShadowResolution>k__BackingField;
```

- `private System.Boolean <terrainCastShadows>k__BackingField`  

```csharp
private System.Boolean <terrainCastShadows>k__BackingField;
```

- `private System.Single <shadowCullingThresholdHeight>k__BackingField`  

```csharp
private System.Single <shadowCullingThresholdHeight>k__BackingField;
```

- `private System.Single <shadowCullingThresholdVolume>k__BackingField`  

```csharp
private System.Single <shadowCullingThresholdVolume>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.HDShadowSettings m_CascadeShadows`  

```csharp
private static UnityEngine.Rendering.HighDefinition.HDShadowSettings m_CascadeShadows;
```

- `private static UnityEngine.Rendering.HighDefinition.HDAdditionalLightData m_SunLightData`  

```csharp
private static UnityEngine.Rendering.HighDefinition.HDAdditionalLightData m_SunLightData;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Int32 directionalShadowResolution { get; set }`  

```csharp
public System.Int32 directionalShadowResolution { get; set; }
```

- `public System.Boolean terrainCastShadows { get; set }`  

```csharp
public System.Boolean terrainCastShadows { get; set; }
```

- `public System.Single shadowCullingThresholdHeight { get; set }`  

```csharp
public System.Single shadowCullingThresholdHeight { get; set; }
```

- `public System.Single shadowCullingThresholdVolume { get; set }`  

```csharp
public System.Single shadowCullingThresholdVolume { get; set; }
```

- `private static Game.Settings.ShadowsQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.ShadowsQualitySettings highQuality { private get; }
```

- `private static Game.Settings.ShadowsQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.ShadowsQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.ShadowsQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.ShadowsQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.ShadowsQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.ShadowsQualitySettings disabled { private get; }
```


## Constructors

- `public ShadowsQualitySettings()`  

```csharp
public ShadowsQualitySettings();
```

- `public ShadowsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public ShadowsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `public virtual IsOptionsDisabled() : System.Boolean`  

```csharp
public virtual System.Boolean IsOptionsDisabled();
```



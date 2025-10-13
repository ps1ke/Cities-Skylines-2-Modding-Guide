# Game.Settings.VolumetricsQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.VolumetricsQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class VolumetricsQualitySettings : Game.Settings.QualitySetting<Game.Settings.VolumetricsQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Single <budget>k__BackingField;
    private System.Single <resolutionDepthRatio>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.Fog m_FogComponent;

    public System.Boolean enabled { get; set; }
    public System.Single budget { get; set; }
    public System.Single resolutionDepthRatio { get; set; }
    private static Game.Settings.VolumetricsQualitySettings highQuality { private get; }
    private static Game.Settings.VolumetricsQualitySettings mediumQuality { private get; }
    private static Game.Settings.VolumetricsQualitySettings lowQuality { private get; }
    private static Game.Settings.VolumetricsQualitySettings disabled { private get; }

    public VolumetricsQualitySettings();
    public VolumetricsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Single <budget>k__BackingField`  

```csharp
private System.Single <budget>k__BackingField;
```

- `private System.Single <resolutionDepthRatio>k__BackingField`  

```csharp
private System.Single <resolutionDepthRatio>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.Fog m_FogComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.Fog m_FogComponent;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Single budget { get; set }`  

```csharp
public System.Single budget { get; set; }
```

- `public System.Single resolutionDepthRatio { get; set }`  

```csharp
public System.Single resolutionDepthRatio { get; set; }
```

- `private static Game.Settings.VolumetricsQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.VolumetricsQualitySettings highQuality { private get; }
```

- `private static Game.Settings.VolumetricsQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.VolumetricsQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.VolumetricsQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.VolumetricsQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.VolumetricsQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.VolumetricsQualitySettings disabled { private get; }
```


## Constructors

- `public VolumetricsQualitySettings()`  

```csharp
public VolumetricsQualitySettings();
```

- `public VolumetricsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public VolumetricsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);
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



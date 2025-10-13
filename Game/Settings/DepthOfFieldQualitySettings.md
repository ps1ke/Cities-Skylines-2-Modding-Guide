# Game.Settings.DepthOfFieldQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.DepthOfFieldQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class DepthOfFieldQualitySettings : Game.Settings.QualitySetting<Game.Settings.DepthOfFieldQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Int32 <nearSampleCount>k__BackingField;
    private System.Single <nearMaxRadius>k__BackingField;
    private System.Int32 <farSampleCount>k__BackingField;
    private System.Single <farMaxRadius>k__BackingField;
    private UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution <resolution>k__BackingField;
    private System.Boolean <highQualityFiltering>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.DepthOfField m_DOFComponent;

    public System.Boolean enabled { get; set; }
    public System.Int32 nearSampleCount { get; set; }
    public System.Single nearMaxRadius { get; set; }
    public System.Int32 farSampleCount { get; set; }
    public System.Single farMaxRadius { get; set; }
    public UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution resolution { get; set; }
    public System.Boolean highQualityFiltering { get; set; }
    private static Game.Settings.DepthOfFieldQualitySettings highQuality { private get; }
    private static Game.Settings.DepthOfFieldQualitySettings mediumQuality { private get; }
    private static Game.Settings.DepthOfFieldQualitySettings lowQuality { private get; }
    private static Game.Settings.DepthOfFieldQualitySettings disabled { private get; }

    public DepthOfFieldQualitySettings();
    public DepthOfFieldQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Int32 <nearSampleCount>k__BackingField`  

```csharp
private System.Int32 <nearSampleCount>k__BackingField;
```

- `private System.Single <nearMaxRadius>k__BackingField`  

```csharp
private System.Single <nearMaxRadius>k__BackingField;
```

- `private System.Int32 <farSampleCount>k__BackingField`  

```csharp
private System.Int32 <farSampleCount>k__BackingField;
```

- `private System.Single <farMaxRadius>k__BackingField`  

```csharp
private System.Single <farMaxRadius>k__BackingField;
```

- `private UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution <resolution>k__BackingField`  

```csharp
private UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution <resolution>k__BackingField;
```

- `private System.Boolean <highQualityFiltering>k__BackingField`  

```csharp
private System.Boolean <highQualityFiltering>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.DepthOfField m_DOFComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.DepthOfField m_DOFComponent;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Int32 nearSampleCount { get; set }`  

```csharp
public System.Int32 nearSampleCount { get; set; }
```

- `public System.Single nearMaxRadius { get; set }`  

```csharp
public System.Single nearMaxRadius { get; set; }
```

- `public System.Int32 farSampleCount { get; set }`  

```csharp
public System.Int32 farSampleCount { get; set; }
```

- `public System.Single farMaxRadius { get; set }`  

```csharp
public System.Single farMaxRadius { get; set; }
```

- `public UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution resolution { get; set }`  

```csharp
public UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution resolution { get; set; }
```

- `public System.Boolean highQualityFiltering { get; set }`  

```csharp
public System.Boolean highQualityFiltering { get; set; }
```

- `private static Game.Settings.DepthOfFieldQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.DepthOfFieldQualitySettings highQuality { private get; }
```

- `private static Game.Settings.DepthOfFieldQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.DepthOfFieldQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.DepthOfFieldQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.DepthOfFieldQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.DepthOfFieldQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.DepthOfFieldQualitySettings disabled { private get; }
```


## Constructors

- `public DepthOfFieldQualitySettings()`  

```csharp
public DepthOfFieldQualitySettings();
```

- `public DepthOfFieldQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public DepthOfFieldQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);
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



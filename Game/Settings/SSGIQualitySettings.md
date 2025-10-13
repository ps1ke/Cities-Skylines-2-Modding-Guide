# Game.Settings.SSGIQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.SSGIQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class SSGIQualitySettings : Game.Settings.QualitySetting<Game.Settings.SSGIQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private System.Boolean <fullscreen>k__BackingField;
    private System.Int32 <raySteps>k__BackingField;
    private System.Single <denoiserRadius>k__BackingField;
    private System.Boolean <halfResolutionPass>k__BackingField;
    private System.Boolean <secondDenoiserPass>k__BackingField;
    private System.Single <depthBufferThickness>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.GlobalIllumination m_SSGIComponent;

    public System.Boolean enabled { get; set; }
    public System.Boolean fullscreen { get; set; }
    public System.Int32 raySteps { get; set; }
    public System.Single denoiserRadius { get; set; }
    public System.Boolean halfResolutionPass { get; set; }
    public System.Boolean secondDenoiserPass { get; set; }
    public System.Single depthBufferThickness { get; set; }
    private static Game.Settings.SSGIQualitySettings highQuality { private get; }
    private static Game.Settings.SSGIQualitySettings mediumQuality { private get; }
    private static Game.Settings.SSGIQualitySettings lowQuality { private get; }
    private static Game.Settings.SSGIQualitySettings disabled { private get; }

    public SSGIQualitySettings();
    public SSGIQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionsDisabled();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
```

- `private System.Boolean <fullscreen>k__BackingField`  

```csharp
private System.Boolean <fullscreen>k__BackingField;
```

- `private System.Int32 <raySteps>k__BackingField`  

```csharp
private System.Int32 <raySteps>k__BackingField;
```

- `private System.Single <denoiserRadius>k__BackingField`  

```csharp
private System.Single <denoiserRadius>k__BackingField;
```

- `private System.Boolean <halfResolutionPass>k__BackingField`  

```csharp
private System.Boolean <halfResolutionPass>k__BackingField;
```

- `private System.Boolean <secondDenoiserPass>k__BackingField`  

```csharp
private System.Boolean <secondDenoiserPass>k__BackingField;
```

- `private System.Single <depthBufferThickness>k__BackingField`  

```csharp
private System.Single <depthBufferThickness>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.GlobalIllumination m_SSGIComponent`  

```csharp
private static UnityEngine.Rendering.HighDefinition.GlobalIllumination m_SSGIComponent;
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.Boolean fullscreen { get; set }`  

```csharp
public System.Boolean fullscreen { get; set; }
```

- `public System.Int32 raySteps { get; set }`  

```csharp
public System.Int32 raySteps { get; set; }
```

- `public System.Single denoiserRadius { get; set }`  

```csharp
public System.Single denoiserRadius { get; set; }
```

- `public System.Boolean halfResolutionPass { get; set }`  

```csharp
public System.Boolean halfResolutionPass { get; set; }
```

- `public System.Boolean secondDenoiserPass { get; set }`  

```csharp
public System.Boolean secondDenoiserPass { get; set; }
```

- `public System.Single depthBufferThickness { get; set }`  

```csharp
public System.Single depthBufferThickness { get; set; }
```

- `private static Game.Settings.SSGIQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.SSGIQualitySettings highQuality { private get; }
```

- `private static Game.Settings.SSGIQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.SSGIQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.SSGIQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.SSGIQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.SSGIQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.SSGIQualitySettings disabled { private get; }
```


## Constructors

- `public SSGIQualitySettings()`  

```csharp
public SSGIQualitySettings();
```

- `public SSGIQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public SSGIQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);
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



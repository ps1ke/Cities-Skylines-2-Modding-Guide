# Game.Settings.FogQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.FogQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class FogQualitySettings : Game.Settings.QualitySetting<Game.Settings.FogQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <enabled>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.Fog m_FogComponent;

    public System.Boolean enabled { get; set; }
    private static Game.Settings.FogQualitySettings lowQuality { private get; }
    private static Game.Settings.FogQualitySettings disabled { private get; }

    public FogQualitySettings();
    public FogQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);

    public virtual System.Void Apply();
}
```


## Fields

- `private System.Boolean <enabled>k__BackingField`  

```csharp
private System.Boolean <enabled>k__BackingField;
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

- `private static Game.Settings.FogQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.FogQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.FogQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.FogQualitySettings disabled { private get; }
```


## Constructors

- `public FogQualitySettings()`  

```csharp
public FogQualitySettings();
```

- `public FogQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

```csharp
public FogQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile);
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```



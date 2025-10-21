# Game.Settings.AntiAliasingQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.AntiAliasingQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class AntiAliasingQualitySettings : Game.Settings.QualitySetting<Game.Settings.AntiAliasingQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod <antiAliasingMethod>k__BackingField;
    private UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel <smaaQuality>k__BackingField;
    private UnityEngine.Rendering.MSAASamples <outlinesMSAA>k__BackingField;
    private static UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData m_GameCamera;

    public Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod antiAliasingMethod { get; set; }
    public UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel smaaQuality { get; set; }
    public UnityEngine.Rendering.MSAASamples outlinesMSAA { get; set; }
    private static Game.Settings.AntiAliasingQualitySettings highQuality { private get; }
    private static Game.Settings.AntiAliasingQualitySettings mediumQuality { private get; }
    private static Game.Settings.AntiAliasingQualitySettings lowQuality { private get; }
    private static Game.Settings.AntiAliasingQualitySettings disabled { private get; }

    public AntiAliasingQualitySettings();
    public AntiAliasingQualitySettings(Game.Settings.QualitySetting+Level quality);

    public virtual System.Void Apply();
    public virtual System.Boolean IsOptionFullyDisabled();
    private static UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+AntialiasingMode ToAAMode(Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod method);
}
```


## Fields

- `private Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod <antiAliasingMethod>k__BackingField`  

```csharp
private Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod <antiAliasingMethod>k__BackingField;
```

- `private UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel <smaaQuality>k__BackingField`  

```csharp
private UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel <smaaQuality>k__BackingField;
```

- `private UnityEngine.Rendering.MSAASamples <outlinesMSAA>k__BackingField`  

```csharp
private UnityEngine.Rendering.MSAASamples <outlinesMSAA>k__BackingField;
```

- `private static UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData m_GameCamera`  

```csharp
private static UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData m_GameCamera;
```


## Properties

- `public Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod antiAliasingMethod { get; set }`  

```csharp
public Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod antiAliasingMethod { get; set; }
```

- `public UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel smaaQuality { get; set }`  

```csharp
public UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel smaaQuality { get; set; }
```

- `public UnityEngine.Rendering.MSAASamples outlinesMSAA { get; set }`  

```csharp
public UnityEngine.Rendering.MSAASamples outlinesMSAA { get; set; }
```

- `private static Game.Settings.AntiAliasingQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.AntiAliasingQualitySettings highQuality { private get; }
```

- `private static Game.Settings.AntiAliasingQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.AntiAliasingQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.AntiAliasingQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.AntiAliasingQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.AntiAliasingQualitySettings disabled { private get }`  

```csharp
private static Game.Settings.AntiAliasingQualitySettings disabled { private get; }
```


## Constructors

- `public AntiAliasingQualitySettings()`  

```csharp
public AntiAliasingQualitySettings();
```

- `public AntiAliasingQualitySettings(Game.Settings.QualitySetting+Level quality)`  

```csharp
public AntiAliasingQualitySettings(Game.Settings.QualitySetting+Level quality);
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `public virtual IsOptionFullyDisabled() : System.Boolean`  

```csharp
public virtual System.Boolean IsOptionFullyDisabled();
```

- `private static ToAAMode(Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod method) : UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+AntialiasingMode`  

```csharp
private static UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+AntialiasingMode ToAAMode(Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod method);
```


## Nested types

- `Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod`  


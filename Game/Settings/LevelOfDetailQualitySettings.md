# Game.Settings.LevelOfDetailQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.LevelOfDetailQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Code

```csharp
public class LevelOfDetailQualitySettings : Game.Settings.QualitySetting<Game.Settings.LevelOfDetailQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Single <levelOfDetail>k__BackingField;
    private System.Boolean <lodCrossFade>k__BackingField;
    private System.Int32 <maxLightCount>k__BackingField;
    private System.Int32 <meshMemoryBudget>k__BackingField;
    private System.Boolean <strictMeshMemory>k__BackingField;

    public System.Single levelOfDetail { get; set; }
    public System.Boolean lodCrossFade { get; set; }
    public System.Int32 maxLightCount { get; set; }
    public System.Int32 meshMemoryBudget { get; set; }
    public System.Boolean strictMeshMemory { get; set; }
    private static Game.Settings.LevelOfDetailQualitySettings highQuality { private get; }
    private static Game.Settings.LevelOfDetailQualitySettings mediumQuality { private get; }
    private static Game.Settings.LevelOfDetailQualitySettings lowQuality { private get; }
    private static Game.Settings.LevelOfDetailQualitySettings veryLowQuality { private get; }

    public LevelOfDetailQualitySettings();
    public LevelOfDetailQualitySettings(Game.Settings.QualitySetting+Level quality);

    public virtual System.Void Apply();
}
```


## Fields

- `private System.Single <levelOfDetail>k__BackingField`  

```csharp
private System.Single <levelOfDetail>k__BackingField;
```

- `private System.Boolean <lodCrossFade>k__BackingField`  

```csharp
private System.Boolean <lodCrossFade>k__BackingField;
```

- `private System.Int32 <maxLightCount>k__BackingField`  

```csharp
private System.Int32 <maxLightCount>k__BackingField;
```

- `private System.Int32 <meshMemoryBudget>k__BackingField`  

```csharp
private System.Int32 <meshMemoryBudget>k__BackingField;
```

- `private System.Boolean <strictMeshMemory>k__BackingField`  

```csharp
private System.Boolean <strictMeshMemory>k__BackingField;
```


## Properties

- `public System.Single levelOfDetail { get; set }`  

```csharp
public System.Single levelOfDetail { get; set; }
```

- `public System.Boolean lodCrossFade { get; set }`  

```csharp
public System.Boolean lodCrossFade { get; set; }
```

- `public System.Int32 maxLightCount { get; set }`  

```csharp
public System.Int32 maxLightCount { get; set; }
```

- `public System.Int32 meshMemoryBudget { get; set }`  

```csharp
public System.Int32 meshMemoryBudget { get; set; }
```

- `public System.Boolean strictMeshMemory { get; set }`  

```csharp
public System.Boolean strictMeshMemory { get; set; }
```

- `private static Game.Settings.LevelOfDetailQualitySettings highQuality { private get }`  

```csharp
private static Game.Settings.LevelOfDetailQualitySettings highQuality { private get; }
```

- `private static Game.Settings.LevelOfDetailQualitySettings mediumQuality { private get }`  

```csharp
private static Game.Settings.LevelOfDetailQualitySettings mediumQuality { private get; }
```

- `private static Game.Settings.LevelOfDetailQualitySettings lowQuality { private get }`  

```csharp
private static Game.Settings.LevelOfDetailQualitySettings lowQuality { private get; }
```

- `private static Game.Settings.LevelOfDetailQualitySettings veryLowQuality { private get }`  

```csharp
private static Game.Settings.LevelOfDetailQualitySettings veryLowQuality { private get; }
```


## Constructors

- `public LevelOfDetailQualitySettings()`  

```csharp
public LevelOfDetailQualitySettings();
```

- `public LevelOfDetailQualitySettings(Game.Settings.QualitySetting+Level quality)`  

```csharp
public LevelOfDetailQualitySettings(Game.Settings.QualitySetting+Level quality);
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```



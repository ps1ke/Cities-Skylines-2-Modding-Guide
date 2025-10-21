# Game.Settings.AudioSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIGroupOrder`  

## Code

```csharp
public class AudioSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Audio.Radio.Radio m_Radio;
    private System.Single <masterVolume>k__BackingField;
    private System.Single <uiVolume>k__BackingField;
    private System.Single <menuVolume>k__BackingField;
    private System.Single <ingameVolume>k__BackingField;
    private System.Boolean <radioActive>k__BackingField;
    private System.Single <radioVolume>k__BackingField;
    private System.Single <ambienceVolume>k__BackingField;
    private System.Single <disastersVolume>k__BackingField;
    private System.Single <worldVolume>k__BackingField;
    private System.Single <audioGroupsVolume>k__BackingField;
    private System.Single <serviceBuildingsVolume>k__BackingField;
    private System.Int32 <clipMemoryBudget>k__BackingField;
    public static const System.String kName;
    public static const System.String kMainGroup;
    public static const System.String kRadioGroup;
    public static const System.String kAdvancedGroup;

    public System.Single masterVolume { get; set; }
    public System.Single uiVolume { get; set; }
    public System.Single menuVolume { get; set; }
    public System.Single ingameVolume { get; set; }
    public System.Boolean radioActive { get; set; }
    public System.Single radioVolume { get; set; }
    public System.Single ambienceVolume { get; set; }
    public System.Single disastersVolume { get; set; }
    public System.Single worldVolume { get; set; }
    public System.Single audioGroupsVolume { get; set; }
    public System.Single serviceBuildingsVolume { get; set; }
    public System.Int32 clipMemoryBudget { get; set; }

    public AudioSettings();

    public virtual System.Void Apply();
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Audio.Radio.Radio m_Radio`  

```csharp
private Game.Audio.Radio.Radio m_Radio;
```

- `private System.Single <masterVolume>k__BackingField`  

```csharp
private System.Single <masterVolume>k__BackingField;
```

- `private System.Single <uiVolume>k__BackingField`  

```csharp
private System.Single <uiVolume>k__BackingField;
```

- `private System.Single <menuVolume>k__BackingField`  

```csharp
private System.Single <menuVolume>k__BackingField;
```

- `private System.Single <ingameVolume>k__BackingField`  

```csharp
private System.Single <ingameVolume>k__BackingField;
```

- `private System.Boolean <radioActive>k__BackingField`  

```csharp
private System.Boolean <radioActive>k__BackingField;
```

- `private System.Single <radioVolume>k__BackingField`  

```csharp
private System.Single <radioVolume>k__BackingField;
```

- `private System.Single <ambienceVolume>k__BackingField`  

```csharp
private System.Single <ambienceVolume>k__BackingField;
```

- `private System.Single <disastersVolume>k__BackingField`  

```csharp
private System.Single <disastersVolume>k__BackingField;
```

- `private System.Single <worldVolume>k__BackingField`  

```csharp
private System.Single <worldVolume>k__BackingField;
```

- `private System.Single <audioGroupsVolume>k__BackingField`  

```csharp
private System.Single <audioGroupsVolume>k__BackingField;
```

- `private System.Single <serviceBuildingsVolume>k__BackingField`  

```csharp
private System.Single <serviceBuildingsVolume>k__BackingField;
```

- `private System.Int32 <clipMemoryBudget>k__BackingField`  

```csharp
private System.Int32 <clipMemoryBudget>k__BackingField;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `public static const System.String kMainGroup`  

```csharp
public static const System.String kMainGroup;
```

- `public static const System.String kRadioGroup`  

```csharp
public static const System.String kRadioGroup;
```

- `public static const System.String kAdvancedGroup`  

```csharp
public static const System.String kAdvancedGroup;
```


## Properties

- `public System.Single masterVolume { get; set }`  

```csharp
public System.Single masterVolume { get; set; }
```

- `public System.Single uiVolume { get; set }`  

```csharp
public System.Single uiVolume { get; set; }
```

- `public System.Single menuVolume { get; set }`  

```csharp
public System.Single menuVolume { get; set; }
```

- `public System.Single ingameVolume { get; set }`  

```csharp
public System.Single ingameVolume { get; set; }
```

- `public System.Boolean radioActive { get; set }`  

```csharp
public System.Boolean radioActive { get; set; }
```

- `public System.Single radioVolume { get; set }`  

```csharp
public System.Single radioVolume { get; set; }
```

- `public System.Single ambienceVolume { get; set }`  

```csharp
public System.Single ambienceVolume { get; set; }
```

- `public System.Single disastersVolume { get; set }`  

```csharp
public System.Single disastersVolume { get; set; }
```

- `public System.Single worldVolume { get; set }`  

```csharp
public System.Single worldVolume { get; set; }
```

- `public System.Single audioGroupsVolume { get; set }`  

```csharp
public System.Single audioGroupsVolume { get; set; }
```

- `public System.Single serviceBuildingsVolume { get; set }`  

```csharp
public System.Single serviceBuildingsVolume { get; set; }
```

- `public System.Int32 clipMemoryBudget { get; set }`  

```csharp
public System.Int32 clipMemoryBudget { get; set; }
```


## Constructors

- `public AudioSettings()`  

```csharp
public AudioSettings();
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```



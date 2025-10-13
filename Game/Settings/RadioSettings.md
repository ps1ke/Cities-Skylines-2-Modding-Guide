# Game.Settings.RadioSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Code

```csharp
public class RadioSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private Game.Audio.Radio.Radio m_Radio;
    private System.Boolean <enableSpectrum>k__BackingField;
    private System.Int32 <spectrumNumSamples>k__BackingField;
    private UnityEngine.FFTWindow <fftWindowType>k__BackingField;
    private Game.Audio.Radio.Radio+Spectrum+BandType <bandType>k__BackingField;
    private System.Single <equalizerBarSpacing>k__BackingField;
    private System.Single <equalizerSidesPadding>k__BackingField;

    public System.Boolean enableSpectrum { get; set; }
    public System.Int32 spectrumNumSamples { get; set; }
    public UnityEngine.FFTWindow fftWindowType { get; set; }
    public Game.Audio.Radio.Radio+Spectrum+BandType bandType { get; set; }
    public System.Single equalizerBarSpacing { get; set; }
    public System.Single equalizerSidesPadding { get; set; }

    public RadioSettings();

    public virtual System.Void Apply();
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private Game.Audio.Radio.Radio m_Radio`  

```csharp
private Game.Audio.Radio.Radio m_Radio;
```

- `private System.Boolean <enableSpectrum>k__BackingField`  

```csharp
private System.Boolean <enableSpectrum>k__BackingField;
```

- `private System.Int32 <spectrumNumSamples>k__BackingField`  

```csharp
private System.Int32 <spectrumNumSamples>k__BackingField;
```

- `private UnityEngine.FFTWindow <fftWindowType>k__BackingField`  

```csharp
private UnityEngine.FFTWindow <fftWindowType>k__BackingField;
```

- `private Game.Audio.Radio.Radio+Spectrum+BandType <bandType>k__BackingField`  

```csharp
private Game.Audio.Radio.Radio+Spectrum+BandType <bandType>k__BackingField;
```

- `private System.Single <equalizerBarSpacing>k__BackingField`  

```csharp
private System.Single <equalizerBarSpacing>k__BackingField;
```

- `private System.Single <equalizerSidesPadding>k__BackingField`  

```csharp
private System.Single <equalizerSidesPadding>k__BackingField;
```


## Properties

- `public System.Boolean enableSpectrum { get; set }`  

```csharp
public System.Boolean enableSpectrum { get; set; }
```

- `public System.Int32 spectrumNumSamples { get; set }`  

```csharp
public System.Int32 spectrumNumSamples { get; set; }
```

- `public UnityEngine.FFTWindow fftWindowType { get; set }`  

```csharp
public UnityEngine.FFTWindow fftWindowType { get; set; }
```

- `public Game.Audio.Radio.Radio+Spectrum+BandType bandType { get; set }`  

```csharp
public Game.Audio.Radio.Radio+Spectrum+BandType bandType { get; set; }
```

- `public System.Single equalizerBarSpacing { get; set }`  

```csharp
public System.Single equalizerBarSpacing { get; set; }
```

- `public System.Single equalizerSidesPadding { get; set }`  

```csharp
public System.Single equalizerSidesPadding { get; set; }
```


## Constructors

- `public RadioSettings()`  

```csharp
public RadioSettings();
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



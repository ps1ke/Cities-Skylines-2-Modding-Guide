# Game.Settings.RadioSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Fields

- `private Game.Audio.Radio.Radio m_Radio`  
- `private System.Boolean <enableSpectrum>k__BackingField`  
- `private System.Int32 <spectrumNumSamples>k__BackingField`  
- `private UnityEngine.FFTWindow <fftWindowType>k__BackingField`  
- `private Game.Audio.Radio.Radio+Spectrum+BandType <bandType>k__BackingField`  
- `private System.Single <equalizerBarSpacing>k__BackingField`  
- `private System.Single <equalizerSidesPadding>k__BackingField`  

## Properties

- `public System.Boolean enableSpectrum { get; set }`  
- `public System.Int32 spectrumNumSamples { get; set }`  
- `public UnityEngine.FFTWindow fftWindowType { get; set }`  
- `public Game.Audio.Radio.Radio+Spectrum+BandType bandType { get; set }`  
- `public System.Single equalizerBarSpacing { get; set }`  
- `public System.Single equalizerSidesPadding { get; set }`  

## Constructors

- `public RadioSettings()`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual SetDefaults() : System.Void`  


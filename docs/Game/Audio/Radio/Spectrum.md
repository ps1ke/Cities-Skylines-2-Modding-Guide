# Game.Audio.Radio.Radio+Spectrum

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Single[] m_SpectrumData`  
- `private Unity.Collections.NativeArray<System.Single> m_Frequencies`  
- `private System.Single m_Bandwidth`  
- `private UnityEngine.Vector4[] m_Levels`  
- `private UnityEngine.FFTWindow m_FFTWindow`  
- `private Game.Audio.Radio.Radio+Spectrum+BandType m_BandType`  
- `private UnityEngine.RenderTexture m_VURender`  
- `private UnityEngine.Material m_Equalizer`  
- `private UnityEngine.Rendering.RenderTargetIdentifier m_VURenderId`  
- `private static readonly System.Single[][] kMiddleFrequenciesForBands`  
- `private static readonly System.Single[] kBandwidthForBands`  
- `private static readonly System.String[] kKeywords`  
- `private static const System.Int32 kTexWidth`  
- `private static const System.Int32 kTexHeight`  

## Properties

- `public UnityEngine.Texture equalizerTexture { get }`  

## Constructors

- `public Spectrum()`  

## Methods

- `public Disable() : System.Void`  
- `public Enable(System.Int32 samplesCount, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing = 10, System.Single padding = 2) : System.Void`  
- `private SpectrumBlit(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera[] camera) : System.Void`  
- `public Update(UnityEngine.AudioSource source) : System.Void`  

## Nested types

- `Game.Audio.Radio.Radio+Spectrum+BandType`  
- `Game.Audio.Radio.Radio+Spectrum+CreateLevels`  


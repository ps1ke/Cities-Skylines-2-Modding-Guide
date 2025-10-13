# Game.Audio.Radio.Radio+Spectrum

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Spectrum
{
    private System.Single[] m_SpectrumData;
    private Unity.Collections.NativeArray<System.Single> m_Frequencies;
    private System.Single m_Bandwidth;
    private UnityEngine.Vector4[] m_Levels;
    private UnityEngine.FFTWindow m_FFTWindow;
    private Game.Audio.Radio.Radio+Spectrum+BandType m_BandType;
    private UnityEngine.RenderTexture m_VURender;
    private UnityEngine.Material m_Equalizer;
    private UnityEngine.Rendering.RenderTargetIdentifier m_VURenderId;
    private static readonly System.Single[][] kMiddleFrequenciesForBands;
    private static readonly System.Single[] kBandwidthForBands;
    private static readonly System.String[] kKeywords;
    private static const System.Int32 kTexWidth;
    private static const System.Int32 kTexHeight;

    public UnityEngine.Texture equalizerTexture { get; }

    public Spectrum();

    public System.Void Disable();
    public System.Void Enable(System.Int32 samplesCount, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding);
    private System.Void SpectrumBlit(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera[] camera);
    public System.Void Update(UnityEngine.AudioSource source);
}
```


## Fields

- `private System.Single[] m_SpectrumData`  

```csharp
private System.Single[] m_SpectrumData;
```

- `private Unity.Collections.NativeArray<System.Single> m_Frequencies`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Frequencies;
```

- `private System.Single m_Bandwidth`  

```csharp
private System.Single m_Bandwidth;
```

- `private UnityEngine.Vector4[] m_Levels`  

```csharp
private UnityEngine.Vector4[] m_Levels;
```

- `private UnityEngine.FFTWindow m_FFTWindow`  

```csharp
private UnityEngine.FFTWindow m_FFTWindow;
```

- `private Game.Audio.Radio.Radio+Spectrum+BandType m_BandType`  

```csharp
private Game.Audio.Radio.Radio+Spectrum+BandType m_BandType;
```

- `private UnityEngine.RenderTexture m_VURender`  

```csharp
private UnityEngine.RenderTexture m_VURender;
```

- `private UnityEngine.Material m_Equalizer`  

```csharp
private UnityEngine.Material m_Equalizer;
```

- `private UnityEngine.Rendering.RenderTargetIdentifier m_VURenderId`  

```csharp
private UnityEngine.Rendering.RenderTargetIdentifier m_VURenderId;
```

- `private static readonly System.Single[][] kMiddleFrequenciesForBands`  

```csharp
private static readonly System.Single[][] kMiddleFrequenciesForBands;
```

- `private static readonly System.Single[] kBandwidthForBands`  

```csharp
private static readonly System.Single[] kBandwidthForBands;
```

- `private static readonly System.String[] kKeywords`  

```csharp
private static readonly System.String[] kKeywords;
```

- `private static const System.Int32 kTexWidth`  

```csharp
private static const System.Int32 kTexWidth;
```

- `private static const System.Int32 kTexHeight`  

```csharp
private static const System.Int32 kTexHeight;
```


## Properties

- `public UnityEngine.Texture equalizerTexture { get }`  

```csharp
public UnityEngine.Texture equalizerTexture { get; }
```


## Constructors

- `public Spectrum()`  

```csharp
public Spectrum();
```


## Methods

- `public Disable() : System.Void`  

```csharp
public System.Void Disable();
```

- `public Enable(System.Int32 samplesCount, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing = 10, System.Single padding = 2) : System.Void`  

```csharp
public System.Void Enable(System.Int32 samplesCount, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding);
```

- `private SpectrumBlit(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera[] camera) : System.Void`  

```csharp
private System.Void SpectrumBlit(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera[] camera);
```

- `public Update(UnityEngine.AudioSource source) : System.Void`  

```csharp
public System.Void Update(UnityEngine.AudioSource source);
```


## Nested types

- `Game.Audio.Radio.Radio+Spectrum+BandType`  
- `Game.Audio.Radio.Radio+Spectrum+CreateLevels`  


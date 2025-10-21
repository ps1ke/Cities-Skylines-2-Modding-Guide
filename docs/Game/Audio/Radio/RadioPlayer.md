# Game.Audio.Radio.Radio+RadioPlayer

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class RadioPlayer : System.IDisposable
{
    private UnityEngine.Audio.AudioMixerGroup m_RadioGroup;
    private UnityEngine.AudioSource m_AudioSource;
    private System.Diagnostics.Stopwatch m_Timer;
    private System.Double m_Elapsed;
    private Game.Audio.Radio.Radio+Spectrum m_Spectrum;

    public System.Boolean isCreated { get; }
    public System.Boolean isPlaying { get; }
    public System.Int32 playbackPosition { get; }
    public System.Boolean muted { get; set; }
    public UnityEngine.Texture equalizerTexture { get; }
    public System.String currentClipName { get; }
    public UnityEngine.AudioClip currentClip { get; }

    public RadioPlayer(UnityEngine.Audio.AudioMixerGroup radioGroup);

    public System.Void Create(UnityEngine.GameObject listener);
    private UnityEngine.AudioSource CreateAudioSource(UnityEngine.GameObject listener);
    public System.Void Dispose();
    public System.Double GetAudioSourceDuration();
    public System.Double GetAudioSourceTimeElapsed();
    public System.Double GetAudioSourceTimeRemaining();
    public static System.Double GetDuration(UnityEngine.AudioClip clip);
    public System.Void Pause();
    public System.Void Play(UnityEngine.AudioClip clip, System.Int32 timeSamples);
    public System.Void Rewind();
    public System.Void SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding);
    public System.Void Unpause();
    public System.Void UpdateSpectrum();
}
```


## Fields

- `private UnityEngine.Audio.AudioMixerGroup m_RadioGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_RadioGroup;
```

- `private UnityEngine.AudioSource m_AudioSource`  

```csharp
private UnityEngine.AudioSource m_AudioSource;
```

- `private System.Diagnostics.Stopwatch m_Timer`  

```csharp
private System.Diagnostics.Stopwatch m_Timer;
```

- `private System.Double m_Elapsed`  

```csharp
private System.Double m_Elapsed;
```

- `private Game.Audio.Radio.Radio+Spectrum m_Spectrum`  

```csharp
private Game.Audio.Radio.Radio+Spectrum m_Spectrum;
```


## Properties

- `public System.Boolean isCreated { get }`  

```csharp
public System.Boolean isCreated { get; }
```

- `public System.Boolean isPlaying { get }`  

```csharp
public System.Boolean isPlaying { get; }
```

- `public System.Int32 playbackPosition { get }`  

```csharp
public System.Int32 playbackPosition { get; }
```

- `public System.Boolean muted { get; set }`  

```csharp
public System.Boolean muted { get; set; }
```

- `public UnityEngine.Texture equalizerTexture { get }`  

```csharp
public UnityEngine.Texture equalizerTexture { get; }
```

- `public System.String currentClipName { get }`  

```csharp
public System.String currentClipName { get; }
```

- `public UnityEngine.AudioClip currentClip { get }`  

```csharp
public UnityEngine.AudioClip currentClip { get; }
```


## Constructors

- `public RadioPlayer(UnityEngine.Audio.AudioMixerGroup radioGroup)`  

```csharp
public RadioPlayer(UnityEngine.Audio.AudioMixerGroup radioGroup);
```


## Methods

- `public Create(UnityEngine.GameObject listener) : System.Void`  

```csharp
public System.Void Create(UnityEngine.GameObject listener);
```

- `private CreateAudioSource(UnityEngine.GameObject listener) : UnityEngine.AudioSource`  

```csharp
private UnityEngine.AudioSource CreateAudioSource(UnityEngine.GameObject listener);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetAudioSourceDuration() : System.Double`  

```csharp
public System.Double GetAudioSourceDuration();
```

- `public GetAudioSourceTimeElapsed() : System.Double`  

```csharp
public System.Double GetAudioSourceTimeElapsed();
```

- `public GetAudioSourceTimeRemaining() : System.Double`  

```csharp
public System.Double GetAudioSourceTimeRemaining();
```

- `public static GetDuration(UnityEngine.AudioClip clip) : System.Double`  

```csharp
public static System.Double GetDuration(UnityEngine.AudioClip clip);
```

- `public Pause() : System.Void`  

```csharp
public System.Void Pause();
```

- `public Play(UnityEngine.AudioClip clip, System.Int32 timeSamples = 0) : System.Void`  

```csharp
public System.Void Play(UnityEngine.AudioClip clip, System.Int32 timeSamples);
```

- `public Rewind() : System.Void`  

```csharp
public System.Void Rewind();
```

- `public SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding) : System.Void`  

```csharp
public System.Void SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding);
```

- `public Unpause() : System.Void`  

```csharp
public System.Void Unpause();
```

- `public UpdateSpectrum() : System.Void`  

```csharp
public System.Void UpdateSpectrum();
```



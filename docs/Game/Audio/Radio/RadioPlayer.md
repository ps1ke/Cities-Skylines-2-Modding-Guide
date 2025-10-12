# Game.Audio.Radio.Radio+RadioPlayer

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private UnityEngine.Audio.AudioMixerGroup m_RadioGroup`  
- `private UnityEngine.AudioSource m_AudioSource`  
- `private System.Diagnostics.Stopwatch m_Timer`  
- `private System.Double m_Elapsed`  
- `private Game.Audio.Radio.Radio+Spectrum m_Spectrum`  

## Properties

- `public System.Boolean isCreated { get }`  
- `public System.Boolean isPlaying { get }`  
- `public System.Int32 playbackPosition { get }`  
- `public System.Boolean muted { get; set }`  
- `public UnityEngine.Texture equalizerTexture { get }`  
- `public System.String currentClipName { get }`  
- `public UnityEngine.AudioClip currentClip { get }`  

## Constructors

- `public RadioPlayer(UnityEngine.Audio.AudioMixerGroup radioGroup)`  

## Methods

- `public Create(UnityEngine.GameObject listener) : System.Void`  
- `private CreateAudioSource(UnityEngine.GameObject listener) : UnityEngine.AudioSource`  
- `public Dispose() : System.Void`  
- `public GetAudioSourceDuration() : System.Double`  
- `public GetAudioSourceTimeElapsed() : System.Double`  
- `public GetAudioSourceTimeRemaining() : System.Double`  
- `public static GetDuration(UnityEngine.AudioClip clip) : System.Double`  
- `public Pause() : System.Void`  
- `public Play(UnityEngine.AudioClip clip, System.Int32 timeSamples = 0) : System.Void`  
- `public Rewind() : System.Void`  
- `public SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding) : System.Void`  
- `public Unpause() : System.Void`  
- `public UpdateSpectrum() : System.Void`  


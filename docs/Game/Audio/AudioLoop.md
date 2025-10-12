# Game.Audio.AudioLoop

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.IO.AssetDatabase.AudioAsset m_Asset`  
- `private UnityEngine.AudioSource[] m_AudioSource`  
- `private System.Int32 m_ActiveAudioSource`  
- `private System.Double m_NextCheck`  
- `private UnityEngine.Audio.AudioMixerGroup m_group`  
- `private UnityEngine.Audio.AudioMixer m_Mixer`  
- `private System.Single m_FadeOutTime`  
- `private static const System.String kMenuCutoffProperty`  

## Properties

- `public System.Single volume { get; set }`  
- `public System.Boolean isPlaying { get }`  
- `public System.Double elapsedTime { get }`  

## Constructors

- `public AudioLoop(Colossal.IO.AssetDatabase.AudioAsset asset, UnityEngine.Audio.AudioMixer mixer, UnityEngine.Audio.AudioMixerGroup group)`  

## Methods

- `public Dispose() : System.Void`  
- `public FadeOut() : System.Void`  
- `public Start(System.Boolean useAlternativeStart = False) : System.Threading.Tasks.Task`  
- `public Stop() : System.Void`  
- `public Update(System.Double deltaTime) : System.Void`  

## Nested types

- `Game.Audio.AudioLoop+<Start>d__12`  


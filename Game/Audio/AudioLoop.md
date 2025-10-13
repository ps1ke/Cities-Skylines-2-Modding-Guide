# Game.Audio.AudioLoop

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AudioLoop
{
    private Colossal.IO.AssetDatabase.AudioAsset m_Asset;
    private UnityEngine.AudioSource[] m_AudioSource;
    private System.Int32 m_ActiveAudioSource;
    private System.Double m_NextCheck;
    private UnityEngine.Audio.AudioMixerGroup m_group;
    private UnityEngine.Audio.AudioMixer m_Mixer;
    private System.Single m_FadeOutTime;
    private static const System.String kMenuCutoffProperty;

    public System.Single volume { get; set; }
    public System.Boolean isPlaying { get; }
    public System.Double elapsedTime { get; }

    public AudioLoop(Colossal.IO.AssetDatabase.AudioAsset asset, UnityEngine.Audio.AudioMixer mixer, UnityEngine.Audio.AudioMixerGroup group);

    public System.Void Dispose();
    public System.Void FadeOut();
    public System.Threading.Tasks.Task Start(System.Boolean useAlternativeStart);
    public System.Void Stop();
    public System.Void Update(System.Double deltaTime);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.AudioAsset m_Asset`  

```csharp
private Colossal.IO.AssetDatabase.AudioAsset m_Asset;
```

- `private UnityEngine.AudioSource[] m_AudioSource`  

```csharp
private UnityEngine.AudioSource[] m_AudioSource;
```

- `private System.Int32 m_ActiveAudioSource`  

```csharp
private System.Int32 m_ActiveAudioSource;
```

- `private System.Double m_NextCheck`  

```csharp
private System.Double m_NextCheck;
```

- `private UnityEngine.Audio.AudioMixerGroup m_group`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_group;
```

- `private UnityEngine.Audio.AudioMixer m_Mixer`  

```csharp
private UnityEngine.Audio.AudioMixer m_Mixer;
```

- `private System.Single m_FadeOutTime`  

```csharp
private System.Single m_FadeOutTime;
```

- `private static const System.String kMenuCutoffProperty`  

```csharp
private static const System.String kMenuCutoffProperty;
```


## Properties

- `public System.Single volume { get; set }`  

```csharp
public System.Single volume { get; set; }
```

- `public System.Boolean isPlaying { get }`  

```csharp
public System.Boolean isPlaying { get; }
```

- `public System.Double elapsedTime { get }`  

```csharp
public System.Double elapsedTime { get; }
```


## Constructors

- `public AudioLoop(Colossal.IO.AssetDatabase.AudioAsset asset, UnityEngine.Audio.AudioMixer mixer, UnityEngine.Audio.AudioMixerGroup group)`  

```csharp
public AudioLoop(Colossal.IO.AssetDatabase.AudioAsset asset, UnityEngine.Audio.AudioMixer mixer, UnityEngine.Audio.AudioMixerGroup group);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FadeOut() : System.Void`  

```csharp
public System.Void FadeOut();
```

- `public Start(System.Boolean useAlternativeStart = False) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Start(System.Boolean useAlternativeStart);
```

- `public Stop() : System.Void`  

```csharp
public System.Void Stop();
```

- `public Update(System.Double deltaTime) : System.Void`  

```csharp
public System.Void Update(System.Double deltaTime);
```


## Nested types

- `Game.Audio.AudioLoop+<Start>d__12`  


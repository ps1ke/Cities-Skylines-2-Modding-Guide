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
public AudioLoop(AudioAsset asset, AudioMixer mixer, AudioMixerGroup group)
	{
		m_Asset = asset;
		m_group = group;
		m_Mixer = mixer;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		Stop();
		m_NextCheck = -1.0;
		if (m_AudioSource != null)
		{
			if (m_AudioSource.Length > 1 && m_AudioSource[1] != null)
			{
				Object.Destroy(m_AudioSource[1].clip);
			}
			if (m_AudioSource[0] != null)
			{
				Object.Destroy(m_AudioSource[0].clip);
				Object.Destroy(m_AudioSource[0].gameObject);
			}
			m_AudioSource = null;
		}
	}
```

- `public FadeOut() : System.Void`  

```csharp
public void FadeOut()
	{
		m_FadeOutTime = m_Asset.fadeoutTime;
	}
```

- `public Start(System.Boolean useAlternativeStart = False) : System.Threading.Tasks.Task`  

```csharp
public async Task Start(bool useAlternativeStart = false)
	{
		m_FadeOutTime = 0f;
		m_Mixer.SetFloat("MenuCutoff", 22000f);
		AudioClip audioClip = await m_Asset.LoadAsync(useCached: false);
		if (!(audioClip != null))
		{
			return;
		}
		m_NextCheck = -1.0;
		m_ActiveAudioSource = 0;
		if (m_AudioSource == null)
		{
			m_AudioSource = new AudioSource[(!m_Asset.hasLoop) ? 1 : 2];
			GameObject go = new GameObject("MenuAudioSource");
			m_AudioSource[0] = go.AddComponent<AudioSource>();
			m_AudioSource[0].outputAudioMixerGroup = m_group;
			m_AudioSource[0].dopplerLevel = 0f;
			m_AudioSource[0].playOnAwake = false;
			m_AudioSource[0].spatialBlend = 0f;
			m_AudioSource[0].loop = !m_Asset.hasLoop;
			m_AudioSource[0].clip = audioClip;
			if (m_Asset.hasLoop)
			{
				AudioClip clip = await m_Asset.LoadAsync(useCached: false);
				m_AudioSource[1] = go.AddComponent<AudioSource>();
				m_AudioSource[1].outputAudioMixerGroup = m_group;
				m_AudioSource[1].dopplerLevel = 0f;
				m_AudioSource[1].playOnAwake = false;
				m_AudioSource[1].spatialBlend = 0f;
				m_AudioSource[1].loop = false;
				m_AudioSource[1].clip = clip;
			}
		}
		m_AudioSource[0].volume = 1f;
		if (useAlternativeStart && m_Asset.hasAlternativeStart)
		{
			m_AudioSource[0].timeSamples = (int)(m_Asset.alternativeStart * (double)m_AudioSource[0].clip.frequency);
		}
		if (m_Asset.hasLoop)
		{
			m_AudioSource[1].volume = 1f;
			m_NextCheck = AudioSettings.dspTime + m_Asset.loopEnd;
			if (useAlternativeStart && m_Asset.hasAlternativeStart)
			{
				m_NextCheck -= m_Asset.alternativeStart;
			}
		}
		m_AudioSource[0].PlayScheduled(AudioSettings.dspTime);
	}
```

- `public Stop() : System.Void`  

```csharp
public void Stop()
	{
		if (m_AudioSource == null)
		{
			return;
		}
		AudioSource[] audioSource = m_AudioSource;
		foreach (AudioSource audioSource2 in audioSource)
		{
			if (audioSource2 != null)
			{
				audioSource2.Stop();
			}
		}
	}
```

- `public Update(System.Double deltaTime) : System.Void`  

```csharp
public void Update(double deltaTime)
	{
		if (m_AudioSource != null)
		{
			if (m_Asset.hasLoop && m_NextCheck != -1.0 && AudioSettings.dspTime > m_NextCheck - 5.0)
			{
				int num = 1 - m_ActiveAudioSource;
				m_AudioSource[m_ActiveAudioSource].SetScheduledEndTime(m_NextCheck);
				m_AudioSource[num].timeSamples = (int)(m_Asset.loopStart * (double)m_AudioSource[num].clip.frequency);
				m_AudioSource[num].PlayScheduled(m_NextCheck);
				m_ActiveAudioSource = num;
				m_NextCheck += m_Asset.loopDuration;
			}
			if (m_FadeOutTime > 0f)
			{
				m_FadeOutTime -= (float)deltaTime;
				m_Mixer.SetFloat("MenuCutoff", math.lerp(400f, 22000f, math.saturate(math.pow(m_FadeOutTime, 3f))));
				volume = ((m_Asset.fadeoutTime > 0f) ? (m_FadeOutTime / m_Asset.fadeoutTime) : 0f);
			}
			else if (m_FadeOutTime < 0f)
			{
				Dispose();
			}
		}
	}
```


## Nested types

- `Game.Audio.AudioLoop+<Start>d__12`  


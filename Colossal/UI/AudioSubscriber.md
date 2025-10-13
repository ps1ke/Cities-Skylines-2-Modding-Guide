# Colossal.UI.AudioSubscriber

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class AudioSubscriber : System.IDisposable
{
    private Colossal.UI.UIView m_View;
    private UnityEngine.AudioClip m_AudioClip;
    private System.Single[] m_AudioClipSamples;
    private System.Int32 m_BufferPosition;
    private System.Single[] m_AudioBuffer;
    private System.Boolean m_AutoPlayOnDataReceived;
    private System.Int32 ptrSize;
    private System.Collections.Generic.HashSet<System.Int32> StreamIds;
    private static Colossal.Logging.ILog log;
    private static const System.Int32 kMaxBufferSize;
    private static const System.Int32 kPreBufferSize;

    public AudioSubscriber(Colossal.UI.UIView view);

    private System.Void <LoadReceivedAudioSamples>g__SetAudioClipSamples|15_0(System.Int32 length, System.Int32 offset, System.Int32 startPosition, Colossal.UI.AudioSubscriber+<>c__DisplayClass15_0& );
    private System.Void AutoPlayStream(System.Int32 id);
    private System.Void CreateStream(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate);
    private System.Void DestroyStream(System.Int32 id);
    public System.Void Dispose();
    private System.Void LoadReceivedAudioSamples(System.Int32 samples, System.IntPtr pcm, System.Int32 channels);
    private System.Void ReceiveDataForStream(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels);
    private System.Void StopStream(System.Int32 id);
    public System.Void Subscribe();
    private System.Void SynchronizeAudioAndVideo();
    private System.Void VolumeChanged(System.Int32 id, System.Single volume);
}
```


## Fields

- `private Colossal.UI.UIView m_View`  

```csharp
private Colossal.UI.UIView m_View;
```

- `private UnityEngine.AudioClip m_AudioClip`  

```csharp
private UnityEngine.AudioClip m_AudioClip;
```

- `private System.Single[] m_AudioClipSamples`  

```csharp
private System.Single[] m_AudioClipSamples;
```

- `private System.Int32 m_BufferPosition`  

```csharp
private System.Int32 m_BufferPosition;
```

- `private System.Single[] m_AudioBuffer`  

```csharp
private System.Single[] m_AudioBuffer;
```

- `private System.Boolean m_AutoPlayOnDataReceived`  

```csharp
private System.Boolean m_AutoPlayOnDataReceived;
```

- `private System.Int32 ptrSize`  

```csharp
private System.Int32 ptrSize;
```

- `private System.Collections.Generic.HashSet<System.Int32> StreamIds`  

```csharp
private System.Collections.Generic.HashSet<System.Int32> StreamIds;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.Int32 kMaxBufferSize`  

```csharp
private static const System.Int32 kMaxBufferSize;
```

- `private static const System.Int32 kPreBufferSize`  

```csharp
private static const System.Int32 kPreBufferSize;
```


## Constructors

- `public AudioSubscriber(Colossal.UI.UIView view)`  

```csharp
public AudioSubscriber(Colossal.UI.UIView view);
```


## Methods

- `private <LoadReceivedAudioSamples>g__SetAudioClipSamples|15_0(System.Int32 length, System.Int32 offset, System.Int32 startPosition, Colossal.UI.AudioSubscriber+<>c__DisplayClass15_0& ) : System.Void`  

```csharp
private System.Void <LoadReceivedAudioSamples>g__SetAudioClipSamples|15_0(System.Int32 length, System.Int32 offset, System.Int32 startPosition, Colossal.UI.AudioSubscriber+<>c__DisplayClass15_0& );
```

- `private AutoPlayStream(System.Int32 id) : System.Void`  

```csharp
private System.Void AutoPlayStream(System.Int32 id);
```

- `private CreateStream(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate) : System.Void`  

```csharp
private System.Void CreateStream(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate);
```

- `private DestroyStream(System.Int32 id) : System.Void`  

```csharp
private System.Void DestroyStream(System.Int32 id);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private LoadReceivedAudioSamples(System.Int32 samples, System.IntPtr pcm, System.Int32 channels) : System.Void`  

```csharp
private System.Void LoadReceivedAudioSamples(System.Int32 samples, System.IntPtr pcm, System.Int32 channels);
```

- `private ReceiveDataForStream(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels) : System.Void`  

```csharp
private System.Void ReceiveDataForStream(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels);
```

- `private StopStream(System.Int32 id) : System.Void`  

```csharp
private System.Void StopStream(System.Int32 id);
```

- `public Subscribe() : System.Void`  

```csharp
public System.Void Subscribe();
```

- `private SynchronizeAudioAndVideo() : System.Void`  

```csharp
private System.Void SynchronizeAudioAndVideo();
```

- `private VolumeChanged(System.Int32 id, System.Single volume) : System.Void`  

```csharp
private System.Void VolumeChanged(System.Int32 id, System.Single volume);
```


## Nested types

- `Colossal.UI.AudioSubscriber+<>c__DisplayClass15_0`  


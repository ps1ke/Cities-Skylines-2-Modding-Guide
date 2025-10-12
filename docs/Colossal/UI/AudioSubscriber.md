# Colossal.UI.AudioSubscriber

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.UIView m_View`  
- `private UnityEngine.AudioClip m_AudioClip`  
- `private System.Single[] m_AudioClipSamples`  
- `private System.Int32 m_BufferPosition`  
- `private System.Single[] m_AudioBuffer`  
- `private System.Boolean m_AutoPlayOnDataReceived`  
- `private System.Int32 ptrSize`  
- `private System.Collections.Generic.HashSet<System.Int32> StreamIds`  
- `private static Colossal.Logging.ILog log`  
- `private static const System.Int32 kMaxBufferSize`  
- `private static const System.Int32 kPreBufferSize`  

## Constructors

- `public AudioSubscriber(Colossal.UI.UIView view)`  

## Methods

- `private <LoadReceivedAudioSamples>g__SetAudioClipSamples|15_0(System.Int32 length, System.Int32 offset, System.Int32 startPosition, Colossal.UI.AudioSubscriber+<>c__DisplayClass15_0& ) : System.Void`  
- `private AutoPlayStream(System.Int32 id) : System.Void`  
- `private CreateStream(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate) : System.Void`  
- `private DestroyStream(System.Int32 id) : System.Void`  
- `public Dispose() : System.Void`  
- `private LoadReceivedAudioSamples(System.Int32 samples, System.IntPtr pcm, System.Int32 channels) : System.Void`  
- `private ReceiveDataForStream(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels) : System.Void`  
- `private StopStream(System.Int32 id) : System.Void`  
- `public Subscribe() : System.Void`  
- `private SynchronizeAudioAndVideo() : System.Void`  
- `private VolumeChanged(System.Int32 id, System.Single volume) : System.Void`  

## Nested types

- `Colossal.UI.AudioSubscriber+<>c__DisplayClass15_0`  


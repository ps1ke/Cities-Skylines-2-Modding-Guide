# Game.Audio.Radio.BpmAnalyzer

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class BpmAnalyzer
{
    private static Colossal.Logging.ILog log;
    private static Game.Audio.Radio.BpmAnalyzer+BpmMatchData[] bpmMatchDatas;
    private static const System.Int32 MIN_BPM;
    private static const System.Int32 MAX_BPM;
    private static const System.Int32 BASE_FREQUENCY;
    private static const System.Int32 BASE_CHANNELS;
    private static const System.Int32 BASE_SPLIT_SAMPLE_SIZE;

    public BpmAnalyzer();

    public static System.Int32 AnalyzeBpm(UnityEngine.AudioClip clip);
    private static System.Single[] CreateVolumeArray(System.Single[] allSamples, System.Int32 frequency, System.Int32 channels, System.Int32 splitFrameSize);
    private static System.Int32 SearchBpm(System.Single[] volumeArr, System.Int32 frequency, System.Int32 splitFrameSize);
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static Game.Audio.Radio.BpmAnalyzer+BpmMatchData[] bpmMatchDatas`  

```csharp
private static Game.Audio.Radio.BpmAnalyzer+BpmMatchData[] bpmMatchDatas;
```

- `private static const System.Int32 MIN_BPM`  

```csharp
private static const System.Int32 MIN_BPM;
```

- `private static const System.Int32 MAX_BPM`  

```csharp
private static const System.Int32 MAX_BPM;
```

- `private static const System.Int32 BASE_FREQUENCY`  

```csharp
private static const System.Int32 BASE_FREQUENCY;
```

- `private static const System.Int32 BASE_CHANNELS`  

```csharp
private static const System.Int32 BASE_CHANNELS;
```

- `private static const System.Int32 BASE_SPLIT_SAMPLE_SIZE`  

```csharp
private static const System.Int32 BASE_SPLIT_SAMPLE_SIZE;
```


## Constructors

- `public BpmAnalyzer()`  

```csharp
public BpmAnalyzer();
```


## Methods

- `public static AnalyzeBpm(UnityEngine.AudioClip clip) : System.Int32`  

```csharp
public static System.Int32 AnalyzeBpm(UnityEngine.AudioClip clip);
```

- `private static CreateVolumeArray(System.Single[] allSamples, System.Int32 frequency, System.Int32 channels, System.Int32 splitFrameSize) : System.Single[]`  

```csharp
private static System.Single[] CreateVolumeArray(System.Single[] allSamples, System.Int32 frequency, System.Int32 channels, System.Int32 splitFrameSize);
```

- `private static SearchBpm(System.Single[] volumeArr, System.Int32 frequency, System.Int32 splitFrameSize) : System.Int32`  

```csharp
private static System.Int32 SearchBpm(System.Single[] volumeArr, System.Int32 frequency, System.Int32 splitFrameSize);
```


## Nested types

- `Game.Audio.Radio.BpmAnalyzer+BpmMatchData`  
- `Game.Audio.Radio.BpmAnalyzer+<>c`  


# Game.Audio.Radio.BpmAnalyzer

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private static Colossal.Logging.ILog log`  
- `private static Game.Audio.Radio.BpmAnalyzer+BpmMatchData[] bpmMatchDatas`  
- `private static const System.Int32 MIN_BPM`  
- `private static const System.Int32 MAX_BPM`  
- `private static const System.Int32 BASE_FREQUENCY`  
- `private static const System.Int32 BASE_CHANNELS`  
- `private static const System.Int32 BASE_SPLIT_SAMPLE_SIZE`  

## Constructors

- `public BpmAnalyzer()`  

## Methods

- `public static AnalyzeBpm(UnityEngine.AudioClip clip) : System.Int32`  
- `private static CreateVolumeArray(System.Single[] allSamples, System.Int32 frequency, System.Int32 channels, System.Int32 splitFrameSize) : System.Single[]`  
- `private static SearchBpm(System.Single[] volumeArr, System.Int32 frequency, System.Int32 splitFrameSize) : System.Int32`  

## Nested types

- `Game.Audio.Radio.BpmAnalyzer+BpmMatchData`  
- `Game.Audio.Radio.BpmAnalyzer+<>c`  


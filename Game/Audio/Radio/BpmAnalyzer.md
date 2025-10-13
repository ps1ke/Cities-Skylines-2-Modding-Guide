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
public static int AnalyzeBpm(AudioClip clip)
	{
		for (int i = 0; i < bpmMatchDatas.Length; i++)
		{
			bpmMatchDatas[i].match = 0f;
		}
		if (clip == null)
		{
			return -1;
		}
		log.InfoFormat("AnalyzeBpm audioClipName: {0}", clip.name);
		int frequency = clip.frequency;
		log.InfoFormat("Frequency: {0}", frequency);
		int channels = clip.channels;
		log.InfoFormat("Channels: {0}", channels);
		int splitFrameSize = Mathf.FloorToInt((float)frequency / 44100f * ((float)channels / 2f) * 2205f);
		float[] array = new float[clip.samples * channels];
		clip.GetData(array, 0);
		int num = SearchBpm(CreateVolumeArray(array, frequency, channels, splitFrameSize), frequency, splitFrameSize);
		log.InfoFormat("Matched BPM: {0}", num);
		StringBuilder stringBuilder = new StringBuilder("BPM Match Data List\n");
		for (int j = 0; j < bpmMatchDatas.Length; j++)
		{
			stringBuilder.Append("bpm : " + bpmMatchDatas[j].bpm + ", match : " + Mathf.FloorToInt(bpmMatchDatas[j].match * 10000f) + "\n");
		}
		log.Info(stringBuilder.ToString());
		return num;
	}
```

- `private static CreateVolumeArray(System.Single[] allSamples, System.Int32 frequency, System.Int32 channels, System.Int32 splitFrameSize) : System.Single[]`  

```csharp
private static float[] CreateVolumeArray(float[] allSamples, int frequency, int channels, int splitFrameSize)
	{
		float[] array = new float[Mathf.CeilToInt((float)allSamples.Length / (float)splitFrameSize)];
		int num = 0;
		for (int i = 0; i < allSamples.Length; i += splitFrameSize)
		{
			float num2 = 0f;
			for (int j = i; j < i + splitFrameSize && allSamples.Length > j; j++)
			{
				float num3 = Mathf.Abs(allSamples[j]);
				if (!(num3 > 1f))
				{
					num2 += num3 * num3;
				}
			}
			array[num] = Mathf.Sqrt(num2 / (float)splitFrameSize);
			num++;
		}
		float num4 = array.Max();
		for (int k = 0; k < array.Length; k++)
		{
			array[k] /= num4;
		}
		return array;
	}
```

- `private static SearchBpm(System.Single[] volumeArr, System.Int32 frequency, System.Int32 splitFrameSize) : System.Int32`  

```csharp
private static int SearchBpm(float[] volumeArr, int frequency, int splitFrameSize)
	{
		List<float> list = new List<float>();
		for (int i = 1; i < volumeArr.Length; i++)
		{
			list.Add(Mathf.Max(volumeArr[i] - volumeArr[i - 1], 0f));
		}
		int num = 0;
		float num2 = (float)frequency / (float)splitFrameSize;
		for (int j = 60; j <= 400; j++)
		{
			float num3 = 0f;
			float num4 = 0f;
			float num5 = (float)j / 60f;
			if (list.Count > 0)
			{
				for (int k = 0; k < list.Count; k++)
				{
					num3 += list[k] * Mathf.Cos((float)k * 2f * MathF.PI * num5 / num2);
					num4 += list[k] * Mathf.Sin((float)k * 2f * MathF.PI * num5 / num2);
				}
				num3 *= 1f / (float)list.Count;
				num4 *= 1f / (float)list.Count;
			}
			float match = Mathf.Sqrt(num3 * num3 + num4 * num4);
			bpmMatchDatas[num].bpm = j;
			bpmMatchDatas[num].match = match;
			num++;
		}
		int num6 = Array.FindIndex(bpmMatchDatas, (BpmMatchData x) => x.match == bpmMatchDatas.Max((BpmMatchData y) => y.match));
		return bpmMatchDatas[num6].bpm;
	}
```


## Nested types

- `Game.Audio.Radio.BpmAnalyzer+BpmMatchData`  
- `Game.Audio.Radio.BpmAnalyzer+<>c`  


# Game.Debug.ProfilerMetricsDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class ProfilerMetricsDebugUI : System.IDisposable
{
    private System.Collections.Generic.List<Game.Debug.ProfilerMetricsDebugUI+StatInfo> m_AvailableStats;

    public ProfilerMetricsDebugUI();

    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildProfilerMetricsDebugUI();
    private System.Void CollectProfilerMetrics();
    public System.Void Dispose();
    private System.Void DisposeProfilerMetrics();
    private static System.Double GetRecorderFrameAverage(Unity.Profiling.ProfilerRecorder recorder);
}
```


## Fields

- `private System.Collections.Generic.List<Game.Debug.ProfilerMetricsDebugUI+StatInfo> m_AvailableStats`  

```csharp
private System.Collections.Generic.List<Game.Debug.ProfilerMetricsDebugUI+StatInfo> m_AvailableStats;
```


## Constructors

- `public ProfilerMetricsDebugUI()`  

```csharp
public ProfilerMetricsDebugUI()
	{
		CollectProfilerMetrics();
	}
```


## Methods

- `private BuildProfilerMetricsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildProfilerMetricsDebugUI()
	{
		List<DebugUI.Widget> list = new List<DebugUI.Widget>();
		Dictionary<string, DebugUI.Foldout> dictionary = new Dictionary<string, DebugUI.Foldout>();
		foreach (StatInfo stat in m_AvailableStats)
		{
			if (!dictionary.TryGetValue(stat.categoryName, out var value))
			{
				value = new DebugUI.Foldout
				{
					displayName = stat.categoryName
				};
				list.Add(value);
				dictionary.Add(stat.categoryName, value);
			}
			ProfilerRecorder profilerRecorder = stat.profilerRecorder;
			switch (profilerRecorder.UnitType)
			{
			case ProfilerMarkerDataUnit.Bytes:
				value.children.Add(new DebugUI.Value
				{
					displayName = stat.name,
					getter = delegate
					{
						ProfilerRecorder profilerRecorder2 = stat.profilerRecorder;
						return FormatUtils.FormatBytes(profilerRecorder2.LastValue);
					}
				});
				break;
			case ProfilerMarkerDataUnit.TimeNanoseconds:
				value.children.Add(new DebugUI.Value
				{
					displayName = stat.name,
					getter = () => $"{GetRecorderFrameAverage(stat.profilerRecorder) * 9.999999974752427E-07:F2}ms"
				});
				break;
			case ProfilerMarkerDataUnit.Count:
				value.children.Add(new DebugUI.Value
				{
					displayName = stat.name,
					getter = delegate
					{
						ProfilerRecorder profilerRecorder2 = stat.profilerRecorder;
						return profilerRecorder2.Count;
					}
				});
				break;
			case ProfilerMarkerDataUnit.FrequencyHz:
				value.children.Add(new DebugUI.Value
				{
					displayName = stat.name,
					getter = delegate
					{
						ProfilerRecorder profilerRecorder2 = stat.profilerRecorder;
						return $"{profilerRecorder2.LastValue}Hz";
					}
				});
				break;
			case ProfilerMarkerDataUnit.Percent:
				value.children.Add(new DebugUI.Value
				{
					displayName = stat.name,
					getter = delegate
					{
						ProfilerRecorder profilerRecorder2 = stat.profilerRecorder;
						return $"{profilerRecorder2.LastValue}%";
					}
				});
				break;
			}
		}
		return list;
	}
```

- `private CollectProfilerMetrics() : System.Void`  

```csharp
private void CollectProfilerMetrics()
	{
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Total Used Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Total Reserved Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "GC Used Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "GC Reserved Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Gfx Used Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Gfx Reserved Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Audio Used Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Audio Reserved Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Video Used Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Video Reserved Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Profiler Used Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "Profiler Reserved Memory"));
		m_AvailableStats.Add(new StatInfo("Memory", ProfilerCategory.Memory, "System Used Memory"));
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		DisposeProfilerMetrics();
	}
```

- `private DisposeProfilerMetrics() : System.Void`  

```csharp
private void DisposeProfilerMetrics()
	{
		foreach (StatInfo availableStat in m_AvailableStats)
		{
			availableStat.profilerRecorder.Dispose();
		}
		m_AvailableStats.Clear();
	}
```

- `private static GetRecorderFrameAverage(Unity.Profiling.ProfilerRecorder recorder) : System.Double`  

```csharp
private unsafe static double GetRecorderFrameAverage(ProfilerRecorder recorder)
	{
		int capacity = recorder.Capacity;
		if (capacity == 0)
		{
			return 0.0;
		}
		double num = 0.0;
		ProfilerRecorderSample* ptr = stackalloc ProfilerRecorderSample[capacity];
		recorder.CopyTo(ptr, capacity);
		for (int i = 0; i < capacity; i++)
		{
			num += (double)ptr[i].Value;
		}
		return num / (double)capacity;
	}
```


## Nested types

- `Game.Debug.ProfilerMetricsDebugUI+StatInfo`  
- `Game.Debug.ProfilerMetricsDebugUI+<>c__DisplayClass7_0`  


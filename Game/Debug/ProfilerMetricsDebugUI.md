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
public ProfilerMetricsDebugUI();
```


## Methods

- `private BuildProfilerMetricsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildProfilerMetricsDebugUI();
```

- `private CollectProfilerMetrics() : System.Void`  

```csharp
private System.Void CollectProfilerMetrics();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private DisposeProfilerMetrics() : System.Void`  

```csharp
private System.Void DisposeProfilerMetrics();
```

- `private static GetRecorderFrameAverage(Unity.Profiling.ProfilerRecorder recorder) : System.Double`  

```csharp
private static System.Double GetRecorderFrameAverage(Unity.Profiling.ProfilerRecorder recorder);
```


## Nested types

- `Game.Debug.ProfilerMetricsDebugUI+StatInfo`  
- `Game.Debug.ProfilerMetricsDebugUI+<>c__DisplayClass7_0`  


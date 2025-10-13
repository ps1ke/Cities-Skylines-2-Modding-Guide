# Game.Rendering.Utilities.AdaptiveDynamicResolutionScale

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AdaptiveDynamicResolutionScale
{
    private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField;
    private System.Boolean <isEnabled>k__BackingField;
    private System.Boolean <isAdaptive>k__BackingField;
    private System.Single <minScale>k__BackingField;
    public System.Single DefaultTargetFrameRate;
    public System.Int32 EvaluationFrameCount;
    public System.UInt32 ScaleUpDuration;
    public System.UInt32 ScaleDownDuration;
    public System.Int32 ScaleUpStepCount;
    public System.Int32 ScaleDownStepCount;
    private System.Single m_AccumGPUFrameTime;
    private System.Single m_GPULimitedFrames;
    private System.Int32 m_CurrentFrameSlot;
    private System.UInt32 m_ScaleUpCounter;
    private System.UInt32 m_ScaleDownCounter;
    private System.Boolean m_Initialized;
    private System.UInt32 m_InitialFrameCounter;
    private System.Single m_AvgGPUTime;
    private System.Single m_AvgGPULimited;
    private static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale s_Instance;
    private static System.Single s_CurrentScaleFraction;
    private static const System.UInt32 InitialFramesToSkip;

    public static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale instance { get; }
    public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; private set; }
    public System.Boolean isEnabled { get; private set; }
    public System.Boolean isAdaptive { get; private set; }
    public System.Single minScale { get; private set; }
    public System.Single currentScale { get; }
    public System.String debugState { get; }

    public AdaptiveDynamicResolutionScale();

    public static System.Void Dispose();
    private static UnityEngine.Rendering.DynamicResUpscaleFilter GetFilterFromUiEnum(Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter);
    private static System.Boolean IsGpuBottleneck(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime);
    private static System.Void ResetScale();
    public System.Void SetParams(System.Boolean enabled, System.Boolean adaptive, System.Single minScale, Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter, UnityEngine.Camera camera);
    public System.Void UpdateDRS(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime);
}
```


## Fields

- `private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField`  

```csharp
private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField;
```

- `private System.Boolean <isEnabled>k__BackingField`  

```csharp
private System.Boolean <isEnabled>k__BackingField;
```

- `private System.Boolean <isAdaptive>k__BackingField`  

```csharp
private System.Boolean <isAdaptive>k__BackingField;
```

- `private System.Single <minScale>k__BackingField`  

```csharp
private System.Single <minScale>k__BackingField;
```

- `public System.Single DefaultTargetFrameRate`  

```csharp
public System.Single DefaultTargetFrameRate;
```

- `public System.Int32 EvaluationFrameCount`  

```csharp
public System.Int32 EvaluationFrameCount;
```

- `public System.UInt32 ScaleUpDuration`  

```csharp
public System.UInt32 ScaleUpDuration;
```

- `public System.UInt32 ScaleDownDuration`  

```csharp
public System.UInt32 ScaleDownDuration;
```

- `public System.Int32 ScaleUpStepCount`  

```csharp
public System.Int32 ScaleUpStepCount;
```

- `public System.Int32 ScaleDownStepCount`  

```csharp
public System.Int32 ScaleDownStepCount;
```

- `private System.Single m_AccumGPUFrameTime`  

```csharp
private System.Single m_AccumGPUFrameTime;
```

- `private System.Single m_GPULimitedFrames`  

```csharp
private System.Single m_GPULimitedFrames;
```

- `private System.Int32 m_CurrentFrameSlot`  

```csharp
private System.Int32 m_CurrentFrameSlot;
```

- `private System.UInt32 m_ScaleUpCounter`  

```csharp
private System.UInt32 m_ScaleUpCounter;
```

- `private System.UInt32 m_ScaleDownCounter`  

```csharp
private System.UInt32 m_ScaleDownCounter;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.UInt32 m_InitialFrameCounter`  

```csharp
private System.UInt32 m_InitialFrameCounter;
```

- `private System.Single m_AvgGPUTime`  

```csharp
private System.Single m_AvgGPUTime;
```

- `private System.Single m_AvgGPULimited`  

```csharp
private System.Single m_AvgGPULimited;
```

- `private static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale s_Instance`  

```csharp
private static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale s_Instance;
```

- `private static System.Single s_CurrentScaleFraction`  

```csharp
private static System.Single s_CurrentScaleFraction;
```

- `private static const System.UInt32 InitialFramesToSkip`  

```csharp
private static const System.UInt32 InitialFramesToSkip;
```


## Properties

- `public static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale instance { get }`  

```csharp
public static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale instance { get; }
```

- `public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; private set }`  

```csharp
public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; private set; }
```

- `public System.Boolean isEnabled { get; private set }`  

```csharp
public System.Boolean isEnabled { get; private set; }
```

- `public System.Boolean isAdaptive { get; private set }`  

```csharp
public System.Boolean isAdaptive { get; private set; }
```

- `public System.Single minScale { get; private set }`  

```csharp
public System.Single minScale { get; private set; }
```

- `public System.Single currentScale { get }`  

```csharp
public System.Single currentScale { get; }
```

- `public System.String debugState { get }`  

```csharp
public System.String debugState { get; }
```


## Constructors

- `public AdaptiveDynamicResolutionScale()`  

```csharp
public AdaptiveDynamicResolutionScale();
```


## Methods

- `public static Dispose() : System.Void`  

```csharp
public static void Dispose()
	{
		ResetScale();
		s_Instance = null;
	}
```

- `private static GetFilterFromUiEnum(Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter) : UnityEngine.Rendering.DynamicResUpscaleFilter`  

```csharp
private static DynamicResUpscaleFilter GetFilterFromUiEnum(DynResUpscaleFilter filter)
	{
		return filter switch
		{
			DynResUpscaleFilter.CatmullRom => DynamicResUpscaleFilter.CatmullRom, 
			DynResUpscaleFilter.EdgeAdaptiveScaling => DynamicResUpscaleFilter.EdgeAdaptiveScalingUpres, 
			DynResUpscaleFilter.ContrastAdaptiveSharpen => DynamicResUpscaleFilter.TAAU, 
			DynResUpscaleFilter.TAAU => DynamicResUpscaleFilter.ContrastAdaptiveSharpen, 
			_ => throw new NotSupportedException($"{filter} is not a supported upscaler"), 
		};
	}
```

- `private static IsGpuBottleneck(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime) : System.Boolean`  

```csharp
private static bool IsGpuBottleneck(float fullFrameTime, float mainThreadCpuTime, float renderThreadCpuTime, float gpuTime)
	{
		if (gpuTime == 0f || mainThreadCpuTime == 0f)
		{
			return false;
		}
		float num = fullFrameTime * 0.8f;
		if (gpuTime > num && mainThreadCpuTime < num)
		{
			return renderThreadCpuTime < num;
		}
		return false;
	}
```

- `private static ResetScale() : System.Void`  

```csharp
private static void ResetScale()
	{
		s_CurrentScaleFraction = 1f;
	}
```

- `public SetParams(System.Boolean enabled, System.Boolean adaptive, System.Single minScale, Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter, UnityEngine.Camera camera) : System.Void`  

```csharp
public void SetParams(bool enabled, bool adaptive, float minScale, DynResUpscaleFilter filter, Camera camera)
	{
		isEnabled = enabled;
		isAdaptive = adaptive;
		this.minScale = minScale;
		upscaleFilter = filter;
		if (camera != null)
		{
			if (!SharedSettings.instance.graphics.isDlssActive && !SharedSettings.instance.graphics.isFsr2Active)
			{
				HDAdditionalCameraData component = camera.GetComponent<HDAdditionalCameraData>();
				component.allowDeepLearningSuperSampling = false;
				component.allowFidelityFX2SuperResolution = false;
				DynamicResolutionHandler.SetUpscaleFilter(camera, (!enabled) ? DynamicResUpscaleFilter.CatmullRom : GetFilterFromUiEnum(filter));
			}
			else
			{
				DynamicResolutionHandler.ClearSelectedCamera();
			}
		}
	}
```

- `public UpdateDRS(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime) : System.Void`  

```csharp
public void UpdateDRS(float fullFrameTime, float mainThreadCpuTime, float renderThreadCpuTime, float gpuTime)
	{
		if (!FrameTimingManager.IsFeatureEnabled())
		{
			return;
		}
		if (!m_Initialized)
		{
			if (m_InitialFrameCounter >= 1)
			{
				DynamicResolutionHandler.SetDynamicResScaler(() => s_CurrentScaleFraction * 100f, DynamicResScalePolicyType.ReturnsPercentage);
				m_Initialized = true;
			}
			else
			{
				m_InitialFrameCounter++;
			}
		}
		if (!m_Initialized)
		{
			return;
		}
		if (!isEnabled)
		{
			s_CurrentScaleFraction = 1f;
			return;
		}
		if (!isAdaptive)
		{
			s_CurrentScaleFraction = minScale;
			return;
		}
		m_AccumGPUFrameTime += gpuTime;
		m_GPULimitedFrames += (IsGpuBottleneck(fullFrameTime, mainThreadCpuTime, renderThreadCpuTime, gpuTime) ? 1 : 0);
		m_CurrentFrameSlot++;
		if (m_CurrentFrameSlot != EvaluationFrameCount)
		{
			return;
		}
		m_AvgGPUTime = m_AccumGPUFrameTime / (float)EvaluationFrameCount;
		m_AvgGPULimited = m_GPULimitedFrames / (float)EvaluationFrameCount;
		float defaultTargetFrameRate = DefaultTargetFrameRate;
		if (1000f / defaultTargetFrameRate - m_AvgGPUTime < 0f && m_AvgGPULimited > 0.3f)
		{
			m_ScaleUpCounter = 0u;
			m_ScaleDownCounter++;
			if (m_ScaleDownCounter >= ScaleDownDuration)
			{
				m_ScaleDownCounter = 0u;
				s_CurrentScaleFraction -= (1f - minScale) / (float)ScaleDownStepCount;
				s_CurrentScaleFraction = math.clamp(s_CurrentScaleFraction, minScale, 1f);
			}
		}
		else
		{
			m_ScaleDownCounter = 0u;
			m_ScaleUpCounter++;
			if (m_ScaleUpCounter >= ScaleUpDuration)
			{
				m_ScaleUpCounter = 0u;
				s_CurrentScaleFraction += (1f - minScale) / (float)ScaleUpStepCount;
				s_CurrentScaleFraction = math.clamp(s_CurrentScaleFraction, minScale, 1f);
			}
		}
		m_AccumGPUFrameTime = 0f;
		m_GPULimitedFrames = 0f;
		m_CurrentFrameSlot = 0;
	}
```


## Nested types

- `Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter`  
- `Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+<>c`  


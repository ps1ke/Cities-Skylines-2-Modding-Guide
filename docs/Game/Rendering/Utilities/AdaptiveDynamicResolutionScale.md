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
public static System.Void Dispose();
```

- `private static GetFilterFromUiEnum(Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter) : UnityEngine.Rendering.DynamicResUpscaleFilter`  

```csharp
private static UnityEngine.Rendering.DynamicResUpscaleFilter GetFilterFromUiEnum(Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter);
```

- `private static IsGpuBottleneck(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime) : System.Boolean`  

```csharp
private static System.Boolean IsGpuBottleneck(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime);
```

- `private static ResetScale() : System.Void`  

```csharp
private static System.Void ResetScale();
```

- `public SetParams(System.Boolean enabled, System.Boolean adaptive, System.Single minScale, Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter, UnityEngine.Camera camera) : System.Void`  

```csharp
public System.Void SetParams(System.Boolean enabled, System.Boolean adaptive, System.Single minScale, Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter, UnityEngine.Camera camera);
```

- `public UpdateDRS(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime) : System.Void`  

```csharp
public System.Void UpdateDRS(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime);
```


## Nested types

- `Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter`  
- `Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+<>c`  


# Game.Rendering.Utilities.AdaptiveDynamicResolutionScale

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField`  
- `private System.Boolean <isEnabled>k__BackingField`  
- `private System.Boolean <isAdaptive>k__BackingField`  
- `private System.Single <minScale>k__BackingField`  
- `public System.Single DefaultTargetFrameRate`  
- `public System.Int32 EvaluationFrameCount`  
- `public System.UInt32 ScaleUpDuration`  
- `public System.UInt32 ScaleDownDuration`  
- `public System.Int32 ScaleUpStepCount`  
- `public System.Int32 ScaleDownStepCount`  
- `private System.Single m_AccumGPUFrameTime`  
- `private System.Single m_GPULimitedFrames`  
- `private System.Int32 m_CurrentFrameSlot`  
- `private System.UInt32 m_ScaleUpCounter`  
- `private System.UInt32 m_ScaleDownCounter`  
- `private System.Boolean m_Initialized`  
- `private System.UInt32 m_InitialFrameCounter`  
- `private System.Single m_AvgGPUTime`  
- `private System.Single m_AvgGPULimited`  
- `private static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale s_Instance`  
- `private static System.Single s_CurrentScaleFraction`  
- `private static const System.UInt32 InitialFramesToSkip`  

## Properties

- `public static Game.Rendering.Utilities.AdaptiveDynamicResolutionScale instance { get }`  
- `public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; private set }`  
- `public System.Boolean isEnabled { get; private set }`  
- `public System.Boolean isAdaptive { get; private set }`  
- `public System.Single minScale { get; private set }`  
- `public System.Single currentScale { get }`  
- `public System.String debugState { get }`  

## Constructors

- `public AdaptiveDynamicResolutionScale()`  

## Methods

- `public static Dispose() : System.Void`  
- `private static GetFilterFromUiEnum(Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter) : UnityEngine.Rendering.DynamicResUpscaleFilter`  
- `private static IsGpuBottleneck(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime) : System.Boolean`  
- `private static ResetScale() : System.Void`  
- `public SetParams(System.Boolean enabled, System.Boolean adaptive, System.Single minScale, Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter filter, UnityEngine.Camera camera) : System.Void`  
- `public UpdateDRS(System.Single fullFrameTime, System.Single mainThreadCpuTime, System.Single renderThreadCpuTime, System.Single gpuTime) : System.Void`  

## Nested types

- `Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter`  
- `Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+<>c`  


# Game.Simulation.SnowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public class SnowSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal;
    private UnityEngine.ComputeBuffer m_snowBackdropBuffer;
    private UnityEngine.ComputeBuffer m_MinHeights;
    private System.Int32 <SnowSimSpeed>k__BackingField;
    private UnityEngine.RenderTexture[] m_SnowHeights;
    private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
    private UnityEngine.ComputeShader m_SnowUpdateShader;
    private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField;
    private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField;
    private System.Int32 m_TransferKernel;
    private System.Int32 m_AddKernel;
    private System.Int32 m_ResetKernel;
    private System.Int32 m_LoadKernel;
    private System.Int32 m_LoadOldFormatKernel;
    private System.Int32 m_UpdateBackdropSnowHeightTextureKernel;
    private System.Int32 m_ClearBackdropSnowHeightTextureKernel;
    private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel;
    private System.Int32 m_ID_SnowDepth;
    private System.Int32 m_ID_OldSnowDepth;
    private System.Int32 m_ID_Timestep;
    private System.Int32 m_ID_AddMultiplier;
    private System.Int32 m_ID_MeltMultiplier;
    private System.Int32 m_ID_AddWaterMultiplier;
    private System.Int32 m_ID_ElapseWaterMultiplier;
    private System.Int32 m_ID_Temperature;
    private System.Int32 m_ID_Rain;
    private System.Int32 m_ID_Wind;
    private System.Int32 m_ID_Time;
    private System.Int32 m_ID_SnowScale;
    private System.Int32 m_ID_MinHeights;
    private System.Int32 m_ID_SnowHeightBackdropBuffer;
    private System.Int32 m_ID_SnowHeightBackdropFinal;
    private System.Int32 m_ID_SnowBackdropUpdateLerpFactor;
    private System.Int32 m_ID_SnowHeightBackdropBufferSize;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private System.Int32 <Write>k__BackingField;
    private System.Boolean <IsAsync>k__BackingField;
    private static Colossal.Logging.ILog log;
    private static const System.Int32 kTexSize;
    private static const System.Int32 kGroupSizeAddSnow;
    private static const System.Int32 kNumGroupAddSnow;
    private static const System.Single kTimeStep;
    private static const System.Single kSnowHeightScale;
    private static const System.Single kSnowMeltScale;
    private static const System.Single m_SnowAddConstant;
    private static const System.Single m_WaterAddConstant;
    private static const System.Int32 kSnowHeightBackdropTextureSize;
    private static const System.Single kSnowBackdropUpdateLerpFactor;

    public UnityEngine.RenderTexture SnowHeightBackdropTexture { get; }
    public System.Int32 SnowSimSpeed { get; set; }
    public Unity.Mathematics.int2 TextureSize { get; }
    public System.Boolean Loaded { get; }
    private UnityEngine.ComputeShader m_SnowTransferShader { private get; set; }
    private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set; }
    private Unity.Mathematics.float4 SnowScaleVector { private get; }
    private System.Int32 Write { private get; private set; }
    private System.Int32 Read { private get; }
    public UnityEngine.RenderTexture SnowDepth { get; }
    public System.Boolean IsAsync { get; set; }

    public SnowSystem();

    private System.Void AddSnow(UnityEngine.Rendering.CommandBuffer cmd);
    private UnityEngine.RenderTexture CreateTexture(System.String name);
    public System.Void DebugReset();
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void FlipSnow();
    private System.Single GetSnowiness();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private System.Void InitShader();
    private System.Void InitTextures();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void SnowTransfer(UnityEngine.Rendering.CommandBuffer cmd);
    public System.Void UpdateDynamicHeights();
    private System.Void UpdateSnowBackdropTexture(UnityEngine.Rendering.CommandBuffer cmd, System.Single lerpFactor);
}
```


## Fields

- `private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal`  

```csharp
private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal;
```

- `private UnityEngine.ComputeBuffer m_snowBackdropBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_snowBackdropBuffer;
```

- `private UnityEngine.ComputeBuffer m_MinHeights`  

```csharp
private UnityEngine.ComputeBuffer m_MinHeights;
```

- `private System.Int32 <SnowSimSpeed>k__BackingField`  

```csharp
private System.Int32 <SnowSimSpeed>k__BackingField;
```

- `private UnityEngine.RenderTexture[] m_SnowHeights`  

```csharp
private UnityEngine.RenderTexture[] m_SnowHeights;
```

- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
```

- `private UnityEngine.ComputeShader m_SnowUpdateShader`  

```csharp
private UnityEngine.ComputeShader m_SnowUpdateShader;
```

- `private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField`  

```csharp
private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField;
```

- `private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField`  

```csharp
private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField;
```

- `private System.Int32 m_TransferKernel`  

```csharp
private System.Int32 m_TransferKernel;
```

- `private System.Int32 m_AddKernel`  

```csharp
private System.Int32 m_AddKernel;
```

- `private System.Int32 m_ResetKernel`  

```csharp
private System.Int32 m_ResetKernel;
```

- `private System.Int32 m_LoadKernel`  

```csharp
private System.Int32 m_LoadKernel;
```

- `private System.Int32 m_LoadOldFormatKernel`  

```csharp
private System.Int32 m_LoadOldFormatKernel;
```

- `private System.Int32 m_UpdateBackdropSnowHeightTextureKernel`  

```csharp
private System.Int32 m_UpdateBackdropSnowHeightTextureKernel;
```

- `private System.Int32 m_ClearBackdropSnowHeightTextureKernel`  

```csharp
private System.Int32 m_ClearBackdropSnowHeightTextureKernel;
```

- `private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel`  

```csharp
private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel;
```

- `private System.Int32 m_ID_SnowDepth`  

```csharp
private System.Int32 m_ID_SnowDepth;
```

- `private System.Int32 m_ID_OldSnowDepth`  

```csharp
private System.Int32 m_ID_OldSnowDepth;
```

- `private System.Int32 m_ID_Timestep`  

```csharp
private System.Int32 m_ID_Timestep;
```

- `private System.Int32 m_ID_AddMultiplier`  

```csharp
private System.Int32 m_ID_AddMultiplier;
```

- `private System.Int32 m_ID_MeltMultiplier`  

```csharp
private System.Int32 m_ID_MeltMultiplier;
```

- `private System.Int32 m_ID_AddWaterMultiplier`  

```csharp
private System.Int32 m_ID_AddWaterMultiplier;
```

- `private System.Int32 m_ID_ElapseWaterMultiplier`  

```csharp
private System.Int32 m_ID_ElapseWaterMultiplier;
```

- `private System.Int32 m_ID_Temperature`  

```csharp
private System.Int32 m_ID_Temperature;
```

- `private System.Int32 m_ID_Rain`  

```csharp
private System.Int32 m_ID_Rain;
```

- `private System.Int32 m_ID_Wind`  

```csharp
private System.Int32 m_ID_Wind;
```

- `private System.Int32 m_ID_Time`  

```csharp
private System.Int32 m_ID_Time;
```

- `private System.Int32 m_ID_SnowScale`  

```csharp
private System.Int32 m_ID_SnowScale;
```

- `private System.Int32 m_ID_MinHeights`  

```csharp
private System.Int32 m_ID_MinHeights;
```

- `private System.Int32 m_ID_SnowHeightBackdropBuffer`  

```csharp
private System.Int32 m_ID_SnowHeightBackdropBuffer;
```

- `private System.Int32 m_ID_SnowHeightBackdropFinal`  

```csharp
private System.Int32 m_ID_SnowHeightBackdropFinal;
```

- `private System.Int32 m_ID_SnowBackdropUpdateLerpFactor`  

```csharp
private System.Int32 m_ID_SnowBackdropUpdateLerpFactor;
```

- `private System.Int32 m_ID_SnowHeightBackdropBufferSize`  

```csharp
private System.Int32 m_ID_SnowHeightBackdropBufferSize;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private System.Int32 <Write>k__BackingField`  

```csharp
private System.Int32 <Write>k__BackingField;
```

- `private System.Boolean <IsAsync>k__BackingField`  

```csharp
private System.Boolean <IsAsync>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.Int32 kTexSize`  

```csharp
private static const System.Int32 kTexSize;
```

- `private static const System.Int32 kGroupSizeAddSnow`  

```csharp
private static const System.Int32 kGroupSizeAddSnow;
```

- `private static const System.Int32 kNumGroupAddSnow`  

```csharp
private static const System.Int32 kNumGroupAddSnow;
```

- `private static const System.Single kTimeStep`  

```csharp
private static const System.Single kTimeStep;
```

- `private static const System.Single kSnowHeightScale`  

```csharp
private static const System.Single kSnowHeightScale;
```

- `private static const System.Single kSnowMeltScale`  

```csharp
private static const System.Single kSnowMeltScale;
```

- `private static const System.Single m_SnowAddConstant`  

```csharp
private static const System.Single m_SnowAddConstant;
```

- `private static const System.Single m_WaterAddConstant`  

```csharp
private static const System.Single m_WaterAddConstant;
```

- `private static const System.Int32 kSnowHeightBackdropTextureSize`  

```csharp
private static const System.Int32 kSnowHeightBackdropTextureSize;
```

- `private static const System.Single kSnowBackdropUpdateLerpFactor`  

```csharp
private static const System.Single kSnowBackdropUpdateLerpFactor;
```


## Properties

- `public UnityEngine.RenderTexture SnowHeightBackdropTexture { get }`  

```csharp
public UnityEngine.RenderTexture SnowHeightBackdropTexture { get; }
```

- `public System.Int32 SnowSimSpeed { get; set }`  

```csharp
public System.Int32 SnowSimSpeed { get; set; }
```

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```

- `public System.Boolean Loaded { get }`  

```csharp
public System.Boolean Loaded { get; }
```

- `private UnityEngine.ComputeShader m_SnowTransferShader { private get; set }`  

```csharp
private UnityEngine.ComputeShader m_SnowTransferShader { private get; set; }
```

- `private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set }`  

```csharp
private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set; }
```

- `private Unity.Mathematics.float4 SnowScaleVector { private get }`  

```csharp
private Unity.Mathematics.float4 SnowScaleVector { private get; }
```

- `private System.Int32 Write { private get; private set }`  

```csharp
private System.Int32 Write { private get; private set; }
```

- `private System.Int32 Read { private get }`  

```csharp
private System.Int32 Read { private get; }
```

- `public UnityEngine.RenderTexture SnowDepth { get }`  

```csharp
public UnityEngine.RenderTexture SnowDepth { get; }
```

- `public System.Boolean IsAsync { get; set }`  

```csharp
public System.Boolean IsAsync { get; set; }
```


## Constructors

- `public SnowSystem()`  

```csharp
public SnowSystem();
```


## Methods

- `private AddSnow(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void AddSnow(UnityEngine.Rendering.CommandBuffer cmd);
```

- `private CreateTexture(System.String name) : UnityEngine.RenderTexture`  

```csharp
private UnityEngine.RenderTexture CreateTexture(System.String name);
```

- `public DebugReset() : System.Void`  

```csharp
public System.Void DebugReset();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private FlipSnow() : System.Void`  

```csharp
private System.Void FlipSnow();
```

- `private GetSnowiness() : System.Single`  

```csharp
private System.Single GetSnowiness();
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `private InitShader() : System.Void`  

```csharp
private System.Void InitShader();
```

- `private InitTextures() : System.Void`  

```csharp
private System.Void InitTextures();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private SnowTransfer(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void SnowTransfer(UnityEngine.Rendering.CommandBuffer cmd);
```

- `public UpdateDynamicHeights() : System.Void`  

```csharp
public System.Void UpdateDynamicHeights();
```

- `private UpdateSnowBackdropTexture(UnityEngine.Rendering.CommandBuffer cmd, System.Single lerpFactor) : System.Void`  

```csharp
private System.Void UpdateSnowBackdropTexture(UnityEngine.Rendering.CommandBuffer cmd, System.Single lerpFactor);
```


## Nested types

- `Game.Simulation.SnowSystem+ushort2`  


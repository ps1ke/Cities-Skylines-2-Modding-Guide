# Game.Simulation.SnowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `FormerlySerializedAs`  

## Fields

- `private UnityEngine.RenderTexture m_snowHeightBackdropTextureFinal`  
- `private UnityEngine.ComputeBuffer m_snowBackdropBuffer`  
- `private UnityEngine.ComputeBuffer m_MinHeights`  
- `private System.Int32 <SnowSimSpeed>k__BackingField`  
- `private UnityEngine.RenderTexture[] m_SnowHeights`  
- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  
- `private UnityEngine.ComputeShader m_SnowUpdateShader`  
- `private UnityEngine.ComputeShader <m_SnowTransferShader>k__BackingField`  
- `private UnityEngine.ComputeShader <m_DynamicHeightShader>k__BackingField`  
- `private System.Int32 m_TransferKernel`  
- `private System.Int32 m_AddKernel`  
- `private System.Int32 m_ResetKernel`  
- `private System.Int32 m_LoadKernel`  
- `private System.Int32 m_LoadOldFormatKernel`  
- `private System.Int32 m_UpdateBackdropSnowHeightTextureKernel`  
- `private System.Int32 m_ClearBackdropSnowHeightTextureKernel`  
- `private System.Int32 m_FinalizeBackdropSnowHeightTextureKernel`  
- `private System.Int32 m_ID_SnowDepth`  
- `private System.Int32 m_ID_OldSnowDepth`  
- `private System.Int32 m_ID_Timestep`  
- `private System.Int32 m_ID_AddMultiplier`  
- `private System.Int32 m_ID_MeltMultiplier`  
- `private System.Int32 m_ID_AddWaterMultiplier`  
- `private System.Int32 m_ID_ElapseWaterMultiplier`  
- `private System.Int32 m_ID_Temperature`  
- `private System.Int32 m_ID_Rain`  
- `private System.Int32 m_ID_Wind`  
- `private System.Int32 m_ID_Time`  
- `private System.Int32 m_ID_SnowScale`  
- `private System.Int32 m_ID_MinHeights`  
- `private System.Int32 m_ID_SnowHeightBackdropBuffer`  
- `private System.Int32 m_ID_SnowHeightBackdropFinal`  
- `private System.Int32 m_ID_SnowBackdropUpdateLerpFactor`  
- `private System.Int32 m_ID_SnowHeightBackdropBufferSize`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private System.Int32 <Write>k__BackingField`  
- `private System.Boolean <IsAsync>k__BackingField`  
- `private static Colossal.Logging.ILog log`  
- `private static const System.Int32 kTexSize`  
- `private static const System.Int32 kGroupSizeAddSnow`  
- `private static const System.Int32 kNumGroupAddSnow`  
- `private static const System.Single kTimeStep`  
- `private static const System.Single kSnowHeightScale`  
- `private static const System.Single kSnowMeltScale`  
- `private static const System.Single m_SnowAddConstant`  
- `private static const System.Single m_WaterAddConstant`  
- `private static const System.Int32 kSnowHeightBackdropTextureSize`  
- `private static const System.Single kSnowBackdropUpdateLerpFactor`  

## Properties

- `public UnityEngine.RenderTexture SnowHeightBackdropTexture { get }`  
- `public System.Int32 SnowSimSpeed { get; set }`  
- `public Unity.Mathematics.int2 TextureSize { get }`  
- `public System.Boolean Loaded { get }`  
- `private UnityEngine.ComputeShader m_SnowTransferShader { private get; set }`  
- `private UnityEngine.ComputeShader m_DynamicHeightShader { private get; set }`  
- `private Unity.Mathematics.float4 SnowScaleVector { private get }`  
- `private System.Int32 Write { private get; private set }`  
- `private System.Int32 Read { private get }`  
- `public UnityEngine.RenderTexture SnowDepth { get }`  
- `public System.Boolean IsAsync { get; set }`  

## Constructors

- `public SnowSystem()`  

## Methods

- `private AddSnow(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `private CreateTexture(System.String name) : UnityEngine.RenderTexture`  
- `public DebugReset() : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private FlipSnow() : System.Void`  
- `private GetSnowiness() : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `private InitShader() : System.Void`  
- `private InitTextures() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private SnowTransfer(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public UpdateDynamicHeights() : System.Void`  
- `private UpdateSnowBackdropTexture(UnityEngine.Rendering.CommandBuffer cmd, System.Single lerpFactor) : System.Void`  

## Nested types

- `Game.Simulation.SnowSystem+ushort2`  


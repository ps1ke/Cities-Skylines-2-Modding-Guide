# Game.Rendering.RenderingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.UInt32 <frameIndex>k__BackingField`  
- `private System.Single <frameTime>k__BackingField`  
- `private System.Single <frameDelta>k__BackingField`  
- `private System.Single <frameLod>k__BackingField`  
- `private System.Single <timeOfDay>k__BackingField`  
- `private System.Int32 <lodTimerDelta>k__BackingField`  
- `private System.Single <frameOffset>k__BackingField`  
- `private System.Boolean <hideOverlay>k__BackingField`  
- `private System.Boolean <unspawnedVisible>k__BackingField`  
- `private System.Boolean <markersVisible>k__BackingField`  
- `private System.Single <levelOfDetail>k__BackingField`  
- `private System.Boolean <lodCrossFade>k__BackingField`  
- `private System.Int32 <maxLightCount>k__BackingField`  
- `private System.Boolean <debugCrossFade>k__BackingField`  
- `private System.Boolean <disableLodModels>k__BackingField`  
- `private Unity.Mathematics.float4 <editorBuildingStateOverride>k__BackingField`  
- `private System.Boolean <motionVectors>k__BackingField`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  
- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  
- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private System.Collections.Generic.Dictionary<UnityEngine.Shader, System.Boolean> m_EnabledShaders`  
- `private Unity.Entities.EntityQuery m_TimeSettingGroup`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private System.Int32 m_TotalLoadingCount`  
- `private System.Int32 m_EnabledShaderCount`  
- `private System.Single m_LastFrameOffset`  
- `private System.Single m_LodTimer`  
- `private System.Boolean m_IsLoading`  
- `private System.Boolean m_EnabledShadersUpdated`  
- `public static const System.String kLoadingTask`  

## Properties

- `public System.UInt32 frameIndex { get; private set }`  
- `public System.Single frameTime { get; private set }`  
- `public System.Single frameDelta { get; private set }`  
- `public System.Single frameLod { get; private set }`  
- `public System.Single timeOfDay { get; private set }`  
- `public System.Int32 lodTimerDelta { get; private set }`  
- `public System.Single frameOffset { get; set }`  
- `public System.Boolean hideOverlay { get; set }`  
- `public System.Boolean unspawnedVisible { get; set }`  
- `public System.Boolean markersVisible { get; set }`  
- `public System.Single levelOfDetail { get; set }`  
- `public System.Boolean lodCrossFade { get; set }`  
- `public System.Int32 maxLightCount { get; set }`  
- `public System.Boolean debugCrossFade { get; set }`  
- `public System.Boolean disableLodModels { get; set }`  
- `public Unity.Mathematics.float4 editorBuildingStateOverride { get; set }`  
- `public System.Single loadingProgress { get; private set }`  
- `public System.Boolean motionVectors { get; private set }`  
- `public System.Collections.Generic.IReadOnlyDictionary<UnityEngine.Shader, System.Boolean> enabledShaders { get }`  

## Constructors

- `public RenderingSystem()`  

## Methods

- `private GetMotionVectorsEnabled() : System.Boolean`  
- `public GetShadowCullingData() : Unity.Mathematics.float3`  
- `public IsShaderEnabled(UnityEngine.Shader shader) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public PrepareRendering() : System.Void`  
- `public SetShaderEnabled(UnityEngine.Shader shader, System.Boolean isEnabled) : System.Void`  
- `private UpdateLoadingProgress() : System.Void`  


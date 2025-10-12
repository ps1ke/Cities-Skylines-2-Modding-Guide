# Game.Simulation.WaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.IGPUSystem`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Fields

- `private System.Int32 <WaterSimSpeed>k__BackingField`  
- `private System.Single <TimeStepOverride>k__BackingField`  
- `private System.Boolean m_Loaded`  
- `private System.Boolean <UseActiveCellsCulling>k__BackingField`  
- `private System.Boolean <BlurFlowMap>k__BackingField`  
- `private System.Boolean <FlowPostProcess>k__BackingField`  
- `private System.Int32 m_numFlowDownsample`  
- `public System.Single MaxFlowlengthForRender`  
- `public System.Single PostFlowspeedMultiplier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.SoilWaterSystem m_SoilWaterSystem`  
- `private Game.Simulation.SnowSystem m_SnowSystem`  
- `private Unity.Entities.EntityQuery m_SourceGroup`  
- `private Unity.Entities.EntityQuery m_SoilWaterParameterGroup`  
- `private Unity.Entities.EntityQuery m_WaterLevelChangeGroup`  
- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache1`  
- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache2`  
- `private Unity.Jobs.JobHandle m_SourceHandle`  
- `private System.Int32 m_SourceCacheIndex`  
- `private System.Boolean m_FlipSourceCache`  
- `private System.Int32 <GridSizeMultiplier>k__BackingField`  
- `private System.Int32 m_lastFrameGridSize`  
- `private System.Single <MaxVelocity>k__BackingField`  
- `private System.Int32 <MaxSpeed>k__BackingField`  
- `public System.Single m_TimeStep`  
- `public System.Single m_Damping`  
- `public System.Single m_Evaporation`  
- `public System.Single m_RainConstant`  
- `public System.Single m_PollutionDecayRate`  
- `public System.Single m_Fluidness`  
- `public System.Single m_FlowSpeed`  
- `public System.Single m_ConstantDepthDepth`  
- `private System.Single m_lastFrameTimeStep`  
- `private Game.Simulation.WaterSystem+QuadWaterBuffer m_Water`  
- `private UnityEngine.ComputeBuffer m_Active`  
- `private UnityEngine.ComputeBuffer m_CurrentActiveTilesIndices`  
- `private System.Int32 m_numThreadGroupsTotal`  
- `private System.Int32 m_numThreadGroupsX`  
- `private System.Int32 m_numThreadGroupsY`  
- `private Unity.Mathematics.int2 <m_ActiveGridSize>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Int32> m_ActiveCPU`  
- `private Unity.Collections.NativeArray<System.Int32> m_ActiveCPUTemp`  
- `private Game.Simulation.SurfaceDataReader m_depthsReader`  
- `private Game.Simulation.SurfaceDataReader m_velocitiesReader`  
- `private Unity.Jobs.JobHandle m_ActiveReaders`  
- `private System.UInt32 m_LastReadyFrame`  
- `private System.UInt32 m_PreviousReadyFrame`  
- `private System.Int32 m_SubFrame`  
- `private Unity.Mathematics.int2 m_TexSize`  
- `private System.Boolean m_NewMap`  
- `private System.Int32 m_terrainChangeCounter`  
- `private System.Single m_restoreHeightMinWaterHeight`  
- `private UnityEngine.ComputeShader m_UpdateShader`  
- `private System.Int32 m_VelocityKernel`  
- `private System.Int32 m_DownsampleKernel`  
- `private System.Int32 m_VerticalBlurKernel`  
- `private System.Int32 m_HorizontalBlurKernel`  
- `private System.Int32 m_FlowPostProcessKernel`  
- `private System.Int32 m_DepthKernel`  
- `private System.Int32 m_CopyToHeightmapKernel`  
- `private System.Int32 m_RestoreHeightFromHeightmapKernel`  
- `private System.Int32 m_AddKernel`  
- `private System.Int32 m_AddConstantKernel`  
- `private System.Int32 m_EvaporateKernel`  
- `private System.Int32 m_ResetKernel`  
- `private System.Int32 m_ResetActiveKernel`  
- `private System.Int32 m_ResetToLevelKernel`  
- `private System.Int32 m_LoadKernel`  
- `private System.Int32 m_LoadFlowMapKernel`  
- `private System.Int32 m_AddBorderKernel`  
- `private System.Int32 m_ID_AddPosition`  
- `private System.Int32 m_ID_AddRadius`  
- `private System.Int32 m_ID_AddAmount`  
- `private System.Int32 m_ID_AddPolluted`  
- `private System.Int32 m_ID_AreaX`  
- `private System.Int32 m_ID_AreaY`  
- `private System.Int32 m_ID_CellsPerArea`  
- `private System.Int32 m_ID_AreaCountX`  
- `private System.Int32 m_ID_AreaCountY`  
- `private System.Int32 m_ID_Evaporation`  
- `private System.Int32 m_ID_RainConstant`  
- `private System.Int32 m_ID_TerrainScale`  
- `private System.Int32 m_ID_Timestep`  
- `private System.Int32 m_ID_Fluidness`  
- `private System.Int32 m_ID_Damping`  
- `private System.Int32 m_ID_FlowInterpolationFatcor`  
- `private System.Int32 m_ID_CellSize`  
- `private System.Int32 m_ID_SoilWaterDepthConstant`  
- `private System.Int32 m_ID_SoilOutputMultiplier`  
- `private System.Int32 m_ID_AddBorderPosition`  
- `private System.Int32 m_ID_PollutionDecayRate`  
- `private System.Int32 m_ID_Previous`  
- `private System.Int32 m_ID_Result`  
- `private System.Int32 m_ID_Terrain`  
- `private System.Int32 m_ID_TerrainLod`  
- `private System.Int32 m_ID_MaxVelocity`  
- `private System.Int32 m_ID_RestoreHeightMinWaterHeight`  
- `private System.Int32 m_ID_Active`  
- `private System.UInt64 m_NextSimulationFrame`  
- `private System.UInt64 m_LastReadbackRequest`  
- `private System.UInt64 m_LastDepthReadbackRequest`  
- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  
- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  
- `private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback`  
- `private Colossal.Rendering.AsyncGPUReadbackHelper m_SaveAsyncGPUReadback`  
- `private System.Boolean m_PendingActiveReadback`  
- `private System.Boolean <IsAsync>k__BackingField`  
- `private Game.Simulation.WaterSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1000286415_0`  
- `public static readonly System.Int32 kMapSize`  
- `public static readonly System.Single kDefaultMinWaterToRestoreHeight`  
- `private static System.Single s_SeaLevel`  
- `private static readonly System.Single kCellSize`  
- `private static Unity.Profiling.ProfilerMarker m_DepthUpdate`  
- `public static const System.Int32 MAX_FLOW_DOWNSCALE`  
- `private static const System.Single kGravity`  
- `private static const System.Int32 kGridSize`  

## Properties

- `public static System.Single SeaLevel { get }`  
- `public System.Int32 WaterSimSpeed { get; set }`  
- `public System.Single TimeStepOverride { get; set }`  
- `public System.Boolean Loaded { get }`  
- `public System.Boolean UseActiveCellsCulling { get; set }`  
- `public Unity.Mathematics.int2 TextureSize { get }`  
- `public UnityEngine.RenderTexture WaterTexture { get }`  
- `public UnityEngine.RenderTexture WaterRenderTexture { get }`  
- `public System.Boolean BlurFlowMap { get; set }`  
- `public System.Boolean FlowPostProcess { get; set }`  
- `public System.Int32 FlowMapNumDownscale { get; set }`  
- `public System.Boolean EnableFlowDownscale { get; set }`  
- `public UnityEngine.Texture FlowTextureUpdated { get }`  
- `public System.Single CellSize { get }`  
- `public Unity.Mathematics.float2 MapSize { get }`  
- `public System.Int32 GridSizeMultiplier { get; set }`  
- `public System.Int32 GridSize { get }`  
- `public System.Single MaxVelocity { get; set }`  
- `public System.Int32 MaxSpeed { get; set }`  
- `public System.Int32 SimulationCycleSteps { get }`  
- `private System.Int32 ReadbackRequestInterval { private get }`  
- `private System.Int32 DepthReadbackRequestInterval { private get }`  
- `public static System.Single WaveSpeed { get }`  
- `public Unity.Mathematics.int2 m_ActiveGridSize { get; private set }`  
- `public System.Boolean IsAsync { get; set }`  
- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> LastFrameSourceCache { private get }`  
- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> CurrentJobSourceCache { private get }`  

## Constructors

- `public WaterSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddActiveReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddSurfaceReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public AddVelocitySurfaceReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `private BindTextures() : System.Void`  
- `private BorderCircleIntersection(System.Boolean isX, System.Boolean isPositive, Unity.Mathematics.float2 center, System.Single radius, Unity.Mathematics.int2& result) : System.Boolean`  
- `public static CalculateSourceMultiplier(Game.Simulation.WaterSourceData source, Unity.Mathematics.float3 pos) : System.Single`  
- `private CopyToHeightmapStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public CreateByteArray<T>(Unity.Collections.NativeArray<T> src) : System.Byte[]`  
- `private DepthStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private EvaporateStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `private Game.IGPUSystem.get_Enabled() : System.Boolean`  
- `public GetActive() : Unity.Collections.NativeArray<System.Int32>`  
- `public static GetCell(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize) : Unity.Mathematics.int2`  
- `private static GetCellCoords(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize) : Unity.Mathematics.float2`  
- `public GetDepth(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> waterMap) : Game.Simulation.SurfaceWater`  
- `public GetDepths(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<Game.Simulation.SurfaceWater>`  
- `public GetSurfaceData(Unity.Jobs.JobHandle& deps) : Game.Simulation.WaterSurfaceData`  
- `public GetTimeStep() : System.Single`  
- `public GetVelocitiesSurfaceData(Unity.Jobs.JobHandle& deps) : Game.Simulation.WaterSurfaceData`  
- `private HasWater(Unity.Mathematics.float3 position) : System.Boolean`  
- `private InitShader() : System.Void`  
- `private InitTextures() : System.Void`  
- `public JobLoad() : System.Void`  
- `private JobSaveToFile(Unity.Collections.NativeArray<Unity.Mathematics.float4> buffer) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `public OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Reset() : System.Void`  
- `private ResetActive(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `private ResetToLevel(System.Single level) : System.Void`  
- `public ResetToSealevel() : System.Void`  
- `public Restart() : System.Void`  
- `private RestoreHeightFromHeightmap(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public Save() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private Simulate(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public static SourceMatchesDirection(Game.Simulation.WaterSourceData source, Game.Objects.Transform transform, Unity.Mathematics.float2 direction) : System.Boolean`  
- `private SourceStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  
- `public TerrainWillChange() : System.Void`  
- `public TerrainWillChangeFromBrush(Colossal.Mathematics.Bounds2 area) : System.Void`  
- `private UpdateGPUReadback() : System.Void`  
- `private UpdateSaveReadback() : System.Void`  
- `private VelocityStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

## Nested types

- `Game.Simulation.WaterSystem+WaterSource`  
- `Game.Simulation.WaterSystem+QuadWaterBuffer`  
- `Game.Simulation.WaterSystem+WaterSourceCache`  
- `Game.Simulation.WaterSystem+SourceJob`  
- `Game.Simulation.WaterSystem+ReadCommandHelper`  
- `Game.Simulation.WaterSystem+TypeHandle`  


# Game.Simulation.WaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.IGPUSystem`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Code

```csharp
public class WaterSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.IGPUSystem
{
    private System.Int32 <WaterSimSpeed>k__BackingField;
    private System.Single <TimeStepOverride>k__BackingField;
    private System.Boolean m_Loaded;
    private System.Boolean <UseActiveCellsCulling>k__BackingField;
    private System.Boolean <BlurFlowMap>k__BackingField;
    private System.Boolean <FlowPostProcess>k__BackingField;
    private System.Int32 m_numFlowDownsample;
    public System.Single MaxFlowlengthForRender;
    public System.Single PostFlowspeedMultiplier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.SoilWaterSystem m_SoilWaterSystem;
    private Game.Simulation.SnowSystem m_SnowSystem;
    private Unity.Entities.EntityQuery m_SourceGroup;
    private Unity.Entities.EntityQuery m_SoilWaterParameterGroup;
    private Unity.Entities.EntityQuery m_WaterLevelChangeGroup;
    private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache1;
    private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache2;
    private Unity.Jobs.JobHandle m_SourceHandle;
    private System.Int32 m_SourceCacheIndex;
    private System.Boolean m_FlipSourceCache;
    private System.Int32 <GridSizeMultiplier>k__BackingField;
    private System.Int32 m_lastFrameGridSize;
    private System.Single <MaxVelocity>k__BackingField;
    private System.Int32 <MaxSpeed>k__BackingField;
    public System.Single m_TimeStep;
    public System.Single m_Damping;
    public System.Single m_Evaporation;
    public System.Single m_RainConstant;
    public System.Single m_PollutionDecayRate;
    public System.Single m_Fluidness;
    public System.Single m_FlowSpeed;
    public System.Single m_ConstantDepthDepth;
    private System.Single m_lastFrameTimeStep;
    private Game.Simulation.WaterSystem+QuadWaterBuffer m_Water;
    private UnityEngine.ComputeBuffer m_Active;
    private UnityEngine.ComputeBuffer m_CurrentActiveTilesIndices;
    private System.Int32 m_numThreadGroupsTotal;
    private System.Int32 m_numThreadGroupsX;
    private System.Int32 m_numThreadGroupsY;
    private Unity.Mathematics.int2 <m_ActiveGridSize>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_ActiveCPU;
    private Unity.Collections.NativeArray<System.Int32> m_ActiveCPUTemp;
    private Game.Simulation.SurfaceDataReader m_depthsReader;
    private Game.Simulation.SurfaceDataReader m_velocitiesReader;
    private Unity.Jobs.JobHandle m_ActiveReaders;
    private System.UInt32 m_LastReadyFrame;
    private System.UInt32 m_PreviousReadyFrame;
    private System.Int32 m_SubFrame;
    private Unity.Mathematics.int2 m_TexSize;
    private System.Boolean m_NewMap;
    private System.Int32 m_terrainChangeCounter;
    private System.Single m_restoreHeightMinWaterHeight;
    private UnityEngine.ComputeShader m_UpdateShader;
    private System.Int32 m_VelocityKernel;
    private System.Int32 m_DownsampleKernel;
    private System.Int32 m_VerticalBlurKernel;
    private System.Int32 m_HorizontalBlurKernel;
    private System.Int32 m_FlowPostProcessKernel;
    private System.Int32 m_DepthKernel;
    private System.Int32 m_CopyToHeightmapKernel;
    private System.Int32 m_RestoreHeightFromHeightmapKernel;
    private System.Int32 m_AddKernel;
    private System.Int32 m_AddConstantKernel;
    private System.Int32 m_EvaporateKernel;
    private System.Int32 m_ResetKernel;
    private System.Int32 m_ResetActiveKernel;
    private System.Int32 m_ResetToLevelKernel;
    private System.Int32 m_LoadKernel;
    private System.Int32 m_LoadFlowMapKernel;
    private System.Int32 m_AddBorderKernel;
    private System.Int32 m_ID_AddPosition;
    private System.Int32 m_ID_AddRadius;
    private System.Int32 m_ID_AddAmount;
    private System.Int32 m_ID_AddPolluted;
    private System.Int32 m_ID_AreaX;
    private System.Int32 m_ID_AreaY;
    private System.Int32 m_ID_CellsPerArea;
    private System.Int32 m_ID_AreaCountX;
    private System.Int32 m_ID_AreaCountY;
    private System.Int32 m_ID_Evaporation;
    private System.Int32 m_ID_RainConstant;
    private System.Int32 m_ID_TerrainScale;
    private System.Int32 m_ID_Timestep;
    private System.Int32 m_ID_Fluidness;
    private System.Int32 m_ID_Damping;
    private System.Int32 m_ID_FlowInterpolationFatcor;
    private System.Int32 m_ID_CellSize;
    private System.Int32 m_ID_SoilWaterDepthConstant;
    private System.Int32 m_ID_SoilOutputMultiplier;
    private System.Int32 m_ID_AddBorderPosition;
    private System.Int32 m_ID_PollutionDecayRate;
    private System.Int32 m_ID_Previous;
    private System.Int32 m_ID_Result;
    private System.Int32 m_ID_Terrain;
    private System.Int32 m_ID_TerrainLod;
    private System.Int32 m_ID_MaxVelocity;
    private System.Int32 m_ID_RestoreHeightMinWaterHeight;
    private System.Int32 m_ID_Active;
    private System.UInt64 m_NextSimulationFrame;
    private System.UInt64 m_LastReadbackRequest;
    private System.UInt64 m_LastDepthReadbackRequest;
    private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
    private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
    private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback;
    private Colossal.Rendering.AsyncGPUReadbackHelper m_SaveAsyncGPUReadback;
    private System.Boolean m_PendingActiveReadback;
    private System.Boolean <IsAsync>k__BackingField;
    private Game.Simulation.WaterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1000286415_0;
    public static readonly System.Int32 kMapSize;
    public static readonly System.Single kDefaultMinWaterToRestoreHeight;
    private static System.Single s_SeaLevel;
    private static readonly System.Single kCellSize;
    private static Unity.Profiling.ProfilerMarker m_DepthUpdate;
    public static const System.Int32 MAX_FLOW_DOWNSCALE;
    private static const System.Single kGravity;
    private static const System.Int32 kGridSize;

    public static System.Single SeaLevel { get; }
    public System.Int32 WaterSimSpeed { get; set; }
    public System.Single TimeStepOverride { get; set; }
    public System.Boolean Loaded { get; }
    public System.Boolean UseActiveCellsCulling { get; set; }
    public Unity.Mathematics.int2 TextureSize { get; }
    public UnityEngine.RenderTexture WaterTexture { get; }
    public UnityEngine.RenderTexture WaterRenderTexture { get; }
    public System.Boolean BlurFlowMap { get; set; }
    public System.Boolean FlowPostProcess { get; set; }
    public System.Int32 FlowMapNumDownscale { get; set; }
    public System.Boolean EnableFlowDownscale { get; set; }
    public UnityEngine.Texture FlowTextureUpdated { get; }
    public System.Single CellSize { get; }
    public Unity.Mathematics.float2 MapSize { get; }
    public System.Int32 GridSizeMultiplier { get; set; }
    public System.Int32 GridSize { get; }
    public System.Single MaxVelocity { get; set; }
    public System.Int32 MaxSpeed { get; set; }
    public System.Int32 SimulationCycleSteps { get; }
    private System.Int32 ReadbackRequestInterval { private get; }
    private System.Int32 DepthReadbackRequestInterval { private get; }
    public static System.Single WaveSpeed { get; }
    public Unity.Mathematics.int2 m_ActiveGridSize { get; private set; }
    public System.Boolean IsAsync { get; set; }
    private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> LastFrameSourceCache { private get; }
    private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> CurrentJobSourceCache { private get; }

    public WaterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddActiveReader(Unity.Jobs.JobHandle handle);
    public System.Void AddSurfaceReader(Unity.Jobs.JobHandle handle);
    public System.Void AddVelocitySurfaceReader(Unity.Jobs.JobHandle handle);
    private System.Void BindTextures();
    private System.Boolean BorderCircleIntersection(System.Boolean isX, System.Boolean isPositive, Unity.Mathematics.float2 center, System.Single radius, Unity.Mathematics.int2& result);
    public static System.Single CalculateSourceMultiplier(Game.Simulation.WaterSourceData source, Unity.Mathematics.float3 pos);
    private System.Void CopyToHeightmapStep(UnityEngine.Rendering.CommandBuffer cmd);
    public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
    private System.Void DepthStep(UnityEngine.Rendering.CommandBuffer cmd);
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void EvaporateStep(UnityEngine.Rendering.CommandBuffer cmd);
    private System.Boolean Game.IGPUSystem.get_Enabled();
    public Unity.Collections.NativeArray<System.Int32> GetActive();
    public static Unity.Mathematics.int2 GetCell(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize);
    private static Unity.Mathematics.float2 GetCellCoords(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize);
    public Game.Simulation.SurfaceWater GetDepth(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> waterMap);
    public Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> GetDepths(Unity.Jobs.JobHandle& deps);
    public Game.Simulation.WaterSurfaceData GetSurfaceData(Unity.Jobs.JobHandle& deps);
    public System.Single GetTimeStep();
    public Game.Simulation.WaterSurfaceData GetVelocitiesSurfaceData(Unity.Jobs.JobHandle& deps);
    private System.Boolean HasWater(Unity.Mathematics.float3 position);
    private System.Void InitShader();
    private System.Void InitTextures();
    public System.Void JobLoad();
    private System.Void JobSaveToFile(Unity.Collections.NativeArray<Unity.Mathematics.float4> buffer);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    public System.Void OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    private System.Void Reset();
    private System.Void ResetActive(UnityEngine.Rendering.CommandBuffer cmd);
    private System.Void ResetToLevel(System.Single level);
    public System.Void ResetToSealevel();
    public System.Void Restart();
    private System.Void RestoreHeightFromHeightmap(UnityEngine.Rendering.CommandBuffer cmd);
    public System.Void Save();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void Simulate(UnityEngine.Rendering.CommandBuffer cmd);
    public static System.Boolean SourceMatchesDirection(Game.Simulation.WaterSourceData source, Game.Objects.Transform transform, Unity.Mathematics.float2 direction);
    private System.Void SourceStep(UnityEngine.Rendering.CommandBuffer cmd);
    public System.Void TerrainWillChange();
    public System.Void TerrainWillChangeFromBrush(Colossal.Mathematics.Bounds2 area);
    private System.Void UpdateGPUReadback();
    private System.Void UpdateSaveReadback();
    private System.Void VelocityStep(UnityEngine.Rendering.CommandBuffer cmd);
}
```


## Fields

- `private System.Int32 <WaterSimSpeed>k__BackingField`  

```csharp
private System.Int32 <WaterSimSpeed>k__BackingField;
```

- `private System.Single <TimeStepOverride>k__BackingField`  

```csharp
private System.Single <TimeStepOverride>k__BackingField;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Boolean <UseActiveCellsCulling>k__BackingField`  

```csharp
private System.Boolean <UseActiveCellsCulling>k__BackingField;
```

- `private System.Boolean <BlurFlowMap>k__BackingField`  

```csharp
private System.Boolean <BlurFlowMap>k__BackingField;
```

- `private System.Boolean <FlowPostProcess>k__BackingField`  

```csharp
private System.Boolean <FlowPostProcess>k__BackingField;
```

- `private System.Int32 m_numFlowDownsample`  

```csharp
private System.Int32 m_numFlowDownsample;
```

- `public System.Single MaxFlowlengthForRender`  

```csharp
public System.Single MaxFlowlengthForRender;
```

- `public System.Single PostFlowspeedMultiplier`  

```csharp
public System.Single PostFlowspeedMultiplier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.SoilWaterSystem m_SoilWaterSystem`  

```csharp
private Game.Simulation.SoilWaterSystem m_SoilWaterSystem;
```

- `private Game.Simulation.SnowSystem m_SnowSystem`  

```csharp
private Game.Simulation.SnowSystem m_SnowSystem;
```

- `private Unity.Entities.EntityQuery m_SourceGroup`  

```csharp
private Unity.Entities.EntityQuery m_SourceGroup;
```

- `private Unity.Entities.EntityQuery m_SoilWaterParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_SoilWaterParameterGroup;
```

- `private Unity.Entities.EntityQuery m_WaterLevelChangeGroup`  

```csharp
private Unity.Entities.EntityQuery m_WaterLevelChangeGroup;
```

- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache1`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache1;
```

- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache2`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> m_SourceCache2;
```

- `private Unity.Jobs.JobHandle m_SourceHandle`  

```csharp
private Unity.Jobs.JobHandle m_SourceHandle;
```

- `private System.Int32 m_SourceCacheIndex`  

```csharp
private System.Int32 m_SourceCacheIndex;
```

- `private System.Boolean m_FlipSourceCache`  

```csharp
private System.Boolean m_FlipSourceCache;
```

- `private System.Int32 <GridSizeMultiplier>k__BackingField`  

```csharp
private System.Int32 <GridSizeMultiplier>k__BackingField;
```

- `private System.Int32 m_lastFrameGridSize`  

```csharp
private System.Int32 m_lastFrameGridSize;
```

- `private System.Single <MaxVelocity>k__BackingField`  

```csharp
private System.Single <MaxVelocity>k__BackingField;
```

- `private System.Int32 <MaxSpeed>k__BackingField`  

```csharp
private System.Int32 <MaxSpeed>k__BackingField;
```

- `public System.Single m_TimeStep`  

```csharp
public System.Single m_TimeStep;
```

- `public System.Single m_Damping`  

```csharp
public System.Single m_Damping;
```

- `public System.Single m_Evaporation`  

```csharp
public System.Single m_Evaporation;
```

- `public System.Single m_RainConstant`  

```csharp
public System.Single m_RainConstant;
```

- `public System.Single m_PollutionDecayRate`  

```csharp
public System.Single m_PollutionDecayRate;
```

- `public System.Single m_Fluidness`  

```csharp
public System.Single m_Fluidness;
```

- `public System.Single m_FlowSpeed`  

```csharp
public System.Single m_FlowSpeed;
```

- `public System.Single m_ConstantDepthDepth`  

```csharp
public System.Single m_ConstantDepthDepth;
```

- `private System.Single m_lastFrameTimeStep`  

```csharp
private System.Single m_lastFrameTimeStep;
```

- `private Game.Simulation.WaterSystem+QuadWaterBuffer m_Water`  

```csharp
private Game.Simulation.WaterSystem+QuadWaterBuffer m_Water;
```

- `private UnityEngine.ComputeBuffer m_Active`  

```csharp
private UnityEngine.ComputeBuffer m_Active;
```

- `private UnityEngine.ComputeBuffer m_CurrentActiveTilesIndices`  

```csharp
private UnityEngine.ComputeBuffer m_CurrentActiveTilesIndices;
```

- `private System.Int32 m_numThreadGroupsTotal`  

```csharp
private System.Int32 m_numThreadGroupsTotal;
```

- `private System.Int32 m_numThreadGroupsX`  

```csharp
private System.Int32 m_numThreadGroupsX;
```

- `private System.Int32 m_numThreadGroupsY`  

```csharp
private System.Int32 m_numThreadGroupsY;
```

- `private Unity.Mathematics.int2 <m_ActiveGridSize>k__BackingField`  

```csharp
private Unity.Mathematics.int2 <m_ActiveGridSize>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ActiveCPU`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ActiveCPU;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ActiveCPUTemp`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ActiveCPUTemp;
```

- `private Game.Simulation.SurfaceDataReader m_depthsReader`  

```csharp
private Game.Simulation.SurfaceDataReader m_depthsReader;
```

- `private Game.Simulation.SurfaceDataReader m_velocitiesReader`  

```csharp
private Game.Simulation.SurfaceDataReader m_velocitiesReader;
```

- `private Unity.Jobs.JobHandle m_ActiveReaders`  

```csharp
private Unity.Jobs.JobHandle m_ActiveReaders;
```

- `private System.UInt32 m_LastReadyFrame`  

```csharp
private System.UInt32 m_LastReadyFrame;
```

- `private System.UInt32 m_PreviousReadyFrame`  

```csharp
private System.UInt32 m_PreviousReadyFrame;
```

- `private System.Int32 m_SubFrame`  

```csharp
private System.Int32 m_SubFrame;
```

- `private Unity.Mathematics.int2 m_TexSize`  

```csharp
private Unity.Mathematics.int2 m_TexSize;
```

- `private System.Boolean m_NewMap`  

```csharp
private System.Boolean m_NewMap;
```

- `private System.Int32 m_terrainChangeCounter`  

```csharp
private System.Int32 m_terrainChangeCounter;
```

- `private System.Single m_restoreHeightMinWaterHeight`  

```csharp
private System.Single m_restoreHeightMinWaterHeight;
```

- `private UnityEngine.ComputeShader m_UpdateShader`  

```csharp
private UnityEngine.ComputeShader m_UpdateShader;
```

- `private System.Int32 m_VelocityKernel`  

```csharp
private System.Int32 m_VelocityKernel;
```

- `private System.Int32 m_DownsampleKernel`  

```csharp
private System.Int32 m_DownsampleKernel;
```

- `private System.Int32 m_VerticalBlurKernel`  

```csharp
private System.Int32 m_VerticalBlurKernel;
```

- `private System.Int32 m_HorizontalBlurKernel`  

```csharp
private System.Int32 m_HorizontalBlurKernel;
```

- `private System.Int32 m_FlowPostProcessKernel`  

```csharp
private System.Int32 m_FlowPostProcessKernel;
```

- `private System.Int32 m_DepthKernel`  

```csharp
private System.Int32 m_DepthKernel;
```

- `private System.Int32 m_CopyToHeightmapKernel`  

```csharp
private System.Int32 m_CopyToHeightmapKernel;
```

- `private System.Int32 m_RestoreHeightFromHeightmapKernel`  

```csharp
private System.Int32 m_RestoreHeightFromHeightmapKernel;
```

- `private System.Int32 m_AddKernel`  

```csharp
private System.Int32 m_AddKernel;
```

- `private System.Int32 m_AddConstantKernel`  

```csharp
private System.Int32 m_AddConstantKernel;
```

- `private System.Int32 m_EvaporateKernel`  

```csharp
private System.Int32 m_EvaporateKernel;
```

- `private System.Int32 m_ResetKernel`  

```csharp
private System.Int32 m_ResetKernel;
```

- `private System.Int32 m_ResetActiveKernel`  

```csharp
private System.Int32 m_ResetActiveKernel;
```

- `private System.Int32 m_ResetToLevelKernel`  

```csharp
private System.Int32 m_ResetToLevelKernel;
```

- `private System.Int32 m_LoadKernel`  

```csharp
private System.Int32 m_LoadKernel;
```

- `private System.Int32 m_LoadFlowMapKernel`  

```csharp
private System.Int32 m_LoadFlowMapKernel;
```

- `private System.Int32 m_AddBorderKernel`  

```csharp
private System.Int32 m_AddBorderKernel;
```

- `private System.Int32 m_ID_AddPosition`  

```csharp
private System.Int32 m_ID_AddPosition;
```

- `private System.Int32 m_ID_AddRadius`  

```csharp
private System.Int32 m_ID_AddRadius;
```

- `private System.Int32 m_ID_AddAmount`  

```csharp
private System.Int32 m_ID_AddAmount;
```

- `private System.Int32 m_ID_AddPolluted`  

```csharp
private System.Int32 m_ID_AddPolluted;
```

- `private System.Int32 m_ID_AreaX`  

```csharp
private System.Int32 m_ID_AreaX;
```

- `private System.Int32 m_ID_AreaY`  

```csharp
private System.Int32 m_ID_AreaY;
```

- `private System.Int32 m_ID_CellsPerArea`  

```csharp
private System.Int32 m_ID_CellsPerArea;
```

- `private System.Int32 m_ID_AreaCountX`  

```csharp
private System.Int32 m_ID_AreaCountX;
```

- `private System.Int32 m_ID_AreaCountY`  

```csharp
private System.Int32 m_ID_AreaCountY;
```

- `private System.Int32 m_ID_Evaporation`  

```csharp
private System.Int32 m_ID_Evaporation;
```

- `private System.Int32 m_ID_RainConstant`  

```csharp
private System.Int32 m_ID_RainConstant;
```

- `private System.Int32 m_ID_TerrainScale`  

```csharp
private System.Int32 m_ID_TerrainScale;
```

- `private System.Int32 m_ID_Timestep`  

```csharp
private System.Int32 m_ID_Timestep;
```

- `private System.Int32 m_ID_Fluidness`  

```csharp
private System.Int32 m_ID_Fluidness;
```

- `private System.Int32 m_ID_Damping`  

```csharp
private System.Int32 m_ID_Damping;
```

- `private System.Int32 m_ID_FlowInterpolationFatcor`  

```csharp
private System.Int32 m_ID_FlowInterpolationFatcor;
```

- `private System.Int32 m_ID_CellSize`  

```csharp
private System.Int32 m_ID_CellSize;
```

- `private System.Int32 m_ID_SoilWaterDepthConstant`  

```csharp
private System.Int32 m_ID_SoilWaterDepthConstant;
```

- `private System.Int32 m_ID_SoilOutputMultiplier`  

```csharp
private System.Int32 m_ID_SoilOutputMultiplier;
```

- `private System.Int32 m_ID_AddBorderPosition`  

```csharp
private System.Int32 m_ID_AddBorderPosition;
```

- `private System.Int32 m_ID_PollutionDecayRate`  

```csharp
private System.Int32 m_ID_PollutionDecayRate;
```

- `private System.Int32 m_ID_Previous`  

```csharp
private System.Int32 m_ID_Previous;
```

- `private System.Int32 m_ID_Result`  

```csharp
private System.Int32 m_ID_Result;
```

- `private System.Int32 m_ID_Terrain`  

```csharp
private System.Int32 m_ID_Terrain;
```

- `private System.Int32 m_ID_TerrainLod`  

```csharp
private System.Int32 m_ID_TerrainLod;
```

- `private System.Int32 m_ID_MaxVelocity`  

```csharp
private System.Int32 m_ID_MaxVelocity;
```

- `private System.Int32 m_ID_RestoreHeightMinWaterHeight`  

```csharp
private System.Int32 m_ID_RestoreHeightMinWaterHeight;
```

- `private System.Int32 m_ID_Active`  

```csharp
private System.Int32 m_ID_Active;
```

- `private System.UInt64 m_NextSimulationFrame`  

```csharp
private System.UInt64 m_NextSimulationFrame;
```

- `private System.UInt64 m_LastReadbackRequest`  

```csharp
private System.UInt64 m_LastReadbackRequest;
```

- `private System.UInt64 m_LastDepthReadbackRequest`  

```csharp
private System.UInt64 m_LastDepthReadbackRequest;
```

- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
```

- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  

```csharp
private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
```

- `private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback`  

```csharp
private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback;
```

- `private Colossal.Rendering.AsyncGPUReadbackHelper m_SaveAsyncGPUReadback`  

```csharp
private Colossal.Rendering.AsyncGPUReadbackHelper m_SaveAsyncGPUReadback;
```

- `private System.Boolean m_PendingActiveReadback`  

```csharp
private System.Boolean m_PendingActiveReadback;
```

- `private System.Boolean <IsAsync>k__BackingField`  

```csharp
private System.Boolean <IsAsync>k__BackingField;
```

- `private Game.Simulation.WaterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1000286415_0`  

```csharp
private Unity.Entities.EntityQuery __query_1000286415_0;
```

- `public static readonly System.Int32 kMapSize`  

```csharp
public static readonly System.Int32 kMapSize;
```

- `public static readonly System.Single kDefaultMinWaterToRestoreHeight`  

```csharp
public static readonly System.Single kDefaultMinWaterToRestoreHeight;
```

- `private static System.Single s_SeaLevel`  

```csharp
private static System.Single s_SeaLevel;
```

- `private static readonly System.Single kCellSize`  

```csharp
private static readonly System.Single kCellSize;
```

- `private static Unity.Profiling.ProfilerMarker m_DepthUpdate`  

```csharp
private static Unity.Profiling.ProfilerMarker m_DepthUpdate;
```

- `public static const System.Int32 MAX_FLOW_DOWNSCALE`  

```csharp
public static const System.Int32 MAX_FLOW_DOWNSCALE;
```

- `private static const System.Single kGravity`  

```csharp
private static const System.Single kGravity;
```

- `private static const System.Int32 kGridSize`  

```csharp
private static const System.Int32 kGridSize;
```


## Properties

- `public static System.Single SeaLevel { get }`  

```csharp
public static System.Single SeaLevel { get; }
```

- `public System.Int32 WaterSimSpeed { get; set }`  

```csharp
public System.Int32 WaterSimSpeed { get; set; }
```

- `public System.Single TimeStepOverride { get; set }`  

```csharp
public System.Single TimeStepOverride { get; set; }
```

- `public System.Boolean Loaded { get }`  

```csharp
public System.Boolean Loaded { get; }
```

- `public System.Boolean UseActiveCellsCulling { get; set }`  

```csharp
public System.Boolean UseActiveCellsCulling { get; set; }
```

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```

- `public UnityEngine.RenderTexture WaterTexture { get }`  

```csharp
public UnityEngine.RenderTexture WaterTexture { get; }
```

- `public UnityEngine.RenderTexture WaterRenderTexture { get }`  

```csharp
public UnityEngine.RenderTexture WaterRenderTexture { get; }
```

- `public System.Boolean BlurFlowMap { get; set }`  

```csharp
public System.Boolean BlurFlowMap { get; set; }
```

- `public System.Boolean FlowPostProcess { get; set }`  

```csharp
public System.Boolean FlowPostProcess { get; set; }
```

- `public System.Int32 FlowMapNumDownscale { get; set }`  

```csharp
public System.Int32 FlowMapNumDownscale { get; set; }
```

- `public System.Boolean EnableFlowDownscale { get; set }`  

```csharp
public System.Boolean EnableFlowDownscale { get; set; }
```

- `public UnityEngine.Texture FlowTextureUpdated { get }`  

```csharp
public UnityEngine.Texture FlowTextureUpdated { get; }
```

- `public System.Single CellSize { get }`  

```csharp
public System.Single CellSize { get; }
```

- `public Unity.Mathematics.float2 MapSize { get }`  

```csharp
public Unity.Mathematics.float2 MapSize { get; }
```

- `public System.Int32 GridSizeMultiplier { get; set }`  

```csharp
public System.Int32 GridSizeMultiplier { get; set; }
```

- `public System.Int32 GridSize { get }`  

```csharp
public System.Int32 GridSize { get; }
```

- `public System.Single MaxVelocity { get; set }`  

```csharp
public System.Single MaxVelocity { get; set; }
```

- `public System.Int32 MaxSpeed { get; set }`  

```csharp
public System.Int32 MaxSpeed { get; set; }
```

- `public System.Int32 SimulationCycleSteps { get }`  

```csharp
public System.Int32 SimulationCycleSteps { get; }
```

- `private System.Int32 ReadbackRequestInterval { private get }`  

```csharp
private System.Int32 ReadbackRequestInterval { private get; }
```

- `private System.Int32 DepthReadbackRequestInterval { private get }`  

```csharp
private System.Int32 DepthReadbackRequestInterval { private get; }
```

- `public static System.Single WaveSpeed { get }`  

```csharp
public static System.Single WaveSpeed { get; }
```

- `public Unity.Mathematics.int2 m_ActiveGridSize { get; private set }`  

```csharp
public Unity.Mathematics.int2 m_ActiveGridSize { get; private set; }
```

- `public System.Boolean IsAsync { get; set }`  

```csharp
public System.Boolean IsAsync { get; set; }
```

- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> LastFrameSourceCache { private get }`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> LastFrameSourceCache { private get; }
```

- `private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> CurrentJobSourceCache { private get }`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.WaterSystem+WaterSourceCache> CurrentJobSourceCache { private get; }
```


## Constructors

- `public WaterSystem()`  

```csharp
[Preserve]
	public WaterSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<TerrainPropertiesData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1000286415_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public AddActiveReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddActiveReader(JobHandle handle)
	{
		m_ActiveReaders = JobHandle.CombineDependencies(m_ActiveReaders, handle);
	}
```

- `public AddSurfaceReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddSurfaceReader(JobHandle handle)
	{
		m_depthsReader.JobReaders = JobHandle.CombineDependencies(m_depthsReader.JobReaders, handle);
	}
```

- `public AddVelocitySurfaceReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddVelocitySurfaceReader(JobHandle handle)
	{
		m_velocitiesReader.JobReaders = JobHandle.CombineDependencies(m_velocitiesReader.JobReaders, handle);
	}
```

- `private BindTextures() : System.Void`  

```csharp
private void BindTextures()
	{
		Shader.SetGlobalTexture("colossal_WaterTexture", WaterTexture);
		Shader.SetGlobalVector("colossal_WaterTexture_TexelSize", new Vector4(WaterRenderTexture.width, WaterRenderTexture.height, 1f / (float)WaterRenderTexture.width, 1f / (float)WaterRenderTexture.height));
		Shader.SetGlobalTexture("colossal_WaterRenderTexture", WaterRenderTexture);
		Shader.SetGlobalVector("colossal_WateRenderrTexture_TexelSize", new Vector4(WaterRenderTexture.width, WaterRenderTexture.height, 1f / (float)WaterRenderTexture.width, 1f / (float)WaterRenderTexture.height));
		Shader.SetGlobalTexture("colossal_FlowTexture", FlowTextureUpdated);
		Shader.SetGlobalVector("colossal_FlowTexture_TexelSize", new Vector4(FlowTextureUpdated.width, FlowTextureUpdated.height, 1f / (float)FlowTextureUpdated.width));
	}
```

- `private BorderCircleIntersection(System.Boolean isX, System.Boolean isPositive, Unity.Mathematics.float2 center, System.Single radius, Unity.Mathematics.int2& result) : System.Boolean`  

```csharp
private bool BorderCircleIntersection(bool isX, bool isPositive, float2 center, float radius, out int2 result)
	{
		float num = (float)kMapSize / 2f;
		float num2 = radius * radius;
		float num3 = math.abs((isX ? center.x : center.y) - (isPositive ? num : (0f - num)));
		float num4 = num2 - num3 * num3;
		if (num4 < 0f)
		{
			result = default(int2);
			return false;
		}
		float num5 = (isX ? center.y : center.x);
		float num6 = math.sqrt(num4);
		float2 @float = new float2(num5 - num6 + num, num5 + num6 + num);
		result = new int2(Mathf.FloorToInt((float)TextureSize.x * math.saturate(@float.x / (float)kMapSize)), Mathf.CeilToInt((float)TextureSize.y * math.saturate(@float.y / (float)kMapSize)));
		int num7 = (isX ? TextureSize.y : TextureSize.x) - 2;
		if (isX && isPositive)
		{
			num7++;
		}
		result.y = math.min(result.y, num7);
		result.x = math.min(result.x, result.y);
		return true;
	}
```

- `public static CalculateSourceMultiplier(Game.Simulation.WaterSourceData source, Unity.Mathematics.float3 pos) : System.Single`  

```csharp
public static float CalculateSourceMultiplier(WaterSourceData source, float3 pos)
	{
		if (source.m_Radius < 0.01f)
		{
			return 0f;
		}
		pos.y = 0f;
		int num = Mathf.CeilToInt(source.m_Radius / kCellSize);
		float num2 = 0f;
		float num3 = source.m_Radius * source.m_Radius;
		int num4 = Mathf.FloorToInt(pos.x / kCellSize) - num;
		int num5 = Mathf.FloorToInt(pos.z / kCellSize) - num;
		for (int i = num4; i <= num4 + 2 * num + 1; i++)
		{
			for (int j = num5; j <= num5 + 2 * num + 1; j++)
			{
				float3 x = new float3((float)i * kCellSize, 0f, (float)j * kCellSize);
				num2 += 1f - math.smoothstep(0f, 1f, math.distancesq(x, pos) / num3);
			}
		}
		if (num2 < 0.001f)
		{
			UnityEngine.Debug.LogWarning($"Warning: water source at {pos} has too small radius to work");
			return 1f;
		}
		return 1f / num2;
	}
```

- `private CopyToHeightmapStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void CopyToHeightmapStep(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.CopyToHeightMap)))
		{
			cmd.SetComputeTextureParam(m_UpdateShader, m_CopyToHeightmapKernel, m_ID_Previous, WaterTexture);
			cmd.SetComputeBufferParam(m_UpdateShader, m_CopyToHeightmapKernel, m_ID_Active, m_Active);
			cmd.SetComputeTextureParam(m_UpdateShader, m_CopyToHeightmapKernel, "_WaterOut", WaterRenderTexture);
			cmd.SetComputeTextureParam(m_UpdateShader, m_CopyToHeightmapKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
			cmd.SetComputeBufferParam(m_UpdateShader, m_CopyToHeightmapKernel, "_CurrentActiveIndices", m_CurrentActiveTilesIndices);
			cmd.SetComputeVectorParam(m_UpdateShader, m_ID_TerrainScale, new float4(m_TerrainSystem.heightScaleOffset.xy, 0f, 0f));
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_TerrainLod, TerrainSystem.baseLod);
			if (m_numThreadGroupsTotal > 0)
			{
				cmd.DispatchCompute(m_UpdateShader, m_CopyToHeightmapKernel, m_numThreadGroupsX, m_numThreadGroupsY, m_numThreadGroupsY);
			}
		}
	}
```

- `public CreateByteArray<T>(Unity.Collections.NativeArray<T> src) : System.Byte[]`  

```csharp
public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
```

- `private DepthStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void DepthStep(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.DepthStep)))
		{
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_CellSize, kCellSize);
			cmd.SetComputeTextureParam(m_UpdateShader, m_DepthKernel, m_ID_Previous, WaterRenderTexture);
			cmd.SetComputeTextureParam(m_UpdateShader, m_DepthKernel, m_ID_Result, WaterTexture);
			cmd.SetComputeBufferParam(m_UpdateShader, m_DepthKernel, m_ID_Active, m_Active);
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_CellsPerArea, GridSize);
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_AreaCountX, m_TexSize.x / GridSize);
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_AreaCountY, m_TexSize.y / GridSize);
			cmd.SetComputeTextureParam(m_UpdateShader, m_DepthKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
			cmd.SetComputeTextureParam(m_UpdateShader, m_DepthKernel, "_Snow", m_SnowSystem.SnowDepth);
			cmd.SetComputeVectorParam(m_UpdateShader, m_ID_TerrainScale, new float4(m_TerrainSystem.heightScaleOffset.x, m_TerrainSystem.heightScaleOffset.y, 0f, 0f));
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_TerrainLod, TerrainSystem.baseLod);
			int y = (m_TexSize / GridSize).y;
			_ = 0;
			m_ActiveReaders.Complete();
			cmd.SetComputeBufferParam(m_UpdateShader, m_DepthKernel, "_CurrentActiveIndices", m_CurrentActiveTilesIndices);
			if (m_numThreadGroupsTotal > 0)
			{
				cmd.DispatchCompute(m_UpdateShader, m_DepthKernel, m_numThreadGroupsX, m_numThreadGroupsY, m_numThreadGroupsY);
			}
			if (FlowMapNumDownscale > 0)
			{
				int2 @int = m_TexSize / 2 / 8;
				int num = FlowMapNumDownscale - 1;
				for (int i = 0; i < num; i++)
				{
					@int /= 2;
					cmd.SetComputeTextureParam(m_UpdateShader, m_DownsampleKernel, m_ID_Previous, m_Water.FlowDownScaled(i));
					cmd.SetComputeTextureParam(m_UpdateShader, m_DownsampleKernel, m_ID_Result, m_Water.FlowDownScaled(i + 1));
					cmd.DispatchCompute(m_UpdateShader, m_DownsampleKernel, @int.x, @int.y, 1);
				}
				if (BlurFlowMap && FlowMapNumDownscale > 1)
				{
					cmd.SetComputeTextureParam(m_UpdateShader, m_VerticalBlurKernel, m_ID_Previous, m_Water.FlowDownScaled(FlowMapNumDownscale - 1));
					cmd.SetComputeTextureParam(m_UpdateShader, m_VerticalBlurKernel, m_ID_Result, m_Water.FlowDownScaled(FlowMapNumDownscale - 2));
					cmd.DispatchCompute(m_UpdateShader, m_VerticalBlurKernel, @int.x, @int.y, 1);
					cmd.SetComputeTextureParam(m_UpdateShader, m_HorizontalBlurKernel, m_ID_Previous, m_Water.FlowDownScaled(FlowMapNumDownscale - 2));
					cmd.SetComputeTextureParam(m_UpdateShader, m_HorizontalBlurKernel, m_ID_Result, m_Water.FlowDownScaled(FlowMapNumDownscale - 1));
					cmd.DispatchCompute(m_UpdateShader, m_HorizontalBlurKernel, @int.x, @int.y, 1);
				}
				if (FlowPostProcess)
				{
					cmd.SetComputeTextureParam(m_UpdateShader, m_FlowPostProcessKernel, m_ID_Result, m_Water.FlowDownScaled(FlowMapNumDownscale - 1));
					cmd.SetComputeFloatParam(m_UpdateShader, "maxFlowlengthForRender", MaxFlowlengthForRender);
					cmd.SetComputeFloatParam(m_UpdateShader, "postFlowspeedMultiplier", PostFlowspeedMultiplier);
					cmd.DispatchCompute(m_UpdateShader, m_FlowPostProcessKernel, @int.x, @int.y, 1);
				}
			}
		}
		m_PreviousReadyFrame = m_LastReadyFrame;
		m_LastReadyFrame = (uint)(m_NextSimulationFrame / (ulong)MaxSpeed);
		if (m_NextSimulationFrame >= (ulong)((long)m_LastReadbackRequest + (long)ReadbackRequestInterval) && !m_PendingActiveReadback)
		{
			m_LastReadbackRequest = m_NextSimulationFrame;
			m_AsyncGPUReadback.Request(m_Active);
			m_PendingActiveReadback = true;
		}
		if (m_NextSimulationFrame >= (ulong)((long)m_LastDepthReadbackRequest + (long)DepthReadbackRequestInterval))
		{
			m_LastDepthReadbackRequest = m_NextSimulationFrame;
			m_depthsReader.ExecuteReadBack();
			m_velocitiesReader.ExecuteReadBack();
		}
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private EvaporateStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void EvaporateStep(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.EvaporateStep)))
		{
			bool flag = false;
			int2 activeGridSize = m_TexSize / GridSize;
			if (m_lastFrameGridSize != GridSize)
			{
				if (m_AsyncGPUReadback.isPending)
				{
					m_AsyncGPUReadback.WaitForCompletion();
					UpdateGPUReadback();
				}
				if (m_ActiveCPU.IsCreated)
				{
					m_ActiveReaders.Complete();
					m_ActiveCPU.Dispose();
					m_Active.Dispose();
					m_CurrentActiveTilesIndices.Dispose();
				}
				m_ActiveGridSize = activeGridSize;
				m_Active = new ComputeBuffer(activeGridSize.x * activeGridSize.y, UnsafeUtility.SizeOf<int>(), ComputeBufferType.Default);
				m_CurrentActiveTilesIndices = new ComputeBuffer(activeGridSize.x * activeGridSize.y, UnsafeUtility.SizeOf<int2>(), ComputeBufferType.Default);
				m_ActiveCPU = new NativeArray<int>(activeGridSize.x * activeGridSize.y, Allocator.Persistent);
				ResetActive(cmd);
				m_lastFrameGridSize = GridSize;
				flag = true;
			}
			if (!m_SoilWaterParameterGroup.TryGetSingleton<SoilWaterParameterData>(out var value))
			{
				return;
			}
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_SoilWaterDepthConstant, value.m_MaximumWaterDepth);
			int num = 262144 / SoilWaterSystem.kUpdatesPerDay / SimulationCycleSteps;
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_SoilOutputMultiplier, value.m_WaterPerUnit / (float)num);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_CellSize, kCellSize);
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_AreaCountX, m_TexSize.x / GridSize);
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_AreaCountY, m_TexSize.y / GridSize);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_MaxVelocity, MaxVelocity);
			cmd.SetComputeBufferParam(m_UpdateShader, m_EvaporateKernel, m_ID_Active, m_Active);
			cmd.SetComputeTextureParam(m_UpdateShader, m_EvaporateKernel, "_Snow", m_SnowSystem.SnowDepth);
			cmd.SetComputeTextureParam(m_UpdateShader, m_EvaporateKernel, m_ID_Result, WaterTexture);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_Timestep, GetTimeStep());
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_CellsPerArea, GridSize);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_Evaporation, m_Evaporation);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_RainConstant, m_RainConstant);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_PollutionDecayRate, m_PollutionDecayRate);
			bool flag2 = flag | m_NewMap;
			if (flag2)
			{
				cmd.SetComputeFloatParam(m_UpdateShader, m_ID_Timestep, m_TimeStep);
			}
			int numThreadGroupsX = 0;
			uint2[] array = new uint2[activeGridSize.y * activeGridSize.x];
			for (uint num2 = 0u; num2 < activeGridSize.x; num2++)
			{
				for (uint num3 = 0u; num3 < activeGridSize.y; num3++)
				{
					if (!UseActiveCellsCulling || flag2 || m_ActiveCPU[(int)(num2 + activeGridSize.x * num3)] > 0)
					{
						uint2 @uint = new uint2(num2, num3);
						array[numThreadGroupsX++] = @uint;
					}
				}
			}
			m_CurrentActiveTilesIndices.SetData(array);
			cmd.SetComputeBufferParam(m_UpdateShader, m_EvaporateKernel, "_CurrentActiveIndices", m_CurrentActiveTilesIndices);
			m_numThreadGroupsX = numThreadGroupsX;
			m_numThreadGroupsY = GridSize / 8;
			m_numThreadGroupsTotal = m_numThreadGroupsX * m_numThreadGroupsY;
			if (m_numThreadGroupsTotal > 0)
			{
				cmd.DispatchCompute(m_UpdateShader, m_EvaporateKernel, m_numThreadGroupsX, m_numThreadGroupsY, m_numThreadGroupsY);
			}
		}
	}
```

- `private Game.IGPUSystem.get_Enabled() : System.Boolean`  

```csharp
private System.Boolean Game.IGPUSystem.get_Enabled();
```

- `public GetActive() : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetActive()
	{
		return m_ActiveCPU;
	}
```

- `public static GetCell(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize) : Unity.Mathematics.int2`  

```csharp
public static int2 GetCell(float3 position, int mapSize, int2 textureSize)
	{
		float2 cellCoords = GetCellCoords(position, mapSize, textureSize);
		return new int2(Mathf.FloorToInt(cellCoords.x), Mathf.FloorToInt(cellCoords.y));
	}
```

- `private static GetCellCoords(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize) : Unity.Mathematics.float2`  

```csharp
private static float2 GetCellCoords(float3 position, int mapSize, int2 textureSize)
	{
		float2 @float = (float)mapSize / (float2)textureSize;
		return new float2(((float)(mapSize / 2) + position.x) / @float.x, ((float)(mapSize / 2) + position.z) / @float.y);
	}
```

- `public GetDepth(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> waterMap) : Game.Simulation.SurfaceWater`  

```csharp
public SurfaceWater GetDepth(float3 position, NativeArray<SurfaceWater> waterMap)
	{
		SurfaceWater result = default(SurfaceWater);
		float2 @float = (float)kMapSize / (float2)m_TexSize;
		int2 cell = GetCell(position - new float3(@float.x / 2f, 0f, @float.y / 2f), kMapSize, m_TexSize);
		float2 float2 = GetCellCoords(position, kMapSize, m_TexSize) - new float2(0.5f, 0.5f);
		_ = float2 - cell;
		cell.x = math.max(0, cell.x);
		cell.x = math.min(m_TexSize.x - 2, cell.x);
		cell.y = math.max(0, cell.y);
		cell.y = math.min(m_TexSize.y - 2, cell.y);
		SurfaceWater surfaceWater = waterMap[cell.x + 1 + m_TexSize.x * cell.y];
		SurfaceWater surfaceWater2 = waterMap[cell.x + m_TexSize.x * cell.y];
		SurfaceWater surfaceWater3 = waterMap[cell.x + m_TexSize.x * (cell.y + 1)];
		SurfaceWater surfaceWater4 = waterMap[cell.x + 1 + m_TexSize.x * (cell.y + 1)];
		result.m_Depth = math.lerp(math.lerp(surfaceWater.m_Depth, surfaceWater2.m_Depth, float2.x - (float)cell.x), math.lerp(surfaceWater3.m_Depth, surfaceWater4.m_Depth, float2.x - (float)cell.x), float2.y - (float)cell.y);
		result.m_Depth = math.max(result.m_Depth, 0f);
		result.m_Polluted = math.lerp(math.lerp(surfaceWater.m_Polluted, surfaceWater2.m_Polluted, float2.x - (float)cell.x), math.lerp(surfaceWater3.m_Polluted, surfaceWater4.m_Polluted, float2.x - (float)cell.x), float2.y - (float)cell.y);
		return result;
	}
```

- `public GetDepths(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<Game.Simulation.SurfaceWater>`  

```csharp
public NativeArray<SurfaceWater> GetDepths(out JobHandle deps)
	{
		deps = m_depthsReader.JobWriters;
		return m_depthsReader.WaterSurfaceCPUArray;
	}
```

- `public GetSurfaceData(Unity.Jobs.JobHandle& deps) : Game.Simulation.WaterSurfaceData`  

```csharp
public WaterSurfaceData GetSurfaceData(out JobHandle deps)
	{
		return m_depthsReader.GetSurfaceData(out deps);
	}
```

- `public GetTimeStep() : System.Single`  

```csharp
public float GetTimeStep()
	{
		if (m_NewMap)
		{
			return 1f;
		}
		if (m_SimulationSystem.selectedSpeed == 0f)
		{
			return 0f;
		}
		float num = Math.Min(UnityEngine.Time.smoothDeltaTime * 30f, 1f);
		float num2 = m_SimulationSystem.selectedSpeed * 0.25f;
		if (TimeStepOverride > 0f)
		{
			return TimeStepOverride;
		}
		float end = math.min(1f, num2 * num);
		m_lastFrameTimeStep = math.lerp(m_lastFrameTimeStep, end, UnityEngine.Time.smoothDeltaTime * 0.2f);
		return m_lastFrameTimeStep;
	}
```

- `public GetVelocitiesSurfaceData(Unity.Jobs.JobHandle& deps) : Game.Simulation.WaterSurfaceData`  

```csharp
public WaterSurfaceData GetVelocitiesSurfaceData(out JobHandle deps)
	{
		return m_velocitiesReader.GetSurfaceData(out deps);
	}
```

- `private HasWater(Unity.Mathematics.float3 position) : System.Boolean`  

```csharp
private bool HasWater(float3 position)
	{
		float2 @float = (float)kMapSize / (float2)m_TexSize;
		int2 cell = GetCell(position - new float3(@float.x / 2f, 0f, @float.y / 2f), kMapSize, m_TexSize);
		_ = GetCellCoords(position, kMapSize, m_TexSize) - new float2(0.5f, 0.5f) - cell;
		cell.x = math.max(0, cell.x);
		cell.x = math.min(m_TexSize.x - 2, cell.x);
		cell.y = math.max(0, cell.y);
		cell.y = math.min(m_TexSize.y - 2, cell.y);
		if (m_depthsReader.GetSurface(cell).m_Depth > 0f)
		{
			return true;
		}
		return false;
	}
```

- `private InitShader() : System.Void`  

```csharp
private void InitShader()
	{
		m_UpdateShader = AssetDatabase.global.resources.shaders.waterUpdate;
		m_VelocityKernel = m_UpdateShader.FindKernel("VelocityUpdate");
		m_DownsampleKernel = m_UpdateShader.FindKernel("CSDownsample");
		m_VerticalBlurKernel = m_UpdateShader.FindKernel("CSVerticalBlur");
		m_HorizontalBlurKernel = m_UpdateShader.FindKernel("CSHorizontalBlur");
		m_FlowPostProcessKernel = m_UpdateShader.FindKernel("CSFlowPostProcess");
		m_DepthKernel = m_UpdateShader.FindKernel("DepthUpdate");
		m_CopyToHeightmapKernel = m_UpdateShader.FindKernel("CopyToHeightmap");
		m_RestoreHeightFromHeightmapKernel = m_UpdateShader.FindKernel("RestoreHeightFromHeightmap");
		m_AddKernel = m_UpdateShader.FindKernel("Add");
		m_AddConstantKernel = m_UpdateShader.FindKernel("AddConstant");
		m_EvaporateKernel = m_UpdateShader.FindKernel("Evaporate");
		m_ResetKernel = m_UpdateShader.FindKernel("Reset");
		m_ResetActiveKernel = m_UpdateShader.FindKernel("ResetActive");
		m_ResetToLevelKernel = m_UpdateShader.FindKernel("ResetToLevel");
		m_LoadKernel = m_UpdateShader.FindKernel("Load");
		m_AddBorderKernel = m_UpdateShader.FindKernel("AddBorder");
		m_ID_AddAmount = Shader.PropertyToID("addAmount");
		m_ID_AddPolluted = Shader.PropertyToID("addPolluted");
		m_ID_AddPosition = Shader.PropertyToID("addPosition");
		m_ID_AddRadius = Shader.PropertyToID("addRadius");
		m_ID_AreaX = Shader.PropertyToID("areax");
		m_ID_AreaY = Shader.PropertyToID("areay");
		m_ID_CellsPerArea = Shader.PropertyToID("cellsPerArea");
		m_ID_AreaCountX = Shader.PropertyToID("areaCountX");
		m_ID_AreaCountY = Shader.PropertyToID("areaCountY");
		m_ID_Evaporation = Shader.PropertyToID("evaporation");
		m_ID_RainConstant = Shader.PropertyToID("rainConstant");
		m_ID_TerrainScale = Shader.PropertyToID("terrainScale");
		m_ID_Timestep = Shader.PropertyToID("timestep");
		m_ID_Fluidness = Shader.PropertyToID("fluidness");
		m_ID_Damping = Shader.PropertyToID("damping");
		m_ID_CellSize = Shader.PropertyToID("cellSize");
		m_ID_FlowInterpolationFatcor = Shader.PropertyToID("flowInterpolationFatcor");
		m_ID_PollutionDecayRate = Shader.PropertyToID("pollutionDecayRate");
		m_ID_AddBorderPosition = Shader.PropertyToID("addBorderPosition");
		m_ID_RestoreHeightMinWaterHeight = Shader.PropertyToID("restoreHeightMinWaterHeight");
		m_ID_Previous = Shader.PropertyToID("_Previous");
		m_ID_Result = Shader.PropertyToID("_Result");
		m_ID_Terrain = Shader.PropertyToID("_Terrain");
		m_ID_TerrainLod = Shader.PropertyToID("_TerrainLod");
		m_ID_Active = Shader.PropertyToID("_Active");
		m_ID_MaxVelocity = Shader.PropertyToID("maxVelo");
		m_ID_SoilWaterDepthConstant = Shader.PropertyToID("soilWaterDepthConstant");
		m_ID_SoilOutputMultiplier = Shader.PropertyToID("soilOutputMultiplier");
	}
```

- `private InitTextures() : System.Void`  

```csharp
private void InitTextures()
	{
		m_TexSize = new int2(2048, 2048);
		m_Water = default(QuadWaterBuffer);
		m_Water.Init(m_TexSize);
		int2 @int = (m_ActiveGridSize = m_TexSize / GridSize);
		m_Active = new ComputeBuffer(@int.x * @int.y, UnsafeUtility.SizeOf<int>(), ComputeBufferType.Default);
		m_CurrentActiveTilesIndices = new ComputeBuffer(@int.x * @int.y, UnsafeUtility.SizeOf<int2>(), ComputeBufferType.Default);
		m_ActiveCPU = new NativeArray<int>(@int.x * @int.y, Allocator.Persistent);
		if (m_depthsReader != null)
		{
			m_depthsReader.Dispose();
		}
		if (m_velocitiesReader != null)
		{
			m_velocitiesReader.Dispose();
		}
		m_depthsReader = new SurfaceDataReader(WaterTexture, kMapSize);
		m_velocitiesReader = new SurfaceDataReader(m_Water.FlowDownScaled(0), kMapSize);
		m_NewMap = true;
	}
```

- `public JobLoad() : System.Void`  

```csharp
public void JobLoad()
	{
		throw new NotImplementedException();
	}
```

- `private JobSaveToFile(Unity.Collections.NativeArray<Unity.Mathematics.float4> buffer) : System.Void`  

```csharp
private void JobSaveToFile(NativeArray<float4> buffer)
	{
		throw new NotImplementedException();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		InitShader();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_SoilWaterSystem = base.World.GetOrCreateSystemManaged<SoilWaterSystem>();
		m_SnowSystem = base.World.GetOrCreateSystemManaged<SnowSystem>();
		m_WaterRenderSystem = base.World.GetOrCreateSystemManaged<WaterRenderSystem>();
		RequireForUpdate<TerrainPropertiesData>();
		m_SourceGroup = GetEntityQuery(ComponentType.ReadOnly<WaterSourceData>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_SoilWaterParameterGroup = GetEntityQuery(ComponentType.ReadOnly<SoilWaterParameterData>());
		m_WaterLevelChangeGroup = GetEntityQuery(ComponentType.ReadOnly<WaterLevelChange>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>());
		WaterSimSpeed = 1;
		m_Loaded = false;
		m_CommandBuffer = new CommandBuffer();
		m_CommandBuffer.name = "Watersystem";
		m_SourceCache1 = new NativeList<WaterSourceCache>(Allocator.Persistent);
		m_SourceCache2 = new NativeList<WaterSourceCache>(Allocator.Persistent);
		InitTextures();
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Loaded = false;
		Shader.SetGlobalVector("colossal_WaterParams", new Vector4(0f, 0f, 0f, 0f));
		s_SeaLevel = 0f;
		if (m_velocitiesReader != null)
		{
			m_velocitiesReader.Dispose();
		}
		if (m_depthsReader != null)
		{
			m_depthsReader.Dispose();
		}
		m_SourceCache2.Dispose();
		m_SourceCache1.Dispose();
		if (m_Active != null)
		{
			m_Active.Release();
		}
		if (m_CurrentActiveTilesIndices != null)
		{
			m_CurrentActiveTilesIndices.Release();
		}
		if (m_ActiveCPU.IsCreated)
		{
			m_ActiveReaders.Complete();
			m_ActiveCPU.Dispose();
		}
		m_CommandBuffer.Release();
		m_Water.Dispose();
		base.OnDestroy();
	}
```

- `public OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
public void OnSimulateGPU(CommandBuffer cmd)
	{
		if (Loaded && m_TexSize.x > 0)
		{
			Simulate(cmd);
		}
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_SourceHandle.Complete();
		m_SourceCacheIndex = 1 - m_SourceCacheIndex;
		CurrentJobSourceCache.Clear();
		JobHandle outJobHandle;
		JobHandle outJobHandle2;
		SourceJob jobData = new SourceJob
		{
			m_SourceChunks = m_SourceGroup.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_EventChunks = m_WaterLevelChangeGroup.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
			m_ChangeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_WaterLevelChange_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterSourceData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ChangePrefabDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterLevelChangeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainOffset = m_TerrainSystem.positionOffset,
			m_Cache = CurrentJobSourceCache
		};
		m_SourceHandle = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, m_SourceHandle, outJobHandle, outJobHandle2));
		base.Dependency = m_SourceHandle;
		UpdateSaveReadback();
		m_ActiveReaders.Complete();
	}
```

- `private Reset() : System.Void`  

```csharp
private void Reset()
	{
		m_UpdateShader.SetTexture(m_ResetKernel, m_ID_Result, WaterTexture);
		m_UpdateShader.Dispatch(m_ResetKernel, m_TexSize.x / 16, m_TexSize.y / 16, 1);
	}
```

- `private ResetActive(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void ResetActive(CommandBuffer cmd)
	{
		int2 @int = m_TexSize / GridSize;
		cmd.SetComputeFloatParam(m_UpdateShader, m_ID_CellSize, kCellSize);
		cmd.SetComputeBufferParam(m_UpdateShader, m_ResetActiveKernel, m_ID_Active, m_Active);
		cmd.SetComputeIntParam(m_UpdateShader, m_ID_AreaCountX, m_TexSize.x / GridSize);
		cmd.SetComputeIntParam(m_UpdateShader, m_ID_AreaCountY, m_TexSize.y / GridSize);
		cmd.DispatchCompute(m_UpdateShader, m_ResetActiveKernel, @int.x, @int.y, 1);
	}
```

- `private ResetToLevel(System.Single level) : System.Void`  

```csharp
private void ResetToLevel(float level)
	{
		m_CommandBuffer.Clear();
		UnityEngine.Debug.Log(level);
		using (new ProfilingScope(m_CommandBuffer, ProfilingSampler.Get(ProfileId.WaterResetToLevel)))
		{
			int2 @int = m_TexSize / GridSize;
			m_CommandBuffer.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, level);
			m_CommandBuffer.SetComputeFloatParam(m_UpdateShader, m_ID_CellSize, kCellSize);
			m_CommandBuffer.SetComputeIntParam(m_UpdateShader, m_ID_CellsPerArea, GridSize);
			m_CommandBuffer.SetComputeTextureParam(m_UpdateShader, m_ResetToLevelKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
			m_CommandBuffer.SetComputeVectorParam(m_UpdateShader, m_ID_TerrainScale, new float4(m_TerrainSystem.heightScaleOffset.x, m_TerrainSystem.positionOffset.xy, 0f));
			m_CommandBuffer.SetComputeIntParam(m_UpdateShader, m_ID_TerrainLod, TerrainSystem.baseLod);
			for (int i = 0; i < @int.x; i++)
			{
				m_CommandBuffer.SetComputeIntParam(m_UpdateShader, m_ID_AreaX, i);
				for (int j = 0; j < @int.y; j++)
				{
					m_CommandBuffer.SetComputeIntParam(m_UpdateShader, m_ID_AreaY, j);
					m_CommandBuffer.SetComputeTextureParam(m_UpdateShader, m_ResetToLevelKernel, m_ID_Result, WaterTexture);
					m_CommandBuffer.DispatchCompute(m_UpdateShader, m_ResetToLevelKernel, GridSize / 16, GridSize / 16, 1);
				}
			}
		}
		Graphics.ExecuteCommandBuffer(m_CommandBuffer);
	}
```

- `public ResetToSealevel() : System.Void`  

```csharp
public void ResetToSealevel()
	{
		NativeArray<Entity> nativeArray = m_SourceGroup.ToEntityArray(Allocator.TempJob);
		EntityManager entityManager = base.World.EntityManager;
		float num = float.MaxValue;
		bool flag = false;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			WaterSourceData componentData = entityManager.GetComponentData<WaterSourceData>(entity);
			if (componentData.m_ConstantDepth == 3)
			{
				num = math.min(num, componentData.m_Amount);
				flag = true;
			}
		}
		nativeArray.Dispose();
		if (flag)
		{
			ResetToLevel(num);
		}
	}
```

- `public Restart() : System.Void`  

```csharp
public void Restart()
	{
		int2 @int = m_TexSize / GridSize;
		int num = @int.x * @int.y;
		NativeArray<int> nativeArray = new NativeArray<int>(num, Allocator.TempJob);
		IJobParallelForExtensions.Schedule(new MemsetNativeArray<int>
		{
			Source = nativeArray,
			Value = 0
		}, num, 64).Complete();
		m_Active.SetData(nativeArray);
		nativeArray.Dispose();
		num = m_TexSize.x * m_TexSize.y;
		NativeArray<float4> nativeArray2 = new NativeArray<float4>(num, Allocator.TempJob);
		IJobParallelForExtensions.Schedule(new MemsetNativeArray<float4>
		{
			Source = nativeArray2,
			Value = 0
		}, num, 64).Complete();
		ComputeBuffer computeBuffer = new ComputeBuffer(num, UnsafeUtility.SizeOf<float4>(), ComputeBufferType.Default);
		computeBuffer.SetData(nativeArray2);
		m_UpdateShader.SetInt(m_ID_CellsPerArea, GridSize);
		m_UpdateShader.SetInt(m_ID_AreaCountX, m_TexSize.x / GridSize);
		m_UpdateShader.SetBuffer(m_LoadKernel, "_LoadSource", computeBuffer);
		m_UpdateShader.SetTexture(m_LoadKernel, m_ID_Result, WaterTexture);
		computeBuffer.Dispose();
		nativeArray2.Dispose();
	}
```

- `private RestoreHeightFromHeightmap(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void RestoreHeightFromHeightmap(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.CopyToHeightMap)))
		{
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_RestoreHeightMinWaterHeight, m_restoreHeightMinWaterHeight);
			cmd.SetComputeTextureParam(m_UpdateShader, m_RestoreHeightFromHeightmapKernel, m_ID_Result, WaterTexture);
			cmd.SetComputeBufferParam(m_UpdateShader, m_RestoreHeightFromHeightmapKernel, m_ID_Active, m_Active);
			cmd.SetComputeTextureParam(m_UpdateShader, m_RestoreHeightFromHeightmapKernel, m_ID_Previous, WaterRenderTexture);
			cmd.SetComputeTextureParam(m_UpdateShader, m_RestoreHeightFromHeightmapKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
			cmd.SetComputeBufferParam(m_UpdateShader, m_RestoreHeightFromHeightmapKernel, "_CurrentActiveIndices", m_CurrentActiveTilesIndices);
			cmd.SetComputeVectorParam(m_UpdateShader, m_ID_TerrainScale, new float4(m_TerrainSystem.heightScaleOffset.xy, 0f, 0f));
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_TerrainLod, TerrainSystem.baseLod);
			if (m_numThreadGroupsTotal > 0)
			{
				cmd.DispatchCompute(m_UpdateShader, m_RestoreHeightFromHeightmapKernel, m_numThreadGroupsX, m_numThreadGroupsY, m_numThreadGroupsY);
			}
		}
	}
```

- `public Save() : System.Void`  

```csharp
public void Save()
	{
		WaterSimSpeed = 0;
		m_SaveAsyncGPUReadback.Request(WaterTexture, 0, GraphicsFormat.R32G32B32A32_SFloat);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastReadbackRequest = 0uL;
		m_LastDepthReadbackRequest = 0uL;
		m_PreviousReadyFrame = 0u;
		m_LastReadyFrame = 0u;
		m_NextSimulationFrame = 0uL;
		Reset();
		BindTextures();
		m_NewMap = true;
		m_Loaded = true;
		Shader.SetGlobalVector("colossal_WaterParams", new Vector4(0f, 0f, 0f, 0f));
		s_SeaLevel = 0f;
	}
```

- `private Simulate(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void Simulate(CommandBuffer cmd)
	{
		if (!__query_1000286415_0.HasSingleton<TerrainPropertiesData>())
		{
			return;
		}
		cmd.name = "WaterSimulation";
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.SimulateWater)))
		{
			bool flag = false;
			if (m_terrainChangeCounter > 0)
			{
				if (m_NewMap)
				{
					m_terrainChangeCounter = 0;
					WaterSimSpeed = 1;
				}
				else
				{
					m_terrainChangeCounter--;
					if (m_terrainChangeCounter == 0)
					{
						WaterSimSpeed = 1;
						flag = true;
					}
				}
			}
			if (WaterSimSpeed > 0)
			{
				for (int i = 0; i < WaterSimSpeed; i++)
				{
					if (flag)
					{
						RestoreHeightFromHeightmap(cmd);
						flag = false;
						m_restoreHeightMinWaterHeight = kDefaultMinWaterToRestoreHeight;
					}
					EvaporateStep(cmd);
					SourceStep(cmd);
					VelocityStep(cmd);
					DepthStep(cmd);
					m_NextSimulationFrame += (uint)(4 * MaxSpeed / WaterSimSpeed);
					if (WaterSimSpeed > 1)
					{
						Graphics.ExecuteCommandBuffer(cmd);
						cmd.Clear();
					}
				}
				CopyToHeightmapStep(cmd);
				m_NewMap = false;
			}
			else
			{
				m_NextSimulationFrame += (uint)MaxSpeed;
				m_PreviousReadyFrame = (uint)(m_NextSimulationFrame / (ulong)MaxSpeed);
				m_LastReadyFrame = (uint)(m_NextSimulationFrame / (ulong)MaxSpeed);
			}
		}
		LastFrameSourceCache.Clear();
		UpdateGPUReadback();
	}
```

- `public static SourceMatchesDirection(Game.Simulation.WaterSourceData source, Game.Objects.Transform transform, Unity.Mathematics.float2 direction) : System.Boolean`  

```csharp
public static bool SourceMatchesDirection(WaterSourceData source, Game.Objects.Transform transform, float2 direction)
	{
		if (source.m_ConstantDepth != 2 && source.m_ConstantDepth != 3)
		{
			return false;
		}
		if (math.abs(transform.m_Position.x) > math.abs(transform.m_Position.z))
		{
			return math.sign(transform.m_Position.x) != math.sign(direction.x);
		}
		return math.sign(transform.m_Position.z) != math.sign(direction.y);
	}
```

- `private SourceStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void SourceStep(CommandBuffer cmd)
	{
		int num = 0;
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.SourceStep)))
		{
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_CellSize, kCellSize);
			cmd.SetComputeVectorParam(m_UpdateShader, m_ID_TerrainScale, new float4(m_TerrainSystem.heightScaleOffset.x, m_TerrainSystem.positionOffset.y, 0f, 0f));
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_TerrainLod, TerrainSystem.baseLod);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_Timestep, GetTimeStep());
			m_ActiveReaders.Complete();
			float num2 = float.MaxValue;
			foreach (WaterSourceCache item in LastFrameSourceCache)
			{
				float2 center = item.m_Position + m_TerrainSystem.positionOffset.xz;
				cmd.SetComputeVectorParam(m_UpdateShader, m_ID_AddPosition, new float4(item.m_Position, 0f, 0f));
				cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddRadius, item.m_Radius);
				int num3 = Mathf.CeilToInt(item.m_Radius / kCellSize);
				num3 = 2 * num3 + 1;
				if (item.m_ConstantDepth == 1)
				{
					num++;
					cmd.SetComputeTextureParam(m_UpdateShader, m_AddConstantKernel, m_ID_Result, WaterTexture);
					cmd.SetComputeTextureParam(m_UpdateShader, m_AddConstantKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
					cmd.SetComputeBufferParam(m_UpdateShader, m_AddConstantKernel, m_ID_Active, m_Active);
					cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, item.m_Amount);
					cmd.DispatchCompute(m_UpdateShader, m_AddConstantKernel, num3, num3, 1);
				}
				else if (item.m_ConstantDepth == 0)
				{
					num++;
					cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, (float)SimulationCycleSteps * item.m_Multiplier * item.m_Amount);
					cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddPolluted, item.m_Polluted);
					cmd.SetComputeTextureParam(m_UpdateShader, m_AddKernel, m_ID_Result, WaterTexture);
					cmd.SetComputeBufferParam(m_UpdateShader, m_AddKernel, m_ID_Active, m_Active);
					cmd.DispatchCompute(m_UpdateShader, m_AddKernel, num3, num3, 1);
				}
				else if (item.m_ConstantDepth == 2 || item.m_ConstantDepth == 3)
				{
					num2 = math.min(num2, item.m_Amount);
					cmd.SetComputeTextureParam(m_UpdateShader, m_AddBorderKernel, m_ID_Result, WaterTexture);
					cmd.SetComputeTextureParam(m_UpdateShader, m_AddBorderKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
					cmd.SetComputeBufferParam(m_UpdateShader, m_AddBorderKernel, m_ID_Active, m_Active);
					int4 v = default(int4);
					if (BorderCircleIntersection(isX: false, isPositive: false, center, item.m_Radius, out var result))
					{
						num++;
						v.x = result.x;
						v.y = 0;
						cmd.SetComputeVectorParam(m_UpdateShader, m_ID_AddBorderPosition, new float4(v));
						cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, item.m_Amount);
						cmd.DispatchCompute(m_UpdateShader, m_AddBorderKernel, result.y - result.x + 1, 1, 1);
					}
					if (BorderCircleIntersection(isX: false, isPositive: true, center, item.m_Radius, out result))
					{
						num++;
						v.x = result.x;
						v.y = TextureSize.y - 1;
						cmd.SetComputeVectorParam(m_UpdateShader, m_ID_AddBorderPosition, new float4(v));
						cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, item.m_Amount);
						cmd.DispatchCompute(m_UpdateShader, m_AddBorderKernel, result.y - result.x + 1, 1, 1);
					}
					if (BorderCircleIntersection(isX: true, isPositive: false, center, item.m_Radius, out result))
					{
						num++;
						v.x = 0;
						v.y = result.x;
						cmd.SetComputeVectorParam(m_UpdateShader, m_ID_AddBorderPosition, new float4(v));
						cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, item.m_Amount);
						cmd.DispatchCompute(m_UpdateShader, m_AddBorderKernel, 1, 1, result.y - result.x + 1);
					}
					if (BorderCircleIntersection(isX: true, isPositive: true, center, item.m_Radius, out result))
					{
						num++;
						v.x = TextureSize.x - 1;
						v.y = result.x;
						cmd.SetComputeVectorParam(m_UpdateShader, m_ID_AddBorderPosition, new float4(v));
						cmd.SetComputeFloatParam(m_UpdateShader, m_ID_AddAmount, item.m_Amount);
						cmd.DispatchCompute(m_UpdateShader, m_AddBorderKernel, 1, 1, result.y - result.x + 1);
					}
				}
			}
			if (num2 != float.MaxValue)
			{
				Shader.SetGlobalVector("colossal_WaterParams", new Vector4(num2, 0f, 0f, 0f));
				s_SeaLevel = num2;
			}
		}
	}
```

- `public TerrainWillChange() : System.Void`  

```csharp
public void TerrainWillChange()
	{
		m_terrainChangeCounter = 15;
		WaterSimSpeed = 0;
	}
```

- `public TerrainWillChangeFromBrush(Colossal.Mathematics.Bounds2 area) : System.Void`  

```csharp
public void TerrainWillChangeFromBrush(Bounds2 area)
	{
		if (m_terrainChangeCounter == 0 && HasWater((new float3[5]
		{
			new float3(area.Center().x, 0f, area.Center().y),
			new float3(area.x.min, 0f, area.y.min),
			new float3(area.x.min, 0f, area.y.max),
			new float3(area.x.max, 0f, area.y.min),
			new float3(area.x.max, 0f, area.y.max)
		})[0]))
		{
			m_restoreHeightMinWaterHeight = -1000000f;
		}
		m_terrainChangeCounter = 15;
		WaterSimSpeed = 0;
	}
```

- `private UpdateGPUReadback() : System.Void`  

```csharp
private void UpdateGPUReadback()
	{
		if (m_AsyncGPUReadback.isPending && !m_AsyncGPUReadback.hasError)
		{
			if (m_AsyncGPUReadback.done)
			{
				m_ActiveCPUTemp = m_AsyncGPUReadback.GetData<int>();
				m_ActiveReaders.Complete();
				m_ActiveCPU.CopyFrom(m_ActiveCPUTemp);
				m_PendingActiveReadback = false;
			}
			m_AsyncGPUReadback.IncrementFrame();
		}
	}
```

- `private UpdateSaveReadback() : System.Void`  

```csharp
private void UpdateSaveReadback()
	{
		if (m_SaveAsyncGPUReadback.isPending && !m_SaveAsyncGPUReadback.hasError)
		{
			if (m_SaveAsyncGPUReadback.done)
			{
				JobSaveToFile(m_SaveAsyncGPUReadback.GetData<float4>());
			}
			m_SaveAsyncGPUReadback.IncrementFrame();
		}
	}
```

- `private VelocityStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private void VelocityStep(CommandBuffer cmd)
	{
		using (new ProfilingScope(cmd, ProfilingSampler.Get(ProfileId.VelocityStep)))
		{
			cmd.SetComputeTextureParam(m_UpdateShader, m_ResetKernel, m_ID_Result, WaterRenderTexture);
			cmd.DispatchCompute(m_UpdateShader, m_ResetKernel, m_TexSize.x / 16, m_TexSize.y / 16, 1);
			cmd.SetComputeTextureParam(m_UpdateShader, m_VelocityKernel, m_ID_Terrain, m_TerrainSystem.GetCascadeTexture());
			cmd.SetComputeVectorParam(m_UpdateShader, m_ID_TerrainScale, new float4(m_TerrainSystem.heightScaleOffset.xy, 0f, 0f));
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_CellSize, kCellSize);
			cmd.SetComputeTextureParam(m_UpdateShader, m_VelocityKernel, m_ID_Previous, WaterTexture);
			cmd.SetComputeTextureParam(m_UpdateShader, m_VelocityKernel, m_ID_Result, WaterRenderTexture);
			cmd.SetComputeTextureParam(m_UpdateShader, m_VelocityKernel, "_DownscaledResult", m_Water.FlowDownScaled(0));
			cmd.SetComputeIntParam(m_UpdateShader, m_ID_CellsPerArea, GridSize);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_Fluidness, m_Fluidness);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_Damping, m_Damping);
			cmd.SetComputeFloatParam(m_UpdateShader, m_ID_FlowInterpolationFatcor, m_NewMap ? 1f : 0.1f);
			int y = (m_TexSize / GridSize).y;
			_ = 0;
			m_ActiveReaders.Complete();
			cmd.SetComputeBufferParam(m_UpdateShader, m_VelocityKernel, "_CurrentActiveIndices", m_CurrentActiveTilesIndices);
			if (m_numThreadGroupsTotal > 0)
			{
				cmd.DispatchCompute(m_UpdateShader, m_VelocityKernel, m_numThreadGroupsX, m_numThreadGroupsY, m_numThreadGroupsY);
			}
		}
	}
```


## Nested types

- `Game.Simulation.WaterSystem+WaterSource`  
- `Game.Simulation.WaterSystem+QuadWaterBuffer`  
- `Game.Simulation.WaterSystem+WaterSourceCache`  
- `Game.Simulation.WaterSystem+SourceJob`  
- `Game.Simulation.WaterSystem+ReadCommandHelper`  
- `Game.Simulation.WaterSystem+TypeHandle`  


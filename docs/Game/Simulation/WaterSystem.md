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
public WaterSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddActiveReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddActiveReader(Unity.Jobs.JobHandle handle);
```

- `public AddSurfaceReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddSurfaceReader(Unity.Jobs.JobHandle handle);
```

- `public AddVelocitySurfaceReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddVelocitySurfaceReader(Unity.Jobs.JobHandle handle);
```

- `private BindTextures() : System.Void`  

```csharp
private System.Void BindTextures();
```

- `private BorderCircleIntersection(System.Boolean isX, System.Boolean isPositive, Unity.Mathematics.float2 center, System.Single radius, Unity.Mathematics.int2& result) : System.Boolean`  

```csharp
private System.Boolean BorderCircleIntersection(System.Boolean isX, System.Boolean isPositive, Unity.Mathematics.float2 center, System.Single radius, Unity.Mathematics.int2& result);
```

- `public static CalculateSourceMultiplier(Game.Simulation.WaterSourceData source, Unity.Mathematics.float3 pos) : System.Single`  

```csharp
public static System.Single CalculateSourceMultiplier(Game.Simulation.WaterSourceData source, Unity.Mathematics.float3 pos);
```

- `private CopyToHeightmapStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void CopyToHeightmapStep(UnityEngine.Rendering.CommandBuffer cmd);
```

- `public CreateByteArray<T>(Unity.Collections.NativeArray<T> src) : System.Byte[]`  

```csharp
public System.Byte[] CreateByteArray<T>(Unity.Collections.NativeArray<T> src);
```

- `private DepthStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void DepthStep(UnityEngine.Rendering.CommandBuffer cmd);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private EvaporateStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void EvaporateStep(UnityEngine.Rendering.CommandBuffer cmd);
```

- `private Game.IGPUSystem.get_Enabled() : System.Boolean`  

```csharp
private System.Boolean Game.IGPUSystem.get_Enabled();
```

- `public GetActive() : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetActive();
```

- `public static GetCell(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetCell(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize);
```

- `private static GetCellCoords(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize) : Unity.Mathematics.float2`  

```csharp
private static Unity.Mathematics.float2 GetCellCoords(Unity.Mathematics.float3 position, System.Int32 mapSize, Unity.Mathematics.int2 textureSize);
```

- `public GetDepth(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> waterMap) : Game.Simulation.SurfaceWater`  

```csharp
public Game.Simulation.SurfaceWater GetDepth(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> waterMap);
```

- `public GetDepths(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<Game.Simulation.SurfaceWater>`  

```csharp
public Unity.Collections.NativeArray<Game.Simulation.SurfaceWater> GetDepths(Unity.Jobs.JobHandle& deps);
```

- `public GetSurfaceData(Unity.Jobs.JobHandle& deps) : Game.Simulation.WaterSurfaceData`  

```csharp
public Game.Simulation.WaterSurfaceData GetSurfaceData(Unity.Jobs.JobHandle& deps);
```

- `public GetTimeStep() : System.Single`  

```csharp
public System.Single GetTimeStep();
```

- `public GetVelocitiesSurfaceData(Unity.Jobs.JobHandle& deps) : Game.Simulation.WaterSurfaceData`  

```csharp
public Game.Simulation.WaterSurfaceData GetVelocitiesSurfaceData(Unity.Jobs.JobHandle& deps);
```

- `private HasWater(Unity.Mathematics.float3 position) : System.Boolean`  

```csharp
private System.Boolean HasWater(Unity.Mathematics.float3 position);
```

- `private InitShader() : System.Void`  

```csharp
private System.Void InitShader();
```

- `private InitTextures() : System.Void`  

```csharp
private System.Void InitTextures();
```

- `public JobLoad() : System.Void`  

```csharp
public System.Void JobLoad();
```

- `private JobSaveToFile(Unity.Collections.NativeArray<Unity.Mathematics.float4> buffer) : System.Void`  

```csharp
private System.Void JobSaveToFile(Unity.Collections.NativeArray<Unity.Mathematics.float4> buffer);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `public OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
public System.Void OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd);
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private Reset() : System.Void`  

```csharp
private System.Void Reset();
```

- `private ResetActive(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void ResetActive(UnityEngine.Rendering.CommandBuffer cmd);
```

- `private ResetToLevel(System.Single level) : System.Void`  

```csharp
private System.Void ResetToLevel(System.Single level);
```

- `public ResetToSealevel() : System.Void`  

```csharp
public System.Void ResetToSealevel();
```

- `public Restart() : System.Void`  

```csharp
public System.Void Restart();
```

- `private RestoreHeightFromHeightmap(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void RestoreHeightFromHeightmap(UnityEngine.Rendering.CommandBuffer cmd);
```

- `public Save() : System.Void`  

```csharp
public System.Void Save();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private Simulate(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void Simulate(UnityEngine.Rendering.CommandBuffer cmd);
```

- `public static SourceMatchesDirection(Game.Simulation.WaterSourceData source, Game.Objects.Transform transform, Unity.Mathematics.float2 direction) : System.Boolean`  

```csharp
public static System.Boolean SourceMatchesDirection(Game.Simulation.WaterSourceData source, Game.Objects.Transform transform, Unity.Mathematics.float2 direction);
```

- `private SourceStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void SourceStep(UnityEngine.Rendering.CommandBuffer cmd);
```

- `public TerrainWillChange() : System.Void`  

```csharp
public System.Void TerrainWillChange();
```

- `public TerrainWillChangeFromBrush(Colossal.Mathematics.Bounds2 area) : System.Void`  

```csharp
public System.Void TerrainWillChangeFromBrush(Colossal.Mathematics.Bounds2 area);
```

- `private UpdateGPUReadback() : System.Void`  

```csharp
private System.Void UpdateGPUReadback();
```

- `private UpdateSaveReadback() : System.Void`  

```csharp
private System.Void UpdateSaveReadback();
```

- `private VelocityStep(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
private System.Void VelocityStep(UnityEngine.Rendering.CommandBuffer cmd);
```


## Nested types

- `Game.Simulation.WaterSystem+WaterSource`  
- `Game.Simulation.WaterSystem+QuadWaterBuffer`  
- `Game.Simulation.WaterSystem+WaterSourceCache`  
- `Game.Simulation.WaterSystem+SourceJob`  
- `Game.Simulation.WaterSystem+ReadCommandHelper`  
- `Game.Simulation.WaterSystem+TypeHandle`  


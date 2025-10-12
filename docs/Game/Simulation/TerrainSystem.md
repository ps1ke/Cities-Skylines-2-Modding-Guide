# Game.Simulation.TerrainSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Fields

- `private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback`  
- `private Unity.Collections.NativeArray<System.UInt16> m_CPUHeights`  
- `private Unity.Jobs.JobHandle m_CPUHeightReaders`  
- `private UnityEngine.RenderTexture m_Heightmap`  
- `private UnityEngine.RenderTexture m_HeightmapCascade`  
- `private UnityEngine.RenderTexture m_HeightmapDepth`  
- `private UnityEngine.RenderTexture m_WorldMapEditable`  
- `private UnityEngine.Vector4 m_MapOffsetScale`  
- `private System.Boolean m_HeightMapChanged`  
- `private Unity.Mathematics.int4 m_LastPreviewWrite`  
- `private Unity.Mathematics.int4 m_LastWorldPreviewWrite`  
- `private Unity.Mathematics.int4 m_LastWrite`  
- `private Unity.Mathematics.int4 m_LastWorldWrite`  
- `private Unity.Mathematics.int4 m_LastRequest`  
- `private System.Int32 m_FailCount`  
- `private UnityEngine.Vector4 m_WorldOffsetScale`  
- `private System.Boolean m_NewMap`  
- `private System.Boolean m_NewMapThisFrame`  
- `private System.Boolean m_Loaded`  
- `private System.Boolean m_HeightsReadyAfterLoading`  
- `private System.Boolean m_UpdateOutOfDate`  
- `private UnityEngine.ComputeShader m_AdjustTerrainCS`  
- `private System.Int32 m_ShiftTerrainKernal`  
- `private System.Int32 m_BlurHorzKernal`  
- `private System.Int32 m_BlurVertKernal`  
- `private System.Int32 m_SmoothTerrainKernal`  
- `private System.Int32 m_LevelTerrainKernal`  
- `private System.Int32 m_SlopeTerrainKernal`  
- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  
- `private UnityEngine.Rendering.CommandBuffer m_CascadeCB`  
- `private UnityEngine.Material m_TerrainBlit`  
- `private UnityEngine.Material m_ClipMaterial`  
- `private Unity.Entities.EntityQuery m_BrushQuery`  
- `private Unity.Mathematics.float2 <heightScaleOffset>k__BackingField`  
- `private Colossal.IO.AssetDatabase.TextureAsset <worldMapAsset>k__BackingField`  
- `private UnityEngine.Texture <worldHeightmap>k__BackingField`  
- `private Unity.Mathematics.float2 <playableArea>k__BackingField`  
- `private Unity.Mathematics.float2 <playableOffset>k__BackingField`  
- `private Unity.Mathematics.float2 <worldSize>k__BackingField`  
- `private Unity.Mathematics.float2 <worldOffset>k__BackingField`  
- `private Unity.Mathematics.float2 <worldHeightMinMax>k__BackingField`  
- `private Unity.Collections.NativeList<Game.Buildings.BuildingUtils+LotInfo> m_BuildingCullList`  
- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection> m_LaneCullList`  
- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleCullList`  
- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeCullList`  
- `private Unity.Jobs.JobHandle m_BuildingCull`  
- `private Unity.Jobs.JobHandle m_LaneCull`  
- `private Unity.Jobs.JobHandle m_AreaCull`  
- `private Unity.Jobs.JobHandle m_ClipMapCull`  
- `private Unity.Jobs.JobHandle m_CullFinished`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_BuildingUpgrade`  
- `private Unity.Jobs.JobHandle m_BuildingUpgradeDependencies`  
- `private System.Boolean <heightMapRenderRequired>k__BackingField`  
- `private System.Boolean[] <heightMapSliceUpdated>k__BackingField`  
- `private Unity.Mathematics.float4[] <heightMapViewport>k__BackingField`  
- `private Unity.Mathematics.float4[] <heightMapViewportUpdated>k__BackingField`  
- `private Unity.Mathematics.float4[] <heightMapCullArea>k__BackingField`  
- `private System.Boolean <freezeCascadeUpdates>k__BackingField`  
- `private System.Boolean[] <heightMapSliceUpdatedLast>k__BackingField`  
- `private Unity.Mathematics.float4 m_LastCullArea`  
- `private Unity.Mathematics.float4[] m_CascadeRanges`  
- `private UnityEngine.Vector4[] m_ShaderCascadeRanges`  
- `private Unity.Mathematics.float4 m_UpdateArea`  
- `private Unity.Mathematics.float4 m_TerrainChangeArea`  
- `private System.Boolean m_CascadeReset`  
- `private System.Boolean m_RoadUpdate`  
- `private System.Boolean m_AreaUpdate`  
- `private System.Boolean m_TerrainChange`  
- `private Unity.Entities.EntityQuery m_BuildingsChanged`  
- `private Unity.Entities.EntityQuery m_BuildingGroup`  
- `private Unity.Entities.EntityQuery m_RoadsChanged`  
- `private Unity.Entities.EntityQuery m_RoadsGroup`  
- `private Unity.Entities.EntityQuery m_EditorLotQuery`  
- `private Unity.Entities.EntityQuery m_AreasChanged`  
- `private Unity.Entities.EntityQuery m_AreasQuery`  
- `private System.Collections.Generic.List<Game.Simulation.TerrainSystem+CascadeCullInfo> m_CascadeCulling`  
- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+BuildingLotDraw> m_BuildingInstanceData`  
- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+LaneDraw> m_LaneInstanceData`  
- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleInstanceData`  
- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeInstanceData`  
- `private UnityEngine.Material m_MasterBuildingLotMaterial`  
- `private UnityEngine.Material m_MasterLaneMaterial`  
- `private UnityEngine.Material m_MasterAreaMaterial`  
- `private UnityEngine.Mesh m_LaneMesh`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Simulation.GroundHeightSystem m_GroundHeightSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapList`  
- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapBuffer`  
- `private UnityEngine.ComputeBuffer m_CurrentClipMap`  
- `private UnityEngine.Mesh m_ClipMesh`  
- `private UnityEngine.Mesh m_AreaClipMesh`  
- `private UnityEngine.Mesh+MeshDataArray m_AreaClipMeshData`  
- `private System.Boolean m_HasAreaClipMeshData`  
- `private Unity.Jobs.JobHandle m_AreaClipMeshDataDeps`  
- `private Game.Simulation.TerrainSystem+TerrainMinMaxMap m_TerrainMinMax`  
- `private Game.Simulation.TerrainSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kDefaultHeightmapWidth`  
- `public static readonly System.Int32 kDefaultHeightmapHeight`  
- `private static readonly Unity.Mathematics.float2 kDefaultMapSize`  
- `private static readonly Unity.Mathematics.float2 kDefaultMapOffset`  
- `private static readonly Unity.Mathematics.float2 kDefaultWorldSize`  
- `private static readonly Unity.Mathematics.float2 kDefaultWorldOffset`  
- `private static readonly Unity.Mathematics.float2 kDefaultHeightScaleOffset`  
- `private static System.Int32 <baseLod>k__BackingField`  
- `private static const System.Single kShiftTerrainAmount`  
- `private static const System.Single kSoftenTerrainAmount`  
- `private static const System.Single kSlopeAndLevelTerrainAmount`  
- `public static const System.Int32 kCascadeMax`  

## Properties

- `public UnityEngine.Vector4 VTScaleOffset { get }`  
- `public System.Boolean NewMap { get }`  
- `public UnityEngine.Texture heightmap { get }`  
- `public UnityEngine.Vector4 mapOffsetScale { get }`  
- `public Unity.Mathematics.float2 heightScaleOffset { get; set }`  
- `public Colossal.IO.AssetDatabase.TextureAsset worldMapAsset { get; set }`  
- `public UnityEngine.Texture worldHeightmap { get; set }`  
- `public Unity.Mathematics.float2 playableArea { get; private set }`  
- `public Unity.Mathematics.float2 playableOffset { get; private set }`  
- `public Unity.Mathematics.float2 worldSize { get; private set }`  
- `public Unity.Mathematics.float2 worldOffset { get; private set }`  
- `public Unity.Mathematics.float2 worldHeightMinMax { get; private set }`  
- `public Unity.Mathematics.float3 positionOffset { get }`  
- `public System.Boolean heightMapRenderRequired { get; private set }`  
- `public System.Boolean[] heightMapSliceUpdated { get; private set }`  
- `public Unity.Mathematics.float4[] heightMapViewport { get; private set }`  
- `public Unity.Mathematics.float4[] heightMapViewportUpdated { get; private set }`  
- `public Unity.Mathematics.float4[] heightMapSliceArea { get }`  
- `public Unity.Mathematics.float4[] heightMapCullArea { get; private set }`  
- `public System.Boolean freezeCascadeUpdates { get; set }`  
- `public System.Boolean[] heightMapSliceUpdatedLast { get; private set }`  
- `public Unity.Mathematics.float4 lastCullArea { get }`  
- `public static System.Int32 baseLod { get; private set }`  
- `private UnityEngine.ComputeBuffer clipMapBuffer { private get }`  
- `private System.Int32 clipMapInstances { private get }`  
- `public UnityEngine.Mesh areaClipMesh { get; private set }`  

## Constructors

- `public TerrainSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <UpdateGPUTerrain>b__227_0(UnityEngine.Experimental.Rendering.RenderGraphModule.RenderGraphContext ctx, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  
- `public AddCPUHeightReader(Unity.Jobs.JobHandle handle) : System.Void`  
- `public ApplyBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture) : System.Void`  
- `private ApplyToTerrain(UnityEngine.RenderTexture target, UnityEngine.RenderTexture source, System.Single delta, Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture, System.Boolean worldMap) : System.Void`  
- `public CalculateBuildingCullArea(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> geometryData, Unity.Mathematics.float4& area) : System.Boolean`  
- `public Clear() : System.Void`  
- `private ClipViewport(Unity.Mathematics.float4 Viewport) : Unity.Mathematics.float4`  
- `private CreateDefaultHeightmap(System.Int32 width, System.Int32 height) : UnityEngine.Texture2D`  
- `private CreateRoadMeshes() : System.Void`  
- `private CullCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, System.Int32 laneCount) : System.Void`  
- `public CullClipMapForView(Game.Rendering.Viewer viewer) : System.Void`  
- `private CullForCascades(Unity.Mathematics.float4 area, System.Boolean heightMapRenderRequired, System.Boolean roadsChanged, System.Boolean terrainAreasChanged, System.Boolean clipAreasChanged, System.Int32& laneCount) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private static DeserializeHeightmap<TReader>(TReader reader, System.String name, Unity.Collections.NativeArray`1[[System.UInt16, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& unfiltered, System.Boolean makeNoLongerReadable) : UnityEngine.Texture2D`  
- `private DestroyWorldMap() : System.Void`  
- `private DrawHeightAdjustments(UnityEngine.Rendering.CommandBuffer& cmdBuffer, System.Int32 cascade, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.RenderTargetBinding binding, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+BuildingLotDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+LaneDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lanes, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaTriangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, UnityEngine.Material& lotMaterial, UnityEngine.Material& laneMaterial, UnityEngine.Material& areaMaterial) : System.Void`  
- `private EnsureCPUHeights(System.Int32 length) : System.Void`  
- `private FinalizeTerrainData(UnityEngine.Texture2D map, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax) : System.Void`  
- `public GetBuildingUpgradeWriter(System.Int32 ExpectedAmount) : Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity>`  
- `public GetCascadeInfo(System.Int32& LODCount, System.Int32& baseLOD, Unity.Mathematics.float4x4& areas, Unity.Mathematics.float4& ranges, Unity.Mathematics.float4& size) : System.Void`  
- `public GetCascadeTexture() : UnityEngine.Texture`  
- `public GetHeightData(System.Boolean waitForPending = False) : Game.Simulation.TerrainHeightData`  
- `public GetLastMinMaxUpdate(Unity.Mathematics.float3& min, Unity.Mathematics.float3& max) : System.Void`  
- `public GetRoads() : Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection>`  
- `private GetTerrainAdjustmentSpeed(Game.Prefabs.TerraformingType type) : System.Single`  
- `public GetTerrainBounds() : UnityEngine.Bounds`  
- `public GetTerrainBrushUpdate(Unity.Mathematics.float4& viewport) : System.Boolean`  
- `public HandleNewMap() : System.Void`  
- `private InitializeTerrainData(UnityEngine.Texture2D inMap, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax) : System.Void`  
- `public static IsValidHeightmapFormat(UnityEngine.Texture2D tex) : System.Boolean`  
- `private LoadTerrain() : System.Void`  
- `public OnBuildingMoved(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnHeightsChanged() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Overlap(Unity.Mathematics.float4& A, Unity.Mathematics.float4& B) : System.Boolean`  
- `public PreviewBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture) : System.Void`  
- `private RenderCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer) : System.Void`  
- `public RenderCascades() : System.Void`  
- `private RenderWorldMapToCascade(Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer) : System.Void`  
- `public ReplaceHeightmap(UnityEngine.Texture2D inMap) : System.Void`  
- `public ReplaceWorldHeightmap(UnityEngine.Texture2D inMap) : System.Void`  
- `private SaveBitmap(Unity.Collections.NativeArray<System.UInt16> buffer, System.Int32 width, System.Int32 height) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `private static SerializeHeightmap<TWriter>(TWriter writer, UnityEngine.Texture heightmap) : System.Void`  
- `public SetBuildingUpgradeWriterDependency(Unity.Jobs.JobHandle handle) : System.Void`  
- `private static SetDefaultHeights(UnityEngine.Texture2D targetHeightmap) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private SetHeightmap(UnityEngine.Texture2D map) : System.Void`  
- `public SetTerrainProperties(Unity.Mathematics.float2 heightScaleOffset) : System.Void`  
- `private SetWorldHeightmap(UnityEngine.Texture2D map, System.Boolean isEditor) : System.Void`  
- `public TerrainHeightsReadyAfterLoading() : System.Void`  
- `private static ToR16(UnityEngine.Texture2D textureRGBA64) : UnityEngine.Texture2D`  
- `public TriggerAsyncChange() : System.Void`  
- `private UpdateCascades(System.Boolean isLoaded, System.Boolean heightsReadyAfterLoading) : System.Void`  
- `private UpdateGPUReadback() : System.Void`  
- `private UpdateGPUTerrain() : System.Void`  
- `public UpdateMinMax(Game.Tools.Brush brush, Colossal.Mathematics.Bounds2 area) : System.Void`  
- `private WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer) : System.Void`  
- `private WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer, Unity.Mathematics.int4 offsets) : System.Void`  

## Nested types

- `Game.Simulation.TerrainSystem+ShaderID`  
- `Game.Simulation.TerrainSystem+BuildingLotDraw`  
- `Game.Simulation.TerrainSystem+LaneSection`  
- `Game.Simulation.TerrainSystem+LaneDraw`  
- `Game.Simulation.TerrainSystem+AreaTriangle`  
- `Game.Simulation.TerrainSystem+AreaEdge`  
- `Game.Simulation.TerrainSystem+LaneFlags`  
- `Game.Simulation.TerrainSystem+CascadeCullInfo`  
- `Game.Simulation.TerrainSystem+ClipMapDraw`  
- `Game.Simulation.TerrainSystem+TerrainMinMaxMap`  
- `Game.Simulation.TerrainSystem+TerrainDesc`  
- `Game.Simulation.TerrainSystem+CullBuildingLotsJob`  
- `Game.Simulation.TerrainSystem+DequeBuildingLotsJob`  
- `Game.Simulation.TerrainSystem+CullRoadsJob`  
- `Game.Simulation.TerrainSystem+DequeBuildingDrawsJob`  
- `Game.Simulation.TerrainSystem+CullBuildingsCascadeJob`  
- `Game.Simulation.TerrainSystem+CullTrianglesJob`  
- `Game.Simulation.TerrainSystem+CullEdgesJob`  
- `Game.Simulation.TerrainSystem+GenerateClipDataJob`  
- `Game.Simulation.TerrainSystem+CullAreasJob`  
- `Game.Simulation.TerrainSystem+DequeTrianglesJob`  
- `Game.Simulation.TerrainSystem+DequeEdgesJob`  
- `Game.Simulation.TerrainSystem+GenerateAreaClipMeshJob`  
- `Game.Simulation.TerrainSystem+CullRoadsCacscadeJob`  
- `Game.Simulation.TerrainSystem+TypeHandle`  


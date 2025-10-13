# Game.Simulation.TerrainSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Code

```csharp
public class TerrainSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback;
    private Unity.Collections.NativeArray<System.UInt16> m_CPUHeights;
    private Unity.Jobs.JobHandle m_CPUHeightReaders;
    private UnityEngine.RenderTexture m_Heightmap;
    private UnityEngine.RenderTexture m_HeightmapCascade;
    private UnityEngine.RenderTexture m_HeightmapDepth;
    private UnityEngine.RenderTexture m_WorldMapEditable;
    private UnityEngine.Vector4 m_MapOffsetScale;
    private System.Boolean m_HeightMapChanged;
    private Unity.Mathematics.int4 m_LastPreviewWrite;
    private Unity.Mathematics.int4 m_LastWorldPreviewWrite;
    private Unity.Mathematics.int4 m_LastWrite;
    private Unity.Mathematics.int4 m_LastWorldWrite;
    private Unity.Mathematics.int4 m_LastRequest;
    private System.Int32 m_FailCount;
    private UnityEngine.Vector4 m_WorldOffsetScale;
    private System.Boolean m_NewMap;
    private System.Boolean m_NewMapThisFrame;
    private System.Boolean m_Loaded;
    private System.Boolean m_HeightsReadyAfterLoading;
    private System.Boolean m_UpdateOutOfDate;
    private UnityEngine.ComputeShader m_AdjustTerrainCS;
    private System.Int32 m_ShiftTerrainKernal;
    private System.Int32 m_BlurHorzKernal;
    private System.Int32 m_BlurVertKernal;
    private System.Int32 m_SmoothTerrainKernal;
    private System.Int32 m_LevelTerrainKernal;
    private System.Int32 m_SlopeTerrainKernal;
    private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
    private UnityEngine.Rendering.CommandBuffer m_CascadeCB;
    private UnityEngine.Material m_TerrainBlit;
    private UnityEngine.Material m_ClipMaterial;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Mathematics.float2 <heightScaleOffset>k__BackingField;
    private Colossal.IO.AssetDatabase.TextureAsset <worldMapAsset>k__BackingField;
    private UnityEngine.Texture <worldHeightmap>k__BackingField;
    private Unity.Mathematics.float2 <playableArea>k__BackingField;
    private Unity.Mathematics.float2 <playableOffset>k__BackingField;
    private Unity.Mathematics.float2 <worldSize>k__BackingField;
    private Unity.Mathematics.float2 <worldOffset>k__BackingField;
    private Unity.Mathematics.float2 <worldHeightMinMax>k__BackingField;
    private Unity.Collections.NativeList<Game.Buildings.BuildingUtils+LotInfo> m_BuildingCullList;
    private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection> m_LaneCullList;
    private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleCullList;
    private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeCullList;
    private Unity.Jobs.JobHandle m_BuildingCull;
    private Unity.Jobs.JobHandle m_LaneCull;
    private Unity.Jobs.JobHandle m_AreaCull;
    private Unity.Jobs.JobHandle m_ClipMapCull;
    private Unity.Jobs.JobHandle m_CullFinished;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_BuildingUpgrade;
    private Unity.Jobs.JobHandle m_BuildingUpgradeDependencies;
    private System.Boolean <heightMapRenderRequired>k__BackingField;
    private System.Boolean[] <heightMapSliceUpdated>k__BackingField;
    private Unity.Mathematics.float4[] <heightMapViewport>k__BackingField;
    private Unity.Mathematics.float4[] <heightMapViewportUpdated>k__BackingField;
    private Unity.Mathematics.float4[] <heightMapCullArea>k__BackingField;
    private System.Boolean <freezeCascadeUpdates>k__BackingField;
    private System.Boolean[] <heightMapSliceUpdatedLast>k__BackingField;
    private Unity.Mathematics.float4 m_LastCullArea;
    private Unity.Mathematics.float4[] m_CascadeRanges;
    private UnityEngine.Vector4[] m_ShaderCascadeRanges;
    private Unity.Mathematics.float4 m_UpdateArea;
    private Unity.Mathematics.float4 m_TerrainChangeArea;
    private System.Boolean m_CascadeReset;
    private System.Boolean m_RoadUpdate;
    private System.Boolean m_AreaUpdate;
    private System.Boolean m_TerrainChange;
    private Unity.Entities.EntityQuery m_BuildingsChanged;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Unity.Entities.EntityQuery m_RoadsChanged;
    private Unity.Entities.EntityQuery m_RoadsGroup;
    private Unity.Entities.EntityQuery m_EditorLotQuery;
    private Unity.Entities.EntityQuery m_AreasChanged;
    private Unity.Entities.EntityQuery m_AreasQuery;
    private System.Collections.Generic.List<Game.Simulation.TerrainSystem+CascadeCullInfo> m_CascadeCulling;
    private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+BuildingLotDraw> m_BuildingInstanceData;
    private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+LaneDraw> m_LaneInstanceData;
    private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleInstanceData;
    private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeInstanceData;
    private UnityEngine.Material m_MasterBuildingLotMaterial;
    private UnityEngine.Material m_MasterLaneMaterial;
    private UnityEngine.Material m_MasterAreaMaterial;
    private UnityEngine.Mesh m_LaneMesh;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.GroundHeightSystem m_GroundHeightSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapList;
    private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapBuffer;
    private UnityEngine.ComputeBuffer m_CurrentClipMap;
    private UnityEngine.Mesh m_ClipMesh;
    private UnityEngine.Mesh m_AreaClipMesh;
    private UnityEngine.Mesh+MeshDataArray m_AreaClipMeshData;
    private System.Boolean m_HasAreaClipMeshData;
    private Unity.Jobs.JobHandle m_AreaClipMeshDataDeps;
    private Game.Simulation.TerrainSystem+TerrainMinMaxMap m_TerrainMinMax;
    private Game.Simulation.TerrainSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kDefaultHeightmapWidth;
    public static readonly System.Int32 kDefaultHeightmapHeight;
    private static readonly Unity.Mathematics.float2 kDefaultMapSize;
    private static readonly Unity.Mathematics.float2 kDefaultMapOffset;
    private static readonly Unity.Mathematics.float2 kDefaultWorldSize;
    private static readonly Unity.Mathematics.float2 kDefaultWorldOffset;
    private static readonly Unity.Mathematics.float2 kDefaultHeightScaleOffset;
    private static System.Int32 <baseLod>k__BackingField;
    private static const System.Single kShiftTerrainAmount;
    private static const System.Single kSoftenTerrainAmount;
    private static const System.Single kSlopeAndLevelTerrainAmount;
    public static const System.Int32 kCascadeMax;

    public UnityEngine.Vector4 VTScaleOffset { get; }
    public System.Boolean NewMap { get; }
    public UnityEngine.Texture heightmap { get; }
    public UnityEngine.Vector4 mapOffsetScale { get; }
    public Unity.Mathematics.float2 heightScaleOffset { get; set; }
    public Colossal.IO.AssetDatabase.TextureAsset worldMapAsset { get; set; }
    public UnityEngine.Texture worldHeightmap { get; set; }
    public Unity.Mathematics.float2 playableArea { get; private set; }
    public Unity.Mathematics.float2 playableOffset { get; private set; }
    public Unity.Mathematics.float2 worldSize { get; private set; }
    public Unity.Mathematics.float2 worldOffset { get; private set; }
    public Unity.Mathematics.float2 worldHeightMinMax { get; private set; }
    public Unity.Mathematics.float3 positionOffset { get; }
    public System.Boolean heightMapRenderRequired { get; private set; }
    public System.Boolean[] heightMapSliceUpdated { get; private set; }
    public Unity.Mathematics.float4[] heightMapViewport { get; private set; }
    public Unity.Mathematics.float4[] heightMapViewportUpdated { get; private set; }
    public Unity.Mathematics.float4[] heightMapSliceArea { get; }
    public Unity.Mathematics.float4[] heightMapCullArea { get; private set; }
    public System.Boolean freezeCascadeUpdates { get; set; }
    public System.Boolean[] heightMapSliceUpdatedLast { get; private set; }
    public Unity.Mathematics.float4 lastCullArea { get; }
    public static System.Int32 baseLod { get; private set; }
    private UnityEngine.ComputeBuffer clipMapBuffer { private get; }
    private System.Int32 clipMapInstances { private get; }
    public UnityEngine.Mesh areaClipMesh { get; private set; }

    public TerrainSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void <UpdateGPUTerrain>b__227_0(UnityEngine.Experimental.Rendering.RenderGraphModule.RenderGraphContext ctx, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
    public System.Void AddCPUHeightReader(Unity.Jobs.JobHandle handle);
    public System.Void ApplyBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture);
    private System.Void ApplyToTerrain(UnityEngine.RenderTexture target, UnityEngine.RenderTexture source, System.Single delta, Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture, System.Boolean worldMap);
    public System.Boolean CalculateBuildingCullArea(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> geometryData, Unity.Mathematics.float4& area);
    public System.Void Clear();
    private Unity.Mathematics.float4 ClipViewport(Unity.Mathematics.float4 Viewport);
    private UnityEngine.Texture2D CreateDefaultHeightmap(System.Int32 width, System.Int32 height);
    private System.Void CreateRoadMeshes();
    private System.Void CullCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, System.Int32 laneCount);
    public System.Void CullClipMapForView(Game.Rendering.Viewer viewer);
    private System.Void CullForCascades(Unity.Mathematics.float4 area, System.Boolean heightMapRenderRequired, System.Boolean roadsChanged, System.Boolean terrainAreasChanged, System.Boolean clipAreasChanged, System.Int32& laneCount);
    public System.Void Deserialize<TReader>(TReader reader);
    private static UnityEngine.Texture2D DeserializeHeightmap<TReader>(TReader reader, System.String name, Unity.Collections.NativeArray`1[[System.UInt16, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& unfiltered, System.Boolean makeNoLongerReadable);
    private System.Void DestroyWorldMap();
    private System.Void DrawHeightAdjustments(UnityEngine.Rendering.CommandBuffer& cmdBuffer, System.Int32 cascade, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.RenderTargetBinding binding, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+BuildingLotDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+LaneDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lanes, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaTriangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, UnityEngine.Material& lotMaterial, UnityEngine.Material& laneMaterial, UnityEngine.Material& areaMaterial);
    private System.Void EnsureCPUHeights(System.Int32 length);
    private System.Void FinalizeTerrainData(UnityEngine.Texture2D map, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax);
    public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> GetBuildingUpgradeWriter(System.Int32 ExpectedAmount);
    public System.Void GetCascadeInfo(System.Int32& LODCount, System.Int32& baseLOD, Unity.Mathematics.float4x4& areas, Unity.Mathematics.float4& ranges, Unity.Mathematics.float4& size);
    public UnityEngine.Texture GetCascadeTexture();
    public Game.Simulation.TerrainHeightData GetHeightData(System.Boolean waitForPending);
    public System.Void GetLastMinMaxUpdate(Unity.Mathematics.float3& min, Unity.Mathematics.float3& max);
    public Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection> GetRoads();
    private System.Single GetTerrainAdjustmentSpeed(Game.Prefabs.TerraformingType type);
    public UnityEngine.Bounds GetTerrainBounds();
    public System.Boolean GetTerrainBrushUpdate(Unity.Mathematics.float4& viewport);
    public System.Void HandleNewMap();
    private System.Void InitializeTerrainData(UnityEngine.Texture2D inMap, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax);
    public static System.Boolean IsValidHeightmapFormat(UnityEngine.Texture2D tex);
    private System.Void LoadTerrain();
    public System.Void OnBuildingMoved(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    private System.Void OnHeightsChanged();
    protected virtual System.Void OnUpdate();
    private System.Boolean Overlap(Unity.Mathematics.float4& A, Unity.Mathematics.float4& B);
    public System.Void PreviewBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture);
    private System.Void RenderCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer);
    public System.Void RenderCascades();
    private System.Void RenderWorldMapToCascade(Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer);
    public System.Void ReplaceHeightmap(UnityEngine.Texture2D inMap);
    public System.Void ReplaceWorldHeightmap(UnityEngine.Texture2D inMap);
    private System.Void SaveBitmap(Unity.Collections.NativeArray<System.UInt16> buffer, System.Int32 width, System.Int32 height);
    public System.Void Serialize<TWriter>(TWriter writer);
    private static System.Void SerializeHeightmap<TWriter>(TWriter writer, UnityEngine.Texture heightmap);
    public System.Void SetBuildingUpgradeWriterDependency(Unity.Jobs.JobHandle handle);
    private static System.Void SetDefaultHeights(UnityEngine.Texture2D targetHeightmap);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void SetHeightmap(UnityEngine.Texture2D map);
    public System.Void SetTerrainProperties(Unity.Mathematics.float2 heightScaleOffset);
    private System.Void SetWorldHeightmap(UnityEngine.Texture2D map, System.Boolean isEditor);
    public System.Void TerrainHeightsReadyAfterLoading();
    private static UnityEngine.Texture2D ToR16(UnityEngine.Texture2D textureRGBA64);
    public System.Void TriggerAsyncChange();
    private System.Void UpdateCascades(System.Boolean isLoaded, System.Boolean heightsReadyAfterLoading);
    private System.Void UpdateGPUReadback();
    private System.Void UpdateGPUTerrain();
    public System.Void UpdateMinMax(Game.Tools.Brush brush, Colossal.Mathematics.Bounds2 area);
    private System.Void WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer);
    private System.Void WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer, Unity.Mathematics.int4 offsets);
}
```


## Fields

- `private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback`  

```csharp
private Colossal.Rendering.AsyncGPUReadbackHelper m_AsyncGPUReadback;
```

- `private Unity.Collections.NativeArray<System.UInt16> m_CPUHeights`  

```csharp
private Unity.Collections.NativeArray<System.UInt16> m_CPUHeights;
```

- `private Unity.Jobs.JobHandle m_CPUHeightReaders`  

```csharp
private Unity.Jobs.JobHandle m_CPUHeightReaders;
```

- `private UnityEngine.RenderTexture m_Heightmap`  

```csharp
private UnityEngine.RenderTexture m_Heightmap;
```

- `private UnityEngine.RenderTexture m_HeightmapCascade`  

```csharp
private UnityEngine.RenderTexture m_HeightmapCascade;
```

- `private UnityEngine.RenderTexture m_HeightmapDepth`  

```csharp
private UnityEngine.RenderTexture m_HeightmapDepth;
```

- `private UnityEngine.RenderTexture m_WorldMapEditable`  

```csharp
private UnityEngine.RenderTexture m_WorldMapEditable;
```

- `private UnityEngine.Vector4 m_MapOffsetScale`  

```csharp
private UnityEngine.Vector4 m_MapOffsetScale;
```

- `private System.Boolean m_HeightMapChanged`  

```csharp
private System.Boolean m_HeightMapChanged;
```

- `private Unity.Mathematics.int4 m_LastPreviewWrite`  

```csharp
private Unity.Mathematics.int4 m_LastPreviewWrite;
```

- `private Unity.Mathematics.int4 m_LastWorldPreviewWrite`  

```csharp
private Unity.Mathematics.int4 m_LastWorldPreviewWrite;
```

- `private Unity.Mathematics.int4 m_LastWrite`  

```csharp
private Unity.Mathematics.int4 m_LastWrite;
```

- `private Unity.Mathematics.int4 m_LastWorldWrite`  

```csharp
private Unity.Mathematics.int4 m_LastWorldWrite;
```

- `private Unity.Mathematics.int4 m_LastRequest`  

```csharp
private Unity.Mathematics.int4 m_LastRequest;
```

- `private System.Int32 m_FailCount`  

```csharp
private System.Int32 m_FailCount;
```

- `private UnityEngine.Vector4 m_WorldOffsetScale`  

```csharp
private UnityEngine.Vector4 m_WorldOffsetScale;
```

- `private System.Boolean m_NewMap`  

```csharp
private System.Boolean m_NewMap;
```

- `private System.Boolean m_NewMapThisFrame`  

```csharp
private System.Boolean m_NewMapThisFrame;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Boolean m_HeightsReadyAfterLoading`  

```csharp
private System.Boolean m_HeightsReadyAfterLoading;
```

- `private System.Boolean m_UpdateOutOfDate`  

```csharp
private System.Boolean m_UpdateOutOfDate;
```

- `private UnityEngine.ComputeShader m_AdjustTerrainCS`  

```csharp
private UnityEngine.ComputeShader m_AdjustTerrainCS;
```

- `private System.Int32 m_ShiftTerrainKernal`  

```csharp
private System.Int32 m_ShiftTerrainKernal;
```

- `private System.Int32 m_BlurHorzKernal`  

```csharp
private System.Int32 m_BlurHorzKernal;
```

- `private System.Int32 m_BlurVertKernal`  

```csharp
private System.Int32 m_BlurVertKernal;
```

- `private System.Int32 m_SmoothTerrainKernal`  

```csharp
private System.Int32 m_SmoothTerrainKernal;
```

- `private System.Int32 m_LevelTerrainKernal`  

```csharp
private System.Int32 m_LevelTerrainKernal;
```

- `private System.Int32 m_SlopeTerrainKernal`  

```csharp
private System.Int32 m_SlopeTerrainKernal;
```

- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
```

- `private UnityEngine.Rendering.CommandBuffer m_CascadeCB`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CascadeCB;
```

- `private UnityEngine.Material m_TerrainBlit`  

```csharp
private UnityEngine.Material m_TerrainBlit;
```

- `private UnityEngine.Material m_ClipMaterial`  

```csharp
private UnityEngine.Material m_ClipMaterial;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Mathematics.float2 <heightScaleOffset>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <heightScaleOffset>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.TextureAsset <worldMapAsset>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.TextureAsset <worldMapAsset>k__BackingField;
```

- `private UnityEngine.Texture <worldHeightmap>k__BackingField`  

```csharp
private UnityEngine.Texture <worldHeightmap>k__BackingField;
```

- `private Unity.Mathematics.float2 <playableArea>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <playableArea>k__BackingField;
```

- `private Unity.Mathematics.float2 <playableOffset>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <playableOffset>k__BackingField;
```

- `private Unity.Mathematics.float2 <worldSize>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <worldSize>k__BackingField;
```

- `private Unity.Mathematics.float2 <worldOffset>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <worldOffset>k__BackingField;
```

- `private Unity.Mathematics.float2 <worldHeightMinMax>k__BackingField`  

```csharp
private Unity.Mathematics.float2 <worldHeightMinMax>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.Buildings.BuildingUtils+LotInfo> m_BuildingCullList`  

```csharp
private Unity.Collections.NativeList<Game.Buildings.BuildingUtils+LotInfo> m_BuildingCullList;
```

- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection> m_LaneCullList`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection> m_LaneCullList;
```

- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleCullList`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleCullList;
```

- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeCullList`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeCullList;
```

- `private Unity.Jobs.JobHandle m_BuildingCull`  

```csharp
private Unity.Jobs.JobHandle m_BuildingCull;
```

- `private Unity.Jobs.JobHandle m_LaneCull`  

```csharp
private Unity.Jobs.JobHandle m_LaneCull;
```

- `private Unity.Jobs.JobHandle m_AreaCull`  

```csharp
private Unity.Jobs.JobHandle m_AreaCull;
```

- `private Unity.Jobs.JobHandle m_ClipMapCull`  

```csharp
private Unity.Jobs.JobHandle m_ClipMapCull;
```

- `private Unity.Jobs.JobHandle m_CullFinished`  

```csharp
private Unity.Jobs.JobHandle m_CullFinished;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_BuildingUpgrade`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> m_BuildingUpgrade;
```

- `private Unity.Jobs.JobHandle m_BuildingUpgradeDependencies`  

```csharp
private Unity.Jobs.JobHandle m_BuildingUpgradeDependencies;
```

- `private System.Boolean <heightMapRenderRequired>k__BackingField`  

```csharp
private System.Boolean <heightMapRenderRequired>k__BackingField;
```

- `private System.Boolean[] <heightMapSliceUpdated>k__BackingField`  

```csharp
private System.Boolean[] <heightMapSliceUpdated>k__BackingField;
```

- `private Unity.Mathematics.float4[] <heightMapViewport>k__BackingField`  

```csharp
private Unity.Mathematics.float4[] <heightMapViewport>k__BackingField;
```

- `private Unity.Mathematics.float4[] <heightMapViewportUpdated>k__BackingField`  

```csharp
private Unity.Mathematics.float4[] <heightMapViewportUpdated>k__BackingField;
```

- `private Unity.Mathematics.float4[] <heightMapCullArea>k__BackingField`  

```csharp
private Unity.Mathematics.float4[] <heightMapCullArea>k__BackingField;
```

- `private System.Boolean <freezeCascadeUpdates>k__BackingField`  

```csharp
private System.Boolean <freezeCascadeUpdates>k__BackingField;
```

- `private System.Boolean[] <heightMapSliceUpdatedLast>k__BackingField`  

```csharp
private System.Boolean[] <heightMapSliceUpdatedLast>k__BackingField;
```

- `private Unity.Mathematics.float4 m_LastCullArea`  

```csharp
private Unity.Mathematics.float4 m_LastCullArea;
```

- `private Unity.Mathematics.float4[] m_CascadeRanges`  

```csharp
private Unity.Mathematics.float4[] m_CascadeRanges;
```

- `private UnityEngine.Vector4[] m_ShaderCascadeRanges`  

```csharp
private UnityEngine.Vector4[] m_ShaderCascadeRanges;
```

- `private Unity.Mathematics.float4 m_UpdateArea`  

```csharp
private Unity.Mathematics.float4 m_UpdateArea;
```

- `private Unity.Mathematics.float4 m_TerrainChangeArea`  

```csharp
private Unity.Mathematics.float4 m_TerrainChangeArea;
```

- `private System.Boolean m_CascadeReset`  

```csharp
private System.Boolean m_CascadeReset;
```

- `private System.Boolean m_RoadUpdate`  

```csharp
private System.Boolean m_RoadUpdate;
```

- `private System.Boolean m_AreaUpdate`  

```csharp
private System.Boolean m_AreaUpdate;
```

- `private System.Boolean m_TerrainChange`  

```csharp
private System.Boolean m_TerrainChange;
```

- `private Unity.Entities.EntityQuery m_BuildingsChanged`  

```csharp
private Unity.Entities.EntityQuery m_BuildingsChanged;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Unity.Entities.EntityQuery m_RoadsChanged`  

```csharp
private Unity.Entities.EntityQuery m_RoadsChanged;
```

- `private Unity.Entities.EntityQuery m_RoadsGroup`  

```csharp
private Unity.Entities.EntityQuery m_RoadsGroup;
```

- `private Unity.Entities.EntityQuery m_EditorLotQuery`  

```csharp
private Unity.Entities.EntityQuery m_EditorLotQuery;
```

- `private Unity.Entities.EntityQuery m_AreasChanged`  

```csharp
private Unity.Entities.EntityQuery m_AreasChanged;
```

- `private Unity.Entities.EntityQuery m_AreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreasQuery;
```

- `private System.Collections.Generic.List<Game.Simulation.TerrainSystem+CascadeCullInfo> m_CascadeCulling`  

```csharp
private System.Collections.Generic.List<Game.Simulation.TerrainSystem+CascadeCullInfo> m_CascadeCulling;
```

- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+BuildingLotDraw> m_BuildingInstanceData`  

```csharp
private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+BuildingLotDraw> m_BuildingInstanceData;
```

- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+LaneDraw> m_LaneInstanceData`  

```csharp
private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+LaneDraw> m_LaneInstanceData;
```

- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleInstanceData`  

```csharp
private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaTriangle> m_TriangleInstanceData;
```

- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeInstanceData`  

```csharp
private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+AreaEdge> m_EdgeInstanceData;
```

- `private UnityEngine.Material m_MasterBuildingLotMaterial`  

```csharp
private UnityEngine.Material m_MasterBuildingLotMaterial;
```

- `private UnityEngine.Material m_MasterLaneMaterial`  

```csharp
private UnityEngine.Material m_MasterLaneMaterial;
```

- `private UnityEngine.Material m_MasterAreaMaterial`  

```csharp
private UnityEngine.Material m_MasterAreaMaterial;
```

- `private UnityEngine.Mesh m_LaneMesh`  

```csharp
private UnityEngine.Mesh m_LaneMesh;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.GroundHeightSystem m_GroundHeightSystem`  

```csharp
private Game.Simulation.GroundHeightSystem m_GroundHeightSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapList`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapList;
```

- `private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapBuffer`  

```csharp
private Game.Rendering.Utilities.ManagedStructuredBuffers<Game.Simulation.TerrainSystem+ClipMapDraw> m_ClipMapBuffer;
```

- `private UnityEngine.ComputeBuffer m_CurrentClipMap`  

```csharp
private UnityEngine.ComputeBuffer m_CurrentClipMap;
```

- `private UnityEngine.Mesh m_ClipMesh`  

```csharp
private UnityEngine.Mesh m_ClipMesh;
```

- `private UnityEngine.Mesh m_AreaClipMesh`  

```csharp
private UnityEngine.Mesh m_AreaClipMesh;
```

- `private UnityEngine.Mesh+MeshDataArray m_AreaClipMeshData`  

```csharp
private UnityEngine.Mesh+MeshDataArray m_AreaClipMeshData;
```

- `private System.Boolean m_HasAreaClipMeshData`  

```csharp
private System.Boolean m_HasAreaClipMeshData;
```

- `private Unity.Jobs.JobHandle m_AreaClipMeshDataDeps`  

```csharp
private Unity.Jobs.JobHandle m_AreaClipMeshDataDeps;
```

- `private Game.Simulation.TerrainSystem+TerrainMinMaxMap m_TerrainMinMax`  

```csharp
private Game.Simulation.TerrainSystem+TerrainMinMaxMap m_TerrainMinMax;
```

- `private Game.Simulation.TerrainSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TerrainSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kDefaultHeightmapWidth`  

```csharp
public static readonly System.Int32 kDefaultHeightmapWidth;
```

- `public static readonly System.Int32 kDefaultHeightmapHeight`  

```csharp
public static readonly System.Int32 kDefaultHeightmapHeight;
```

- `private static readonly Unity.Mathematics.float2 kDefaultMapSize`  

```csharp
private static readonly Unity.Mathematics.float2 kDefaultMapSize;
```

- `private static readonly Unity.Mathematics.float2 kDefaultMapOffset`  

```csharp
private static readonly Unity.Mathematics.float2 kDefaultMapOffset;
```

- `private static readonly Unity.Mathematics.float2 kDefaultWorldSize`  

```csharp
private static readonly Unity.Mathematics.float2 kDefaultWorldSize;
```

- `private static readonly Unity.Mathematics.float2 kDefaultWorldOffset`  

```csharp
private static readonly Unity.Mathematics.float2 kDefaultWorldOffset;
```

- `private static readonly Unity.Mathematics.float2 kDefaultHeightScaleOffset`  

```csharp
private static readonly Unity.Mathematics.float2 kDefaultHeightScaleOffset;
```

- `private static System.Int32 <baseLod>k__BackingField`  

```csharp
private static System.Int32 <baseLod>k__BackingField;
```

- `private static const System.Single kShiftTerrainAmount`  

```csharp
private static const System.Single kShiftTerrainAmount;
```

- `private static const System.Single kSoftenTerrainAmount`  

```csharp
private static const System.Single kSoftenTerrainAmount;
```

- `private static const System.Single kSlopeAndLevelTerrainAmount`  

```csharp
private static const System.Single kSlopeAndLevelTerrainAmount;
```

- `public static const System.Int32 kCascadeMax`  

```csharp
public static const System.Int32 kCascadeMax;
```


## Properties

- `public UnityEngine.Vector4 VTScaleOffset { get }`  

```csharp
public UnityEngine.Vector4 VTScaleOffset { get; }
```

- `public System.Boolean NewMap { get }`  

```csharp
public System.Boolean NewMap { get; }
```

- `public UnityEngine.Texture heightmap { get }`  

```csharp
public UnityEngine.Texture heightmap { get; }
```

- `public UnityEngine.Vector4 mapOffsetScale { get }`  

```csharp
public UnityEngine.Vector4 mapOffsetScale { get; }
```

- `public Unity.Mathematics.float2 heightScaleOffset { get; set }`  

```csharp
public Unity.Mathematics.float2 heightScaleOffset { get; set; }
```

- `public Colossal.IO.AssetDatabase.TextureAsset worldMapAsset { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.TextureAsset worldMapAsset { get; set; }
```

- `public UnityEngine.Texture worldHeightmap { get; set }`  

```csharp
public UnityEngine.Texture worldHeightmap { get; set; }
```

- `public Unity.Mathematics.float2 playableArea { get; private set }`  

```csharp
public Unity.Mathematics.float2 playableArea { get; private set; }
```

- `public Unity.Mathematics.float2 playableOffset { get; private set }`  

```csharp
public Unity.Mathematics.float2 playableOffset { get; private set; }
```

- `public Unity.Mathematics.float2 worldSize { get; private set }`  

```csharp
public Unity.Mathematics.float2 worldSize { get; private set; }
```

- `public Unity.Mathematics.float2 worldOffset { get; private set }`  

```csharp
public Unity.Mathematics.float2 worldOffset { get; private set; }
```

- `public Unity.Mathematics.float2 worldHeightMinMax { get; private set }`  

```csharp
public Unity.Mathematics.float2 worldHeightMinMax { get; private set; }
```

- `public Unity.Mathematics.float3 positionOffset { get }`  

```csharp
public Unity.Mathematics.float3 positionOffset { get; }
```

- `public System.Boolean heightMapRenderRequired { get; private set }`  

```csharp
public System.Boolean heightMapRenderRequired { get; private set; }
```

- `public System.Boolean[] heightMapSliceUpdated { get; private set }`  

```csharp
public System.Boolean[] heightMapSliceUpdated { get; private set; }
```

- `public Unity.Mathematics.float4[] heightMapViewport { get; private set }`  

```csharp
public Unity.Mathematics.float4[] heightMapViewport { get; private set; }
```

- `public Unity.Mathematics.float4[] heightMapViewportUpdated { get; private set }`  

```csharp
public Unity.Mathematics.float4[] heightMapViewportUpdated { get; private set; }
```

- `public Unity.Mathematics.float4[] heightMapSliceArea { get }`  

```csharp
public Unity.Mathematics.float4[] heightMapSliceArea { get; }
```

- `public Unity.Mathematics.float4[] heightMapCullArea { get; private set }`  

```csharp
public Unity.Mathematics.float4[] heightMapCullArea { get; private set; }
```

- `public System.Boolean freezeCascadeUpdates { get; set }`  

```csharp
public System.Boolean freezeCascadeUpdates { get; set; }
```

- `public System.Boolean[] heightMapSliceUpdatedLast { get; private set }`  

```csharp
public System.Boolean[] heightMapSliceUpdatedLast { get; private set; }
```

- `public Unity.Mathematics.float4 lastCullArea { get }`  

```csharp
public Unity.Mathematics.float4 lastCullArea { get; }
```

- `public static System.Int32 baseLod { get; private set }`  

```csharp
public static System.Int32 baseLod { get; private set; }
```

- `private UnityEngine.ComputeBuffer clipMapBuffer { private get }`  

```csharp
private UnityEngine.ComputeBuffer clipMapBuffer { private get; }
```

- `private System.Int32 clipMapInstances { private get }`  

```csharp
private System.Int32 clipMapInstances { private get; }
```

- `public UnityEngine.Mesh areaClipMesh { get; private set }`  

```csharp
public UnityEngine.Mesh areaClipMesh { get; private set; }
```


## Constructors

- `public TerrainSystem()`  

```csharp
public TerrainSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <UpdateGPUTerrain>b__227_0(UnityEngine.Experimental.Rendering.RenderGraphModule.RenderGraphContext ctx, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  

```csharp
private System.Void <UpdateGPUTerrain>b__227_0(UnityEngine.Experimental.Rendering.RenderGraphModule.RenderGraphContext ctx, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `public AddCPUHeightReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddCPUHeightReader(Unity.Jobs.JobHandle handle);
```

- `public ApplyBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture) : System.Void`  

```csharp
public System.Void ApplyBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture);
```

- `private ApplyToTerrain(UnityEngine.RenderTexture target, UnityEngine.RenderTexture source, System.Single delta, Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture, System.Boolean worldMap) : System.Void`  

```csharp
private System.Void ApplyToTerrain(UnityEngine.RenderTexture target, UnityEngine.RenderTexture source, System.Single delta, Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture, System.Boolean worldMap);
```

- `public CalculateBuildingCullArea(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> geometryData, Unity.Mathematics.float4& area) : System.Boolean`  

```csharp
public System.Boolean CalculateBuildingCullArea(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> geometryData, Unity.Mathematics.float4& area);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `private ClipViewport(Unity.Mathematics.float4 Viewport) : Unity.Mathematics.float4`  

```csharp
private Unity.Mathematics.float4 ClipViewport(Unity.Mathematics.float4 Viewport);
```

- `private CreateDefaultHeightmap(System.Int32 width, System.Int32 height) : UnityEngine.Texture2D`  

```csharp
private UnityEngine.Texture2D CreateDefaultHeightmap(System.Int32 width, System.Int32 height);
```

- `private CreateRoadMeshes() : System.Void`  

```csharp
private System.Void CreateRoadMeshes();
```

- `private CullCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, System.Int32 laneCount) : System.Void`  

```csharp
private System.Void CullCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, System.Int32 laneCount);
```

- `public CullClipMapForView(Game.Rendering.Viewer viewer) : System.Void`  

```csharp
public System.Void CullClipMapForView(Game.Rendering.Viewer viewer);
```

- `private CullForCascades(Unity.Mathematics.float4 area, System.Boolean heightMapRenderRequired, System.Boolean roadsChanged, System.Boolean terrainAreasChanged, System.Boolean clipAreasChanged, System.Int32& laneCount) : System.Void`  

```csharp
private System.Void CullForCascades(Unity.Mathematics.float4 area, System.Boolean heightMapRenderRequired, System.Boolean roadsChanged, System.Boolean terrainAreasChanged, System.Boolean clipAreasChanged, System.Int32& laneCount);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private static DeserializeHeightmap<TReader>(TReader reader, System.String name, Unity.Collections.NativeArray`1[[System.UInt16, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& unfiltered, System.Boolean makeNoLongerReadable) : UnityEngine.Texture2D`  

```csharp
private static UnityEngine.Texture2D DeserializeHeightmap<TReader>(TReader reader, System.String name, Unity.Collections.NativeArray`1[[System.UInt16, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& unfiltered, System.Boolean makeNoLongerReadable);
```

- `private DestroyWorldMap() : System.Void`  

```csharp
private System.Void DestroyWorldMap();
```

- `private DrawHeightAdjustments(UnityEngine.Rendering.CommandBuffer& cmdBuffer, System.Int32 cascade, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.RenderTargetBinding binding, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+BuildingLotDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+LaneDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lanes, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaTriangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, UnityEngine.Material& lotMaterial, UnityEngine.Material& laneMaterial, UnityEngine.Material& areaMaterial) : System.Void`  

```csharp
private System.Void DrawHeightAdjustments(UnityEngine.Rendering.CommandBuffer& cmdBuffer, System.Int32 cascade, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.RenderTargetBinding binding, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+BuildingLotDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+LaneDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lanes, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaTriangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, UnityEngine.Material& lotMaterial, UnityEngine.Material& laneMaterial, UnityEngine.Material& areaMaterial);
```

- `private EnsureCPUHeights(System.Int32 length) : System.Void`  

```csharp
private System.Void EnsureCPUHeights(System.Int32 length);
```

- `private FinalizeTerrainData(UnityEngine.Texture2D map, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax) : System.Void`  

```csharp
private System.Void FinalizeTerrainData(UnityEngine.Texture2D map, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax);
```

- `public GetBuildingUpgradeWriter(System.Int32 ExpectedAmount) : Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity> GetBuildingUpgradeWriter(System.Int32 ExpectedAmount);
```

- `public GetCascadeInfo(System.Int32& LODCount, System.Int32& baseLOD, Unity.Mathematics.float4x4& areas, Unity.Mathematics.float4& ranges, Unity.Mathematics.float4& size) : System.Void`  

```csharp
public System.Void GetCascadeInfo(System.Int32& LODCount, System.Int32& baseLOD, Unity.Mathematics.float4x4& areas, Unity.Mathematics.float4& ranges, Unity.Mathematics.float4& size);
```

- `public GetCascadeTexture() : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture GetCascadeTexture();
```

- `public GetHeightData(System.Boolean waitForPending = False) : Game.Simulation.TerrainHeightData`  

```csharp
public Game.Simulation.TerrainHeightData GetHeightData(System.Boolean waitForPending);
```

- `public GetLastMinMaxUpdate(Unity.Mathematics.float3& min, Unity.Mathematics.float3& max) : System.Void`  

```csharp
public System.Void GetLastMinMaxUpdate(Unity.Mathematics.float3& min, Unity.Mathematics.float3& max);
```

- `public GetRoads() : Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection>`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection> GetRoads();
```

- `private GetTerrainAdjustmentSpeed(Game.Prefabs.TerraformingType type) : System.Single`  

```csharp
private System.Single GetTerrainAdjustmentSpeed(Game.Prefabs.TerraformingType type);
```

- `public GetTerrainBounds() : UnityEngine.Bounds`  

```csharp
public UnityEngine.Bounds GetTerrainBounds();
```

- `public GetTerrainBrushUpdate(Unity.Mathematics.float4& viewport) : System.Boolean`  

```csharp
public System.Boolean GetTerrainBrushUpdate(Unity.Mathematics.float4& viewport);
```

- `public HandleNewMap() : System.Void`  

```csharp
public System.Void HandleNewMap();
```

- `private InitializeTerrainData(UnityEngine.Texture2D inMap, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax) : System.Void`  

```csharp
private System.Void InitializeTerrainData(UnityEngine.Texture2D inMap, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax);
```

- `public static IsValidHeightmapFormat(UnityEngine.Texture2D tex) : System.Boolean`  

```csharp
public static System.Boolean IsValidHeightmapFormat(UnityEngine.Texture2D tex);
```

- `private LoadTerrain() : System.Void`  

```csharp
private System.Void LoadTerrain();
```

- `public OnBuildingMoved(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void OnBuildingMoved(Unity.Entities.Entity entity);
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

- `private OnHeightsChanged() : System.Void`  

```csharp
private System.Void OnHeightsChanged();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private Overlap(Unity.Mathematics.float4& A, Unity.Mathematics.float4& B) : System.Boolean`  

```csharp
private System.Boolean Overlap(Unity.Mathematics.float4& A, Unity.Mathematics.float4& B);
```

- `public PreviewBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture) : System.Void`  

```csharp
public System.Void PreviewBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture);
```

- `private RenderCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer) : System.Void`  

```csharp
private System.Void RenderCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer);
```

- `public RenderCascades() : System.Void`  

```csharp
public System.Void RenderCascades();
```

- `private RenderWorldMapToCascade(Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer) : System.Void`  

```csharp
private System.Void RenderWorldMapToCascade(Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer);
```

- `public ReplaceHeightmap(UnityEngine.Texture2D inMap) : System.Void`  

```csharp
public System.Void ReplaceHeightmap(UnityEngine.Texture2D inMap);
```

- `public ReplaceWorldHeightmap(UnityEngine.Texture2D inMap) : System.Void`  

```csharp
public System.Void ReplaceWorldHeightmap(UnityEngine.Texture2D inMap);
```

- `private SaveBitmap(Unity.Collections.NativeArray<System.UInt16> buffer, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
private System.Void SaveBitmap(Unity.Collections.NativeArray<System.UInt16> buffer, System.Int32 width, System.Int32 height);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `private static SerializeHeightmap<TWriter>(TWriter writer, UnityEngine.Texture heightmap) : System.Void`  

```csharp
private static System.Void SerializeHeightmap<TWriter>(TWriter writer, UnityEngine.Texture heightmap);
```

- `public SetBuildingUpgradeWriterDependency(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void SetBuildingUpgradeWriterDependency(Unity.Jobs.JobHandle handle);
```

- `private static SetDefaultHeights(UnityEngine.Texture2D targetHeightmap) : System.Void`  

```csharp
private static System.Void SetDefaultHeights(UnityEngine.Texture2D targetHeightmap);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private SetHeightmap(UnityEngine.Texture2D map) : System.Void`  

```csharp
private System.Void SetHeightmap(UnityEngine.Texture2D map);
```

- `public SetTerrainProperties(Unity.Mathematics.float2 heightScaleOffset) : System.Void`  

```csharp
public System.Void SetTerrainProperties(Unity.Mathematics.float2 heightScaleOffset);
```

- `private SetWorldHeightmap(UnityEngine.Texture2D map, System.Boolean isEditor) : System.Void`  

```csharp
private System.Void SetWorldHeightmap(UnityEngine.Texture2D map, System.Boolean isEditor);
```

- `public TerrainHeightsReadyAfterLoading() : System.Void`  

```csharp
public System.Void TerrainHeightsReadyAfterLoading();
```

- `private static ToR16(UnityEngine.Texture2D textureRGBA64) : UnityEngine.Texture2D`  

```csharp
private static UnityEngine.Texture2D ToR16(UnityEngine.Texture2D textureRGBA64);
```

- `public TriggerAsyncChange() : System.Void`  

```csharp
public System.Void TriggerAsyncChange();
```

- `private UpdateCascades(System.Boolean isLoaded, System.Boolean heightsReadyAfterLoading) : System.Void`  

```csharp
private System.Void UpdateCascades(System.Boolean isLoaded, System.Boolean heightsReadyAfterLoading);
```

- `private UpdateGPUReadback() : System.Void`  

```csharp
private System.Void UpdateGPUReadback();
```

- `private UpdateGPUTerrain() : System.Void`  

```csharp
private System.Void UpdateGPUTerrain();
```

- `public UpdateMinMax(Game.Tools.Brush brush, Colossal.Mathematics.Bounds2 area) : System.Void`  

```csharp
public System.Void UpdateMinMax(Game.Tools.Brush brush, Colossal.Mathematics.Bounds2 area);
```

- `private WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer) : System.Void`  

```csharp
private System.Void WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer);
```

- `private WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer, Unity.Mathematics.int4 offsets) : System.Void`  

```csharp
private System.Void WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer, Unity.Mathematics.int4 offsets);
```


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


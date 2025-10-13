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
[Preserve]
	public TerrainSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private <UpdateGPUTerrain>b__227_0(UnityEngine.Experimental.Rendering.RenderGraphModule.RenderGraphContext ctx, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  

```csharp
private System.Void <UpdateGPUTerrain>b__227_0(UnityEngine.Experimental.Rendering.RenderGraphModule.RenderGraphContext ctx, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `public AddCPUHeightReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddCPUHeightReader(JobHandle handle)
	{
		m_CPUHeightReaders = JobHandle.CombineDependencies(m_CPUHeightReaders, handle);
	}
```

- `public ApplyBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture) : System.Void`  

```csharp
public void ApplyBrush(TerraformingType type, Bounds2 area, Brush brush, Texture texture)
	{
		m_WaterSystem.TerrainWillChangeFromBrush(area);
		ApplyToTerrain(m_Heightmap, null, UnityEngine.Time.unscaledDeltaTime, type, area, brush, texture, worldMap: false);
		ApplyToTerrain(m_WorldMapEditable, null, UnityEngine.Time.unscaledDeltaTime, type, area, brush, texture, worldMap: true);
		UpdateMinMax(brush, area);
		TriggerAsyncChange();
	}
```

- `private ApplyToTerrain(UnityEngine.RenderTexture target, UnityEngine.RenderTexture source, System.Single delta, Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture, System.Boolean worldMap) : System.Void`  

```csharp
private void ApplyToTerrain(RenderTexture target, RenderTexture source, float delta, TerraformingType type, Bounds2 area, Brush brush, Texture texture, bool worldMap)
	{
		if (target == null || !target.IsCreated())
		{
			return;
		}
		if (delta == 0f || brush.m_Strength == 0f)
		{
			if (worldMap && source != null && m_LastWorldPreviewWrite.z != 0)
			{
				m_CommandBuffer.Clear();
				m_CommandBuffer.CopyTexture(source, 0, 0, m_LastWorldPreviewWrite.x, m_LastWorldPreviewWrite.y, m_LastWorldPreviewWrite.z, m_LastWorldPreviewWrite.w, target, 0, 0, m_LastWorldPreviewWrite.x, m_LastWorldPreviewWrite.y);
				Graphics.ExecuteCommandBuffer(m_CommandBuffer);
				m_LastWorldPreviewWrite = Unity.Mathematics.int4.zero;
			}
			if (!worldMap && source != null && m_LastPreviewWrite.z != 0)
			{
				m_CommandBuffer.Clear();
				m_CommandBuffer.CopyTexture(source, 0, 0, m_LastPreviewWrite.x, m_LastPreviewWrite.y, m_LastPreviewWrite.z, m_LastPreviewWrite.w, target, 0, 0, m_LastPreviewWrite.x, m_LastPreviewWrite.y);
				Graphics.ExecuteCommandBuffer(m_CommandBuffer);
				m_LastPreviewWrite = Unity.Mathematics.int4.zero;
			}
			return;
		}
		float x = delta * brush.m_Strength * GetTerrainAdjustmentSpeed(type) / heightScaleOffset.x;
		float2 @float = (worldMap ? worldSize : playableArea);
		float2 float2 = (worldMap ? worldOffset : playableOffset);
		float num = math.max(@float.x, @float.y);
		float2 float3 = (brush.m_Position.xz - float2) / @float;
		m_GroundHeightSystem.GetUpdateBuffer().Add(in area);
		if (math.lengthsq(m_UpdateArea) > 0f)
		{
			m_UpdateArea.xy = math.min(m_UpdateArea.xy, area.min);
			m_UpdateArea.zw = math.max(m_UpdateArea.zw, area.max);
		}
		else
		{
			m_UpdateArea = new float4(area.min, area.max);
		}
		if (!m_TerrainChange)
		{
			m_TerrainChange = true;
			m_TerrainChangeArea = new float4(area.min, area.max);
		}
		else
		{
			m_TerrainChangeArea.xy = math.min(m_TerrainChangeArea.xy, area.min);
			m_TerrainChangeArea.zw = math.max(m_TerrainChangeArea.zw, area.max);
		}
		area.min -= float2;
		area.max -= float2;
		area.min /= @float;
		area.max /= @float;
		int4 @int = new int4((int)math.max(math.floor(area.min.x * (float)target.width), 0f), (int)math.max(math.floor(area.min.y * (float)target.height), 0f), (int)math.min(math.ceil(area.max.x * (float)target.width), target.width - 1), (int)math.min(math.ceil(area.max.y * (float)target.height), target.height - 1));
		Vector4 val = new Vector4(float3.x, float3.y, brush.m_Size / num * 0.5f, brush.m_Angle);
		int num2 = @int.z - @int.x + 1;
		int num3 = @int.w - @int.y + 1;
		int threadGroupsX = (num2 + 7) / 8;
		int threadGroupsY = (num3 + 7) / 8;
		m_CommandBuffer.Clear();
		int4 int2 = new int4(math.max(@int.x - 2, 0), math.max(@int.y - 2, 0), num2 + 4, num3 + 4);
		if (int2.x + int2.z < 0 || int2.x > target.width || int2.y + int2.w < 0 || int2.y > target.height || num2 <= 0 || num3 <= 0)
		{
			return;
		}
		if (int2.x + int2.z > target.width)
		{
			int2.z = target.width - int2.x;
		}
		if (int2.y + int2.w > target.height)
		{
			int2.w = target.height - int2.y;
		}
		if (source != null)
		{
			if (worldMap)
			{
				if (m_LastWorldPreviewWrite.z == 0)
				{
					m_CommandBuffer.CopyTexture(source, target);
				}
				else
				{
					m_CommandBuffer.CopyTexture(source, 0, 0, m_LastWorldPreviewWrite.x, m_LastWorldPreviewWrite.y, m_LastWorldPreviewWrite.z, m_LastWorldPreviewWrite.w, target, 0, 0, m_LastWorldPreviewWrite.x, m_LastWorldPreviewWrite.y);
				}
				m_LastWorldPreviewWrite = int2;
			}
			else
			{
				if (m_LastPreviewWrite.z == 0)
				{
					m_CommandBuffer.CopyTexture(source, target);
				}
				else
				{
					m_CommandBuffer.CopyTexture(source, 0, 0, m_LastPreviewWrite.x, m_LastPreviewWrite.y, m_LastPreviewWrite.z, m_LastPreviewWrite.w, target, 0, 0, m_LastPreviewWrite.x, m_LastPreviewWrite.y);
					float4 float4 = new float4((float)m_LastPreviewWrite.x * (1f / (float)target.width), (float)m_LastPreviewWrite.y * (1f / (float)target.width), (float)m_LastPreviewWrite.z * (1f / (float)target.width), (float)m_LastPreviewWrite.w * (1f / (float)target.width));
					float4 float5 = new float4(float2 + float4.xy * @float, float2 + (float4.xy + float4.zw) * @float);
					m_UpdateArea.xy = math.min(m_UpdateArea.xy, float5.xy);
					m_UpdateArea.zw = math.max(m_UpdateArea.zw, float5.zw);
				}
				m_LastPreviewWrite = int2;
			}
		}
		else if (worldMap)
		{
			if (m_LastWorldWrite.z == 0)
			{
				m_LastWorldWrite = int2;
			}
			else
			{
				int2 int3 = new int2(math.min(m_LastWorldWrite.x, int2.x), math.min(m_LastWorldWrite.y, int2.y));
				int2 int4 = new int2(math.max(m_LastWorldWrite.x + m_LastWorldWrite.z, int2.x + int2.z), math.max(m_LastWorldWrite.y + m_LastWorldWrite.w, int2.y + int2.w));
				m_LastWorldWrite.xy = int3;
				m_LastWorldWrite.zw = int4 - int3;
			}
		}
		else if (m_LastWrite.z == 0)
		{
			m_LastWrite = int2;
		}
		else
		{
			int2 int5 = new int2(math.min(m_LastWrite.x, int2.x), math.min(m_LastWrite.y, int2.y));
			int2 int6 = new int2(math.max(m_LastWrite.x + m_LastWrite.z, int2.x + int2.z), math.max(m_LastWrite.y + m_LastWrite.w, int2.y + int2.w));
			m_LastWrite.xy = int5;
			m_LastWrite.zw = int6 - int5;
		}
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._CenterSizeRotation, val);
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._Dims, new Vector4(num, target.width, target.height, 0f));
		int num4 = 0;
		Vector4 val2 = new Vector4(x, 0f, 0f, 0f);
		Vector4 val3 = Vector4.zero;
		switch (type)
		{
		case TerraformingType.Shift:
			num4 = m_ShiftTerrainKernal;
			break;
		case TerraformingType.Level:
			num4 = m_LevelTerrainKernal;
			val2.y = (brush.m_Target.y - positionOffset.y) / heightScaleOffset.x;
			break;
		case TerraformingType.Slope:
		{
			num4 = m_SlopeTerrainKernal;
			float3 float6 = brush.m_Target - brush.m_Start;
			val2.y = (brush.m_Target.y - positionOffset.y) / heightScaleOffset.x;
			val2.z = (brush.m_Start.y - positionOffset.y) / heightScaleOffset.x;
			val2.w = float6.y / heightScaleOffset.x;
			float4 zero = float4.zero;
			zero.xy = math.normalize(float6.xz);
			zero.z = 0f - math.dot((brush.m_Start.xz - float2) / @float, zero.xy);
			zero.w = math.length(float6.xz) / num;
			val3 = zero;
			break;
		}
		case TerraformingType.Soften:
		{
			RenderTextureDescriptor desc = new RenderTextureDescriptor
			{
				autoGenerateMips = false,
				bindMS = false,
				depthBufferBits = 0,
				dimension = TextureDimension.Tex2D,
				enableRandomWrite = true,
				graphicsFormat = GraphicsFormat.R16_UNorm,
				memoryless = RenderTextureMemoryless.None,
				height = num3 + 8,
				width = num2 + 8,
				volumeDepth = 1,
				mipCount = 1,
				msaaSamples = 1,
				sRGB = false,
				useDynamicScale = false,
				useMipMap = false
			};
			m_CommandBuffer.GetTemporaryRT(ShaderID._AvgTerrainHeightsTemp, desc);
			m_CommandBuffer.GetTemporaryRT(ShaderID._BlurTempHorz, desc);
			num4 = m_SmoothTerrainKernal;
			val2.y = desc.width;
			val2.z = desc.height;
			val3.x = 4f;
			val3.y = 4f;
			m_CommandBuffer.SetComputeTextureParam(m_AdjustTerrainCS, m_BlurHorzKernal, ShaderID._Heightmap, target);
			m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._BrushData, val2);
			m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._Range, new Vector4(@int.x - 4, @int.y - 4, @int.z + 4, @int.w + 4));
			int threadGroupsX2 = (num2 + 15) / 8;
			int threadGroupsY2 = num3 + 8;
			m_CommandBuffer.DispatchCompute(m_AdjustTerrainCS, m_BlurHorzKernal, threadGroupsX2, threadGroupsY2, 1);
			int threadGroupsX3 = num2 + 8;
			int threadGroupsY3 = (num3 + 15) / 8;
			m_CommandBuffer.DispatchCompute(m_AdjustTerrainCS, m_BlurVertKernal, threadGroupsX3, threadGroupsY3, 1);
			break;
		}
		default:
			num4 = m_ShiftTerrainKernal;
			break;
		}
		int num5 = 2;
		float4 float7 = ((worldHeightmap != null && !m_ToolSystem.actionMode.IsEditor()) ? new float4(num5, num5, target.width - num5, target.height - num5) : new float4(-1f, -1f, target.width + 1, target.height + 1));
		float val4 = 10f / heightScaleOffset.x;
		m_CommandBuffer.SetComputeTextureParam(m_AdjustTerrainCS, num4, ShaderID._Heightmap, target);
		m_CommandBuffer.SetComputeTextureParam(m_AdjustTerrainCS, num4, ShaderID._BrushTexture, texture);
		m_CommandBuffer.SetComputeTextureParam(m_AdjustTerrainCS, num4, ShaderID._WorldTexture, (worldHeightmap != null) ? worldHeightmap : Texture2D.whiteTexture);
		m_CommandBuffer.SetComputeTextureParam(m_AdjustTerrainCS, num4, ShaderID._WaterTexture, m_WaterSystem.WaterTexture);
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._HeightScaleOffset, new float4(heightScaleOffset.x, heightScaleOffset.y, 0f, 0f));
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._Range, new Vector4(@int.x, @int.y, @int.z, @int.w));
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._BrushData, val2);
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._BrushData2, val3);
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._ClampArea, float7);
		m_CommandBuffer.SetComputeVectorParam(m_AdjustTerrainCS, ShaderID._WorldOffsetScale, m_WorldOffsetScale);
		m_CommandBuffer.SetComputeFloatParam(m_AdjustTerrainCS, ShaderID._EdgeMaxDifference, val4);
		m_CommandBuffer.DispatchCompute(m_AdjustTerrainCS, num4, threadGroupsX, threadGroupsY, 1);
		if (type == TerraformingType.Soften)
		{
			m_CommandBuffer.ReleaseTemporaryRT(ShaderID._AvgTerrainHeightsTemp);
			m_CommandBuffer.ReleaseTemporaryRT(ShaderID._BlurTempHorz);
		}
		Graphics.ExecuteCommandBuffer(m_CommandBuffer);
	}
```

- `public CalculateBuildingCullArea(Game.Objects.Transform transform, Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> geometryData, Unity.Mathematics.float4& area) : System.Boolean`  

```csharp
public bool CalculateBuildingCullArea(Game.Objects.Transform transform, Entity prefab, ComponentLookup<ObjectGeometryData> geometryData, out float4 area)
	{
		area = float4.zero;
		if (geometryData.TryGetComponent(prefab, out var componentData))
		{
			Bounds3 bounds = ObjectUtils.CalculateBounds(transform.m_Position, transform.m_Rotation, componentData);
			bounds = MathUtils.Expand(bounds, ObjectUtils.GetTerrainSmoothingWidth(componentData) - 8f);
			area.xy = bounds.min.xz;
			area.zw = bounds.max.xz;
			return true;
		}
		return false;
	}
```

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		CoreUtils.Destroy(m_Heightmap);
	}
```

- `private ClipViewport(Unity.Mathematics.float4 Viewport) : Unity.Mathematics.float4`  

```csharp
private float4 ClipViewport(float4 Viewport)
	{
		if (Viewport.x < 0f)
		{
			Viewport.z = math.max(Viewport.z + Viewport.x, 0f);
			Viewport.x = 0f;
		}
		else if (Viewport.x > 1f)
		{
			Viewport.x = 1f;
			Viewport.z = 0f;
		}
		if (Viewport.x + Viewport.z > 1f)
		{
			Viewport.z = math.max(1f - Viewport.x, 0f);
		}
		if (Viewport.y < 0f)
		{
			Viewport.w = math.max(Viewport.w + Viewport.y, 0f);
			Viewport.y = 0f;
		}
		else if (Viewport.y > 1f)
		{
			Viewport.y = 1f;
			Viewport.w = 0f;
		}
		if (Viewport.y + Viewport.w > 1f)
		{
			Viewport.w = math.max(1f - Viewport.y, 0f);
		}
		return Viewport;
	}
```

- `private CreateDefaultHeightmap(System.Int32 width, System.Int32 height) : UnityEngine.Texture2D`  

```csharp
private Texture2D CreateDefaultHeightmap(int width, int height)
	{
		Texture2D obj = new Texture2D(width, height, GraphicsFormat.R16_UNorm, TextureCreationFlags.DontInitializePixels | TextureCreationFlags.DontUploadUponCreate)
		{
			hideFlags = HideFlags.HideAndDontSave,
			name = "DefaultHeightmap",
			filterMode = FilterMode.Bilinear,
			wrapMode = TextureWrapMode.Clamp
		};
		SetDefaultHeights(obj);
		return obj;
	}
```

- `private CreateRoadMeshes() : System.Void`  

```csharp
private void CreateRoadMeshes()
	{
		m_LaneMesh = new Mesh
		{
			name = "Lane Mesh"
		};
		int num = 1;
		int num2 = 8;
		int num3 = (num + 1) * (num2 + 1);
		int num4 = num * num2 * 2 * 3;
		Vector3[] array = new Vector3[num3];
		Vector2[] array2 = new Vector2[num3];
		int[] array3 = new int[num4];
		for (int i = 0; i <= num2; i++)
		{
			for (int j = 0; j <= num; j++)
			{
				array[j + (num + 1) * i] = new Vector3((float)j / (float)num, 0f, (float)i / (float)num2);
				array2[j + (num + 1) * i] = new Vector2(array[j + (num + 1) * i].x, array[j + (num + 1) * i].z);
			}
		}
		int num5 = num + 1;
		int num6 = 0;
		for (int k = 0; k < num2; k++)
		{
			for (int l = 0; l < num; l++)
			{
				array3[num6++] = l + num5 * (k + 1);
				array3[num6++] = l + 1 + num5 * (k + 1);
				array3[num6++] = l + 1 + num5 * k;
				array3[num6++] = l + num5 * (k + 1);
				array3[num6++] = l + 1 + num5 * k;
				array3[num6++] = l + num5 * k;
			}
		}
		m_LaneMesh.vertices = array;
		m_LaneMesh.uv = array2;
		m_LaneMesh.subMeshCount = 1;
		m_LaneMesh.SetTriangles(array3, 0);
		m_LaneMesh.UploadMeshData(markNoLongerReadable: true);
		m_ClipMesh = new Mesh
		{
			name = "Clip Mesh"
		};
		int num7 = num3;
		num3 *= 2;
		num4 = num4 * 2 + num2 * 2 * 3 * 2 + num * 2 * 3 * 2;
		array = new Vector3[num3];
		array2 = new Vector2[num3];
		array3 = new int[num4];
		for (int m = 0; m <= num2; m++)
		{
			for (int n = 0; n <= num; n++)
			{
				array[n + (num + 1) * m] = new Vector3((float)n / (float)num, 1f, (float)m / (float)num2);
				array2[n + (num + 1) * m] = new Vector2(array[n + (num + 1) * m].x, array[n + (num + 1) * m].z);
				array[num7 + n + (num + 1) * m] = array[n + (num + 1) * m];
				array[num7 + n + (num + 1) * m].y = 0f;
				array2[num7 + n + (num + 1) * m] = array2[n + (num + 1) * m];
			}
		}
		num5 = num + 1;
		num6 = 0;
		for (int num8 = 0; num8 < num2; num8++)
		{
			for (int num9 = 0; num9 < num; num9++)
			{
				array3[num6++] = num9 + num5 * (num8 + 1);
				array3[num6++] = num9 + 1 + num5 * (num8 + 1);
				array3[num6++] = num9 + 1 + num5 * num8;
				array3[num6++] = num9 + num5 * (num8 + 1);
				array3[num6++] = num9 + 1 + num5 * num8;
				array3[num6++] = num9 + num5 * num8;
			}
		}
		for (int num10 = 0; num10 < num2; num10++)
		{
			for (int num11 = 0; num11 < num; num11++)
			{
				array3[num6++] = num7 + (num11 + 1 + num5 * (num10 + 1));
				array3[num6++] = num7 + (num11 + num5 * (num10 + 1));
				array3[num6++] = num7 + (num11 + 1 + num5 * num10);
				array3[num6++] = num7 + (num11 + 1 + num5 * num10);
				array3[num6++] = num7 + (num11 + num5 * (num10 + 1));
				array3[num6++] = num7 + (num11 + num5 * num10);
			}
		}
		int num12 = 0;
		for (int num13 = 0; num13 < num2; num13++)
		{
			array3[num6++] = num12 + num5 * (num13 + 1);
			array3[num6++] = num12 + num5 * num13;
			array3[num6++] = num7 + num12 + num5 * num13;
			array3[num6++] = num7 + num12 + num5 * num13;
			array3[num6++] = num7 + num12 + num5 * (num13 + 1);
			array3[num6++] = num12 + num5 * (num13 + 1);
		}
		num12 = num;
		for (int num14 = 0; num14 < num2; num14++)
		{
			array3[num6++] = num12 + num5 * num14;
			array3[num6++] = num12 + num5 * (num14 + 1);
			array3[num6++] = num7 + num12 + num5 * num14;
			array3[num6++] = num7 + num12 + num5 * (num14 + 1);
			array3[num6++] = num7 + num12 + num5 * num14;
			array3[num6++] = num12 + num5 * (num14 + 1);
		}
		for (int num15 = 0; num15 < num; num15++)
		{
			array3[num6++] = num15;
			array3[num6++] = num15 + num7;
			array3[num6++] = num15 + num7 + 1;
			array3[num6++] = num15 + num7 + 1;
			array3[num6++] = num15 + 1;
			array3[num6++] = num15;
		}
		for (int num16 = 1; num16 <= num; num16++)
		{
			array3[num6++] = num3 - num16;
			array3[num6++] = num3 - num16 - 1;
			array3[num6++] = num3 - num16 - num7 - 1;
			array3[num6++] = num3 - num16 - num7 - 1;
			array3[num6++] = num3 - num16 - num7;
			array3[num6++] = num3 - num16;
		}
		m_ClipMesh.vertices = array;
		m_ClipMesh.uv = array2;
		m_ClipMesh.subMeshCount = 1;
		m_ClipMesh.SetTriangles(array3, 0);
		m_ClipMesh.UploadMeshData(markNoLongerReadable: true);
	}
```

- `private CullCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, System.Int32 laneCount) : System.Void`  

```csharp
private void CullCascade(int cascadeIndex, float4 area, float4 viewport, int laneCount)
	{
		if (viewport.z == 0f || viewport.w == 0f)
		{
			UnityEngine.Debug.LogError("Invalid Viewport");
		}
		CascadeCullInfo cascadeCullInfo = m_CascadeCulling[cascadeIndex];
		cascadeCullInfo.m_BuildingHandle.Complete();
		cascadeCullInfo.m_BuildingRenderList = new NativeList<BuildingLotDraw>(Allocator.TempJob);
		float2 xy = area.xy;
		float2 @float = area.zw - area.xy;
		area = new float4(xy.x + @float.x * viewport.x, xy.y + @float.y * viewport.y, xy.x + @float.x * (viewport.x + viewport.z), xy.y + @float.y * (viewport.y + viewport.w));
		area += new float4(-10f, -10f, 10f, 10f);
		heightMapCullArea[cascadeIndex] = area;
		NativeQueue<BuildingLotDraw> queue = new NativeQueue<BuildingLotDraw>(Allocator.TempJob);
		CullBuildingsCascadeJob jobData = new CullBuildingsCascadeJob
		{
			m_LotsToCull = m_BuildingCullList,
			m_Area = area,
			Result = queue.AsParallelWriter()
		};
		DequeBuildingDrawsJob jobData2 = new DequeBuildingDrawsJob
		{
			m_Queue = queue,
			m_List = cascadeCullInfo.m_BuildingRenderList
		};
		JobHandle dependsOn = jobData.Schedule(m_BuildingCullList, 128, m_BuildingCull);
		cascadeCullInfo.m_BuildingHandle = IJobExtensions.Schedule(jobData2, dependsOn);
		queue.Dispose(cascadeCullInfo.m_BuildingHandle);
		cascadeCullInfo.m_LaneHandle.Complete();
		cascadeCullInfo.m_LaneRenderList = new NativeList<LaneDraw>(laneCount, Allocator.TempJob);
		CullRoadsCacscadeJob jobData3 = new CullRoadsCacscadeJob
		{
			m_RoadsToCull = m_LaneCullList,
			m_Area = area,
			m_Scale = 1f / heightScaleOffset.x,
			Result = cascadeCullInfo.m_LaneRenderList.AsParallelWriter()
		};
		cascadeCullInfo.m_LaneHandle = jobData3.Schedule(m_LaneCullList, 128, m_LaneCull);
		cascadeCullInfo.m_AreaHandle.Complete();
		cascadeCullInfo.m_TriangleRenderList = new NativeList<AreaTriangle>(Allocator.TempJob);
		cascadeCullInfo.m_EdgeRenderList = new NativeList<AreaEdge>(Allocator.TempJob);
		CullTrianglesJob jobData4 = new CullTrianglesJob
		{
			m_Triangles = m_TriangleCullList,
			m_Area = area,
			Result = cascadeCullInfo.m_TriangleRenderList
		};
		CullEdgesJob jobData5 = new CullEdgesJob
		{
			m_Edges = m_EdgeCullList,
			m_Area = area,
			Result = cascadeCullInfo.m_EdgeRenderList
		};
		JobHandle job = IJobExtensions.Schedule(jobData4, m_AreaCull);
		JobHandle job2 = IJobExtensions.Schedule(jobData5, m_AreaCull);
		cascadeCullInfo.m_AreaHandle = JobHandle.CombineDependencies(job, job2);
		m_CullFinished = JobHandle.CombineDependencies(m_CullFinished, JobHandle.CombineDependencies(cascadeCullInfo.m_BuildingHandle, cascadeCullInfo.m_LaneHandle, cascadeCullInfo.m_AreaHandle));
	}
```

- `public CullClipMapForView(Game.Rendering.Viewer viewer) : System.Void`  

```csharp
public void CullClipMapForView(Viewer viewer)
	{
	}
```

- `private CullForCascades(Unity.Mathematics.float4 area, System.Boolean heightMapRenderRequired, System.Boolean roadsChanged, System.Boolean terrainAreasChanged, System.Boolean clipAreasChanged, System.Int32& laneCount) : System.Void`  

```csharp
private void CullForCascades(float4 area, bool heightMapRenderRequired, bool roadsChanged, bool terrainAreasChanged, bool clipAreasChanged, out int laneCount)
	{
		m_CullFinished.Complete();
		if (roadsChanged)
		{
			m_ClipMapCull.Complete();
			m_LaneCullList.Clear();
			m_ClipMapList.Clear();
			laneCount = m_RoadsGroup.CalculateEntityCountWithoutFiltering() * 6;
			if (laneCount > m_LaneCullList.Capacity)
			{
				m_LaneCullList.Capacity = laneCount + math.max(laneCount / 4, 250);
				m_ClipMapList.Capacity = m_LaneCullList.Capacity;
			}
		}
		else
		{
			laneCount = m_LaneCullList.Length;
		}
		if (heightMapRenderRequired)
		{
			NativeQueue<BuildingUtils.LotInfo> queue = new NativeQueue<BuildingUtils.LotInfo>(Allocator.TempJob);
			CullBuildingLotsJob jobData = new CullBuildingLotsJob
			{
				m_LotHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElevationHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StackHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InstalledUpgradeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAssetStampData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AssetStampData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OverrideTerraform = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AdditionalLots = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AdditionalBuildingTerraformElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Area = area,
				Result = queue.AsParallelWriter()
			};
			DequeBuildingLotsJob jobData2 = new DequeBuildingLotsJob
			{
				m_Queue = queue,
				m_List = m_BuildingCullList
			};
			JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingGroup, base.Dependency);
			m_BuildingCull = IJobExtensions.Schedule(jobData2, dependsOn);
			m_CullFinished = m_BuildingCull;
			queue.Dispose(m_BuildingCull);
		}
		if (roadsChanged)
		{
			CullRoadsJob jobData3 = new CullRoadsJob
			{
				m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TerrainCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TerrainComposition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Area = m_CascadeRanges[baseLod],
				Result = m_LaneCullList.AsParallelWriter()
			};
			m_LaneCull = JobChunkExtensions.ScheduleParallel(jobData3, m_RoadsGroup, base.Dependency);
			m_CullFinished = JobHandle.CombineDependencies(m_CullFinished, m_LaneCull);
			GenerateClipDataJob jobData4 = new GenerateClipDataJob
			{
				m_RoadsToCull = m_LaneCullList,
				Result = m_ClipMapList.AsParallelWriter()
			};
			m_CurrentClipMap = null;
			m_ClipMapCull = jobData4.Schedule(m_LaneCullList, 128, m_LaneCull);
			m_CullFinished = JobHandle.CombineDependencies(m_CullFinished, m_ClipMapCull);
		}
		if (terrainAreasChanged)
		{
			NativeQueue<AreaTriangle> queue2 = new NativeQueue<AreaTriangle>(Allocator.TempJob);
			NativeQueue<AreaEdge> queue3 = new NativeQueue<AreaEdge>(Allocator.TempJob);
			CullAreasJob jobData5 = new CullAreasJob
			{
				m_ClipType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Clip_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_GeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StorageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Storage_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabTerrainAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TerrainAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabStorageAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Area = m_CascadeRanges[baseLod],
				m_Triangles = queue2.AsParallelWriter(),
				m_Edges = queue3.AsParallelWriter()
			};
			DequeTrianglesJob jobData6 = new DequeTrianglesJob
			{
				m_Queue = queue2,
				m_List = m_TriangleCullList
			};
			DequeEdgesJob jobData7 = new DequeEdgesJob
			{
				m_Queue = queue3,
				m_List = m_EdgeCullList
			};
			JobHandle dependsOn2 = JobChunkExtensions.ScheduleParallel(jobData5, m_AreasQuery, base.Dependency);
			JobHandle job = IJobExtensions.Schedule(jobData6, dependsOn2);
			JobHandle job2 = IJobExtensions.Schedule(jobData7, dependsOn2);
			m_AreaCull = JobHandle.CombineDependencies(job, job2);
			m_CullFinished = JobHandle.CombineDependencies(m_CullFinished, m_AreaCull);
			queue2.Dispose(m_AreaCull);
			queue3.Dispose(m_AreaCull);
		}
		if (clipAreasChanged)
		{
			if (!m_HasAreaClipMeshData)
			{
				m_HasAreaClipMeshData = true;
				m_AreaClipMeshData = Mesh.AllocateWritableMeshData(1);
			}
			JobHandle outJobHandle;
			GenerateAreaClipMeshJob jobData8 = new GenerateAreaClipMeshJob
			{
				m_Chunks = m_AreasQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_ClipType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Clip_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_MeshData = m_AreaClipMeshData
			};
			m_AreaClipMeshDataDeps = IJobExtensions.Schedule(jobData8, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			jobData8.m_Chunks.Dispose(m_AreaClipMeshDataDeps);
			m_CullFinished = JobHandle.CombineDependencies(m_CullFinished, m_AreaClipMeshDataDeps);
		}
		base.Dependency = m_CullFinished;
	}
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
private void DestroyWorldMap()
	{
		if (worldHeightmap != null)
		{
			if (worldHeightmap is RenderTexture renderTexture)
			{
				renderTexture.Release();
			}
			UnityEngine.Object.Destroy(worldHeightmap);
			worldHeightmap = null;
		}
		if (m_WorldMapEditable != null)
		{
			m_WorldMapEditable.Release();
			UnityEngine.Object.Destroy(m_WorldMapEditable);
			m_WorldMapEditable = null;
		}
		if (worldMapAsset != null)
		{
			worldMapAsset.Unload();
			worldMapAsset = null;
		}
	}
```

- `private DrawHeightAdjustments(UnityEngine.Rendering.CommandBuffer& cmdBuffer, System.Int32 cascade, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.RenderTargetBinding binding, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+BuildingLotDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+LaneDraw, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lanes, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaTriangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, Unity.Collections.NativeArray`1[[Game.Simulation.TerrainSystem+AreaEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, UnityEngine.Material& lotMaterial, UnityEngine.Material& laneMaterial, UnityEngine.Material& areaMaterial) : System.Void`  

```csharp
private void DrawHeightAdjustments(ref CommandBuffer cmdBuffer, int cascade, float4 area, float4 viewport, RenderTargetBinding binding, ref NativeArray<BuildingLotDraw> lots, ref NativeArray<LaneDraw> lanes, ref NativeArray<AreaTriangle> triangles, ref NativeArray<AreaEdge> edges, ref Material lotMaterial, ref Material laneMaterial, ref Material areaMaterial)
	{
		float4 @float = new float4(-area.xy, 1f / (area.zw - area.xy));
		Rect scissor = new Rect(viewport.x * (float)m_HeightmapCascade.width, viewport.y * (float)m_HeightmapCascade.height, viewport.z * (float)m_HeightmapCascade.width, viewport.w * (float)m_HeightmapCascade.height);
		if (lots.Length > 0)
		{
			ComputeBuffer computeBuffer = m_BuildingInstanceData.Request(lots.Length);
			computeBuffer.SetData(lots);
			computeBuffer.name = $"BuildingLot Buffer Cascade{cascade}";
			lotMaterial.SetVector(ShaderID._TerrainScaleOffsetID, new Vector4(heightScaleOffset.x, heightScaleOffset.y, 0f, 0f));
			lotMaterial.SetVector(ShaderID._MapOffsetScaleID, m_MapOffsetScale);
			lotMaterial.SetVector(ShaderID._CascadeOffsetScale, @float);
			lotMaterial.SetTexture(ShaderID._HeightmapID, heightmap);
			lotMaterial.SetBuffer(ShaderID._BuildingLotID, computeBuffer);
		}
		if (lanes.Length > 0)
		{
			ComputeBuffer computeBuffer2 = m_LaneInstanceData.Request(lanes.Length);
			computeBuffer2.SetData(lanes);
			computeBuffer2.name = $"Lane Buffer Cascade{cascade}";
			laneMaterial.SetVector(ShaderID._TerrainScaleOffsetID, new Vector4(heightScaleOffset.x, heightScaleOffset.y, 0f, 0f));
			laneMaterial.SetVector(ShaderID._MapOffsetScaleID, m_MapOffsetScale);
			laneMaterial.SetVector(ShaderID._CascadeOffsetScale, @float);
			laneMaterial.SetTexture(ShaderID._HeightmapID, heightmap);
			laneMaterial.SetBuffer(ShaderID._LanesID, computeBuffer2);
		}
		if (triangles.Length > 0 || edges.Length > 0)
		{
			ComputeBuffer computeBuffer3 = m_TriangleInstanceData.Request(triangles.Length);
			computeBuffer3.SetData(triangles);
			computeBuffer3.name = $"Triangle Buffer Cascade{cascade}";
			ComputeBuffer computeBuffer4 = m_EdgeInstanceData.Request(edges.Length);
			computeBuffer4.SetData(edges);
			computeBuffer4.name = $"Edge Buffer Cascade{cascade}";
			areaMaterial.SetVector(ShaderID._TerrainScaleOffsetID, new Vector4(heightScaleOffset.x, heightScaleOffset.y, 0f, 0f));
			areaMaterial.SetVector(ShaderID._MapOffsetScaleID, m_MapOffsetScale);
			areaMaterial.SetVector(ShaderID._CascadeOffsetScale, @float);
			areaMaterial.SetTexture(ShaderID._HeightmapID, heightmap);
			areaMaterial.SetBuffer(ShaderID._TrianglesID, computeBuffer3);
			areaMaterial.SetBuffer(ShaderID._EdgesID, computeBuffer4);
		}
		if (lots.Length > 0)
		{
			cmdBuffer.DrawProcedural(Matrix4x4.identity, lotMaterial, 1, MeshTopology.Triangles, 6, lots.Length);
		}
		if (lanes.Length > 0)
		{
			cmdBuffer.DrawMeshInstancedProcedural(m_LaneMesh, 0, laneMaterial, 1, lanes.Length);
		}
		int num = Shader.PropertyToID("_CascadeMinHeights");
		cmdBuffer.GetTemporaryRT(num, m_HeightmapCascade.width, m_HeightmapCascade.height, 0, FilterMode.Point, m_HeightmapCascade.graphicsFormat);
		int num2 = math.max(0, Mathf.FloorToInt(scissor.xMin));
		int num3 = math.max(0, Mathf.FloorToInt(scissor.yMin));
		int srcWidth = math.min(m_HeightmapCascade.width, Mathf.CeilToInt(scissor.xMax)) - num2;
		int srcHeight = math.min(m_HeightmapCascade.height, Mathf.CeilToInt(scissor.yMax)) - num3;
		cmdBuffer.CopyTexture(m_HeightmapCascade, cascade, 0, num2, num3, srcWidth, srcHeight, num, 0, 0, num2, num3);
		cmdBuffer.SetRenderTarget(binding, 0, CubemapFace.Unknown, cascade);
		cmdBuffer.EnableScissorRect(scissor);
		if (triangles.Length > 0)
		{
			cmdBuffer.DrawProcedural(Matrix4x4.identity, areaMaterial, 0, MeshTopology.Triangles, 3, triangles.Length);
		}
		if (edges.Length > 0)
		{
			cmdBuffer.DrawProcedural(Matrix4x4.identity, areaMaterial, 1, MeshTopology.Triangles, 6, edges.Length);
		}
		if (lots.Length > 0)
		{
			cmdBuffer.DrawProcedural(Matrix4x4.identity, lotMaterial, 0, MeshTopology.Triangles, 6, lots.Length);
		}
		if (lanes.Length > 0)
		{
			cmdBuffer.DrawMeshInstancedProcedural(m_LaneMesh, 0, laneMaterial, 0, lanes.Length);
		}
		cmdBuffer.ReleaseTemporaryRT(num);
		if (lots.Length > 0)
		{
			cmdBuffer.DrawProcedural(Matrix4x4.identity, lotMaterial, 2, MeshTopology.Triangles, 6, lots.Length);
		}
		if (lanes.Length > 0)
		{
			cmdBuffer.DrawMeshInstancedProcedural(m_LaneMesh, 0, laneMaterial, 2, lanes.Length);
		}
	}
```

- `private EnsureCPUHeights(System.Int32 length) : System.Void`  

```csharp
private void EnsureCPUHeights(int length)
	{
		if (m_CPUHeights.IsCreated)
		{
			if (m_CPUHeights.Length != length)
			{
				m_CPUHeights.Dispose();
				m_CPUHeights = new NativeArray<ushort>(length, Allocator.Persistent);
			}
		}
		else
		{
			m_CPUHeights = new NativeArray<ushort>(length, Allocator.Persistent);
		}
	}
```

- `private FinalizeTerrainData(UnityEngine.Texture2D map, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax) : System.Void`  

```csharp
private void FinalizeTerrainData(Texture2D map, Texture2D worldMap, float2 heightScaleOffset, float2 inMapCorner, float2 inMapSize, float2 inWorldCorner, float2 inWorldSize, float2 inWorldHeightMinMax)
	{
		this.heightScaleOffset = heightScaleOffset;
		if (math.all(inWorldSize == inMapSize) || worldHeightmap == null)
		{
			baseLod = 0;
			playableArea = inMapSize;
			worldSize = inMapSize;
			playableOffset = inMapCorner;
			worldOffset = inMapCorner;
		}
		else
		{
			baseLod = 1;
			playableArea = inMapSize;
			worldSize = inWorldSize;
			playableOffset = inMapCorner;
			worldOffset = inWorldCorner;
		}
		m_NewMap = true;
		m_NewMapThisFrame = true;
		m_CascadeReset = true;
		worldHeightMinMax = inWorldHeightMinMax;
		m_WorldOffsetScale = new float4((playableOffset - worldOffset) / worldSize, playableArea / worldSize);
		float3 @float = new float3(playableArea.x, heightScaleOffset.x, playableArea.y);
		float3 xyz = 1f / @float;
		float3 xyz2 = -positionOffset;
		m_MapOffsetScale = new Vector4(0f - positionOffset.x, 0f - positionOffset.z, 1f / @float.x, 1f / @float.z);
		if (m_HeightmapCascade == null || m_HeightmapCascade.width != heightmap.width || m_HeightmapCascade.height != heightmap.height)
		{
			if (m_HeightmapCascade != null)
			{
				m_HeightmapCascade.Release();
				UnityEngine.Object.Destroy(m_HeightmapCascade);
				m_HeightmapCascade = null;
			}
			m_HeightmapCascade = new RenderTexture(heightmap.width, heightmap.height, 0, GraphicsFormat.R16_UNorm)
			{
				hideFlags = HideFlags.HideAndDontSave,
				enableRandomWrite = false,
				name = "TerrainHeightsCascade",
				filterMode = FilterMode.Bilinear,
				wrapMode = TextureWrapMode.Clamp,
				dimension = TextureDimension.Tex2DArray,
				volumeDepth = 4
			};
			m_HeightmapCascade.Create();
		}
		if (m_HeightmapDepth == null || m_HeightmapDepth.width != heightmap.width || m_HeightmapDepth.height != heightmap.height)
		{
			if (m_HeightmapDepth != null)
			{
				m_HeightmapDepth.Release();
				UnityEngine.Object.Destroy(m_HeightmapDepth);
				m_HeightmapDepth = null;
			}
			m_HeightmapDepth = new RenderTexture(heightmap.width, heightmap.height, 16, RenderTextureFormat.Depth, RenderTextureReadWrite.Linear)
			{
				name = "HeightmapDepth"
			};
			m_HeightmapDepth.Create();
		}
		if (map != null)
		{
			Graphics.CopyTexture(map, 0, 0, m_HeightmapCascade, baseLod, 0);
		}
		m_CascadeRanges = new float4[4];
		m_ShaderCascadeRanges = new Vector4[4];
		for (int i = 0; i < 4; i++)
		{
			m_CascadeRanges[i] = new float4(0f, 0f, 0f, 0f);
		}
		m_CascadeRanges[baseLod] = new float4(playableOffset, playableOffset + playableArea);
		if (baseLod > 0)
		{
			m_CascadeRanges[0] = new float4(worldOffset, worldOffset + worldSize);
			if (worldMap != null)
			{
				Graphics.CopyTexture(worldMap, 0, 0, m_HeightmapCascade, 0, 0);
			}
		}
		m_UpdateArea = new float4(m_CascadeRanges[baseLod]);
		Shader.SetGlobalTexture("colossal_TerrainTexture", m_Heightmap);
		Shader.SetGlobalVector("colossal_TerrainScale", new float4(xyz, 0f));
		Shader.SetGlobalVector("colossal_TerrainOffset", new float4(xyz2, 0f));
		Shader.SetGlobalVector("colossal_TerrainCascadeLimit", new float4(0.5f / (float)m_HeightmapCascade.width, 0.5f / (float)m_HeightmapCascade.height, 0f, 0f));
		Shader.SetGlobalTexture("colossal_TerrainTextureArray", m_HeightmapCascade);
		Shader.SetGlobalInt("colossal_TerrainTextureArrayBaseLod", baseLod);
		if (map != null)
		{
			m_CPUHeightReaders.Complete();
			m_CPUHeightReaders = default(JobHandle);
			WriteCPUHeights(map.GetRawTextureData<ushort>());
		}
		m_TerrainMinMax.Init((worldHeightmap != null) ? 1024 : 512, (worldHeightmap != null) ? worldHeightmap.width : m_Heightmap.width);
		m_TerrainMinMax.UpdateMap(this, m_Heightmap, worldHeightmap);
	}
```

- `public GetBuildingUpgradeWriter(System.Int32 ExpectedAmount) : Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Unity.Entities.Entity>`  

```csharp
public NativeParallelHashMap<Entity, Entity>.ParallelWriter GetBuildingUpgradeWriter(int ExpectedAmount)
	{
		m_BuildingUpgradeDependencies.Complete();
		if (ExpectedAmount > m_BuildingUpgrade.Capacity)
		{
			m_BuildingUpgrade.Capacity = ExpectedAmount;
		}
		return m_BuildingUpgrade.AsParallelWriter();
	}
```

- `public GetCascadeInfo(System.Int32& LODCount, System.Int32& baseLOD, Unity.Mathematics.float4x4& areas, Unity.Mathematics.float4& ranges, Unity.Mathematics.float4& size) : System.Void`  

```csharp
public void GetCascadeInfo(out int LODCount, out int baseLOD, out float4x4 areas, out float4 ranges, out float4 size)
	{
		LODCount = 4;
		baseLOD = baseLod;
		if (m_CascadeRanges != null)
		{
			areas = new float4x4(m_CascadeRanges[0].x, m_CascadeRanges[0].y, m_CascadeRanges[0].z, m_CascadeRanges[0].w, m_CascadeRanges[1].x, m_CascadeRanges[1].y, m_CascadeRanges[1].z, m_CascadeRanges[1].w, m_CascadeRanges[2].x, m_CascadeRanges[2].y, m_CascadeRanges[2].z, m_CascadeRanges[2].w, m_CascadeRanges[3].x, m_CascadeRanges[3].y, m_CascadeRanges[3].z, m_CascadeRanges[3].w);
			ranges = new float4(math.min(m_CascadeRanges[0].z - m_CascadeRanges[0].x, m_CascadeRanges[0].w - m_CascadeRanges[0].y) * 0.75f, math.min(m_CascadeRanges[1].z - m_CascadeRanges[1].x, m_CascadeRanges[1].w - m_CascadeRanges[1].y) * 0.75f, math.min(m_CascadeRanges[2].z - m_CascadeRanges[2].x, m_CascadeRanges[2].w - m_CascadeRanges[2].y) * 0.75f, math.min(m_CascadeRanges[3].z - m_CascadeRanges[3].x, m_CascadeRanges[3].w - m_CascadeRanges[3].y) * 0.75f);
			size = new float4(math.max(m_CascadeRanges[0].z - m_CascadeRanges[0].x, m_CascadeRanges[0].w - m_CascadeRanges[0].y), math.max(m_CascadeRanges[1].z - m_CascadeRanges[1].x, m_CascadeRanges[1].w - m_CascadeRanges[1].y), math.max(m_CascadeRanges[2].z - m_CascadeRanges[2].x, m_CascadeRanges[2].w - m_CascadeRanges[2].y), math.max(m_CascadeRanges[3].z - m_CascadeRanges[3].x, m_CascadeRanges[3].w - m_CascadeRanges[3].y));
		}
		else
		{
			areas = default(float4x4);
			ranges = default(float4);
			size = default(float4);
		}
	}
```

- `public GetCascadeTexture() : UnityEngine.Texture`  

```csharp
public Texture GetCascadeTexture()
	{
		return m_HeightmapCascade;
	}
```

- `public GetHeightData(System.Boolean waitForPending = False) : Game.Simulation.TerrainHeightData`  

```csharp
public TerrainHeightData GetHeightData(bool waitForPending = false)
	{
		if (waitForPending && m_HeightMapChanged)
		{
			m_AsyncGPUReadback.WaitForCompletion();
			m_CPUHeightReaders.Complete();
			m_CPUHeightReaders = default(JobHandle);
			UpdateGPUReadback();
		}
		int3 resolution = ((m_CPUHeights.IsCreated && !(m_HeightmapCascade == null) && m_CPUHeights.Length == m_HeightmapCascade.width * m_HeightmapCascade.height) ? new int3(m_HeightmapCascade.width, 65536, m_HeightmapCascade.height) : new int3(2, 2, 2));
		float3 @float = new float3(14336f, math.max(1f, heightScaleOffset.x), 14336f);
		float3 scale = new float3(resolution.x, resolution.y - 1, resolution.z) / @float;
		float3 offset = -positionOffset;
		offset.xz -= 0.5f / scale.xz;
		return new TerrainHeightData(m_CPUHeights, resolution, scale, offset);
	}
```

- `public GetLastMinMaxUpdate(Unity.Mathematics.float3& min, Unity.Mathematics.float3& max) : System.Void`  

```csharp
public void GetLastMinMaxUpdate(out float3 min, out float3 max)
	{
		int4 updateArea = m_TerrainMinMax.UpdateArea;
		float2 minMax = m_TerrainMinMax.GetMinMax(updateArea);
		float4 @float = new float4((float)updateArea.x / (float)m_TerrainMinMax.size, (float)updateArea.y / (float)m_TerrainMinMax.size, (float)(updateArea.x + updateArea.z) / (float)m_TerrainMinMax.size, (float)(updateArea.y + updateArea.w) / (float)m_TerrainMinMax.size);
		@float *= worldSize.xyxy;
		@float += worldOffset.xyxy;
		min = new float3(@float.x, minMax.x, @float.y);
		max = new float3(@float.z, minMax.y, @float.w);
	}
```

- `public GetRoads() : Unity.Collections.NativeList<Game.Simulation.TerrainSystem+LaneSection>`  

```csharp
public NativeList<LaneSection> GetRoads()
	{
		m_LaneCull.Complete();
		return m_LaneCullList;
	}
```

- `private GetTerrainAdjustmentSpeed(Game.Prefabs.TerraformingType type) : System.Single`  

```csharp
private float GetTerrainAdjustmentSpeed(TerraformingType type)
	{
		return type switch
		{
			TerraformingType.Soften => 1000f, 
			TerraformingType.Shift => 2000f, 
			_ => 4000f, 
		};
	}
```

- `public GetTerrainBounds() : UnityEngine.Bounds`  

```csharp
public Bounds GetTerrainBounds()
	{
		float3 @float = new float3(0f, (0f - heightScaleOffset.y) * 0.5f, 0f);
		return new Bounds(size: new float3(14336f, heightScaleOffset.x, 14336f), center: @float);
	}
```

- `public GetTerrainBrushUpdate(Unity.Mathematics.float4& viewport) : System.Boolean`  

```csharp
public bool GetTerrainBrushUpdate(out float4 viewport)
	{
		viewport = m_TerrainChangeArea;
		if (m_TerrainChange)
		{
			m_TerrainChange = false;
			viewport = new float4(m_TerrainChangeArea.x - m_CascadeRanges[baseLod].x, m_TerrainChangeArea.y - m_CascadeRanges[baseLod].y, m_TerrainChangeArea.z - m_CascadeRanges[baseLod].x, m_TerrainChangeArea.w - m_CascadeRanges[baseLod].y);
			viewport /= new float4(m_CascadeRanges[baseLod].z - m_CascadeRanges[baseLod].x, m_CascadeRanges[baseLod].w - m_CascadeRanges[baseLod].y, m_CascadeRanges[baseLod].z - m_CascadeRanges[baseLod].x, m_CascadeRanges[baseLod].w - m_CascadeRanges[baseLod].y);
			viewport.zw -= viewport.xy;
			viewport = ClipViewport(viewport);
			m_TerrainChangeArea = viewport;
			return true;
		}
		return false;
	}
```

- `public HandleNewMap() : System.Void`  

```csharp
public void HandleNewMap()
	{
		m_NewMap = false;
	}
```

- `private InitializeTerrainData(UnityEngine.Texture2D inMap, UnityEngine.Texture2D worldMap, Unity.Mathematics.float2 heightScaleOffset, Unity.Mathematics.float2 inMapCorner, Unity.Mathematics.float2 inMapSize, Unity.Mathematics.float2 inWorldCorner, Unity.Mathematics.float2 inWorldSize, Unity.Mathematics.float2 inWorldHeightMinMax) : System.Void`  

```csharp
private void InitializeTerrainData(Texture2D inMap, Texture2D worldMap, float2 heightScaleOffset, float2 inMapCorner, float2 inMapSize, float2 inWorldCorner, float2 inWorldSize, float2 inWorldHeightMinMax)
	{
		Texture2D texture2D = ((inMap != null) ? inMap : CreateDefaultHeightmap((worldMap != null) ? worldMap.width : kDefaultHeightmapWidth, (worldMap != null) ? worldMap.height : kDefaultHeightmapHeight));
		SetHeightmap(texture2D);
		SetWorldHeightmap(worldMap, m_ToolSystem.actionMode.IsEditor());
		FinalizeTerrainData(texture2D, worldMap, heightScaleOffset, inMapCorner, inMapSize, inWorldCorner, inWorldSize, inWorldHeightMinMax);
		if (texture2D != inMap)
		{
			UnityEngine.Object.Destroy(texture2D);
		}
	}
```

- `public static IsValidHeightmapFormat(UnityEngine.Texture2D tex) : System.Boolean`  

```csharp
public static bool IsValidHeightmapFormat(Texture2D tex)
	{
		if (tex.width == kDefaultHeightmapWidth && tex.height == kDefaultHeightmapHeight)
		{
			if (tex.graphicsFormat != GraphicsFormat.R16_UNorm)
			{
				return tex.graphicsFormat == GraphicsFormat.R16G16B16A16_UNorm;
			}
			return true;
		}
		return false;
	}
```

- `private LoadTerrain() : System.Void`  

```csharp
private void LoadTerrain()
	{
		InitializeTerrainData(null, null, kDefaultHeightScaleOffset, kDefaultMapOffset, kDefaultMapSize, kDefaultWorldOffset, kDefaultWorldSize, float2.zero);
	}
```

- `public OnBuildingMoved(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void OnBuildingMoved(Entity entity)
	{
		ComponentLookup<Game.Objects.Transform> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<PrefabRef> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ObjectGeometryData> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef);
		CompleteDependency();
		float4 area = float4.zero;
		if (!componentLookup2.HasComponent(entity) || !componentLookup.HasComponent(entity))
		{
			return;
		}
		PrefabRef prefabRef = componentLookup2[entity];
		Game.Objects.Transform transform = componentLookup[entity];
		if (CalculateBuildingCullArea(transform, prefabRef.m_Prefab, componentLookup3, out area))
		{
			m_GroundHeightSystem.GetUpdateBuffer().Add(new Bounds2(area.xy, area.zw));
			if (math.lengthsq(m_UpdateArea) > 0f)
			{
				m_UpdateArea.xy = math.min(m_UpdateArea.xy, area.xy);
				m_UpdateArea.zw = math.max(m_UpdateArea.zw, area.zw);
			}
			else
			{
				m_UpdateArea = area;
			}
			m_UpdateArea += new float4(-10f, -10f, 10f, 10f);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LastCullArea = float4.zero;
		freezeCascadeUpdates = false;
		m_CPUHeights = new NativeArray<ushort>(4, Allocator.Persistent);
		m_AdjustTerrainCS = Resources.Load<ComputeShader>("AdjustTerrain");
		m_ShiftTerrainKernal = m_AdjustTerrainCS.FindKernel("ShiftTerrain");
		m_BlurHorzKernal = m_AdjustTerrainCS.FindKernel("HorzBlur");
		m_BlurVertKernal = m_AdjustTerrainCS.FindKernel("VertBlur");
		m_SmoothTerrainKernal = m_AdjustTerrainCS.FindKernel("SmoothTerrain");
		m_LevelTerrainKernal = m_AdjustTerrainCS.FindKernel("LevelTerrain");
		m_SlopeTerrainKernal = m_AdjustTerrainCS.FindKernel("SlopeTerrain");
		m_BuildingUpgrade = new NativeParallelHashMap<Entity, Entity>(1024, Allocator.Persistent);
		m_CommandBuffer = new CommandBuffer();
		m_CommandBuffer.name = "TerrainAdjust";
		m_CascadeCB = new CommandBuffer();
		m_CascadeCB.name = "Terrain Cascade";
		Shader shader = Resources.Load<Shader>("BuildingLot");
		m_MasterBuildingLotMaterial = new Material(shader);
		Shader shader2 = Resources.Load<Shader>("Lane");
		m_MasterLaneMaterial = new Material(shader2);
		Shader shader3 = Resources.Load<Shader>("Area");
		m_MasterAreaMaterial = new Material(shader3);
		m_TerrainBlit = CoreUtils.CreateEngineMaterial(Resources.Load<Shader>("TerrainCascadeBlit"));
		m_ClipMaterial = CoreUtils.CreateEngineMaterial(Resources.Load<Shader>("RoadClip"));
		m_TerrainMinMax = new TerrainMinMaxMap();
		m_MapOffsetScale = new Vector4(0f, 0f, 1f, 1f);
		m_UpdateArea = float4.zero;
		m_TerrainChangeArea = float4.zero;
		m_TerrainChange = false;
		m_BuildingCullList = new NativeList<BuildingUtils.LotInfo>(1000, Allocator.Persistent);
		m_LaneCullList = new NativeList<LaneSection>(1000, Allocator.Persistent);
		m_TriangleCullList = new NativeList<AreaTriangle>(100, Allocator.Persistent);
		m_EdgeCullList = new NativeList<AreaEdge>(100, Allocator.Persistent);
		m_ClipMapList = new NativeList<ClipMapDraw>(1000, Allocator.Persistent);
		m_CascadeCulling = new List<CascadeCullInfo>(4);
		for (int i = 0; i < 4; i++)
		{
			m_CascadeCulling.Add(new CascadeCullInfo(m_MasterBuildingLotMaterial, m_MasterLaneMaterial, m_MasterAreaMaterial));
		}
		m_BuildingInstanceData = new ManagedStructuredBuffers<BuildingLotDraw>(10000);
		m_LaneInstanceData = new ManagedStructuredBuffers<LaneDraw>(10000);
		m_TriangleInstanceData = new ManagedStructuredBuffers<AreaTriangle>(1000);
		m_EdgeInstanceData = new ManagedStructuredBuffers<AreaEdge>(1000);
		m_LastPreviewWrite = int4.zero;
		m_LastWorldPreviewWrite = int4.zero;
		m_LastWorldWrite = int4.zero;
		m_LastWrite = int4.zero;
		m_LastRequest = int4.zero;
		m_FailCount = 0;
		baseLod = 0;
		m_NewMap = true;
		m_NewMapThisFrame = true;
		m_CascadeReset = true;
		m_RoadUpdate = false;
		m_AreaUpdate = false;
		m_ClipMapBuffer = new ManagedStructuredBuffers<ClipMapDraw>(10000);
		m_CurrentClipMap = null;
		heightMapRenderRequired = false;
		heightMapSliceUpdated = new bool[4];
		heightMapSliceUpdatedLast = new bool[4];
		heightMapViewport = new float4[4];
		heightMapViewportUpdated = new float4[4];
		heightMapCullArea = new float4[4];
		m_BrushQuery = GetEntityQuery(ComponentType.ReadOnly<Brush>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_BuildingsChanged = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.Lot>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Pillar>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.Lot>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Pillar>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.Lot>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Pillar>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_BuildingGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.Object>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.Lot>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Pillar>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_RoadsChanged = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<EdgeGeometry>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<NodeGeometry>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_RoadsGroup = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<EdgeGeometry>(),
				ComponentType.ReadOnly<NodeGeometry>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_AreasChanged = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Clip>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Areas.Terrain>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AreasQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Clip>(),
				ComponentType.ReadOnly<Game.Areas.Terrain>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_EditorLotQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.Lot>(),
				ComponentType.ReadOnly<Game.Objects.Transform>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Error>(),
				ComponentType.ReadOnly<Warning>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Game.Objects.Transform>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Error>(),
				ComponentType.ReadOnly<Warning>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hidden>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_GroundHeightSystem = base.World.GetOrCreateSystemManaged<GroundHeightSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		CreateRoadMeshes();
		m_Heightmap = null;
		m_HeightmapCascade = null;
		m_HeightmapDepth = null;
		m_WorldMapEditable = null;
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
		CoreUtils.Destroy(m_TerrainBlit);
		CoreUtils.Destroy(m_ClipMaterial);
		if (m_CPUHeights.IsCreated)
		{
			m_CPUHeights.Dispose();
		}
		CoreUtils.Destroy(m_Heightmap);
		CoreUtils.Destroy(m_HeightmapCascade);
		CoreUtils.Destroy(m_WorldMapEditable);
		worldMapAsset?.Unload();
		CoreUtils.Destroy(m_HeightmapDepth);
		if (m_BuildingCullList.IsCreated)
		{
			m_CullFinished.Complete();
			m_BuildingCullList.Dispose();
		}
		if (m_LaneCullList.IsCreated)
		{
			m_CullFinished.Complete();
			m_LaneCullList.Dispose();
		}
		if (m_TriangleCullList.IsCreated)
		{
			m_CullFinished.Complete();
			m_TriangleCullList.Dispose();
		}
		if (m_EdgeCullList.IsCreated)
		{
			m_CullFinished.Complete();
			m_EdgeCullList.Dispose();
		}
		if (m_ClipMapList.IsCreated)
		{
			m_ClipMapCull.Complete();
			m_ClipMapList.Dispose();
		}
		if (m_BuildingInstanceData != null)
		{
			m_BuildingInstanceData.Dispose();
			m_BuildingInstanceData = null;
		}
		if (m_LaneInstanceData != null)
		{
			m_LaneInstanceData.Dispose();
			m_LaneInstanceData = null;
		}
		if (m_TriangleInstanceData != null)
		{
			m_TriangleInstanceData.Dispose();
			m_TriangleInstanceData = null;
		}
		if (m_EdgeInstanceData != null)
		{
			m_EdgeInstanceData.Dispose();
			m_EdgeInstanceData = null;
		}
		if (m_ClipMapBuffer != null)
		{
			m_ClipMapBuffer.Dispose();
			m_ClipMapBuffer = null;
		}
		for (int i = 0; i < 4; i++)
		{
			if (!m_CascadeCulling[i].m_BuildingHandle.IsCompleted)
			{
				m_CascadeCulling[i].m_BuildingHandle.Complete();
			}
			if (m_CascadeCulling[i].m_BuildingRenderList.IsCreated)
			{
				m_CascadeCulling[i].m_BuildingRenderList.Dispose();
			}
			if (!m_CascadeCulling[i].m_LaneHandle.IsCompleted)
			{
				m_CascadeCulling[i].m_LaneHandle.Complete();
			}
			if (m_CascadeCulling[i].m_LaneRenderList.IsCreated)
			{
				m_CascadeCulling[i].m_LaneRenderList.Dispose();
			}
			if (!m_CascadeCulling[i].m_AreaHandle.IsCompleted)
			{
				m_CascadeCulling[i].m_AreaHandle.Complete();
			}
			if (m_CascadeCulling[i].m_TriangleRenderList.IsCreated)
			{
				m_CascadeCulling[i].m_TriangleRenderList.Dispose();
			}
			if (m_CascadeCulling[i].m_EdgeRenderList.IsCreated)
			{
				m_CascadeCulling[i].m_EdgeRenderList.Dispose();
			}
		}
		if (m_BuildingUpgrade.IsCreated)
		{
			m_BuildingUpgradeDependencies.Complete();
			m_BuildingUpgrade.Dispose();
		}
		m_CascadeCB.Dispose();
		m_CommandBuffer.Dispose();
		m_TerrainMinMax.Dispose();
		base.OnDestroy();
	}
```

- `private OnHeightsChanged() : System.Void`  

```csharp
private void OnHeightsChanged()
	{
		m_LastRequest = m_LastWrite;
		m_LastWrite = int4.zero;
		if (m_LastRequest.z == 0 || m_LastRequest.w == 0)
		{
			m_LastRequest = new int4(0, 0, m_HeightmapCascade.width, m_HeightmapCascade.height);
		}
		m_GroundHeightSystem.BeforeReadHeights();
		m_AsyncGPUReadback.Request(m_HeightmapCascade, 0, m_LastRequest.x, m_LastRequest.z, m_LastRequest.y, m_LastRequest.w, baseLod, 1);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_NewMapThisFrame = m_NewMap;
		if (!(m_Heightmap == null))
		{
			m_CPUHeightReaders.Complete();
			m_CPUHeightReaders = default(JobHandle);
			if (!freezeCascadeUpdates)
			{
				UpdateCascades(m_Loaded, m_HeightsReadyAfterLoading);
				m_Loaded = false;
				m_HeightsReadyAfterLoading = false;
			}
			UpdateGPUReadback();
			UpdateGPUTerrain();
		}
	}
```

- `private Overlap(Unity.Mathematics.float4& A, Unity.Mathematics.float4& B) : System.Boolean`  

```csharp
private bool Overlap(ref float4 A, ref float4 B)
	{
		if (A.x > B.z || B.x > A.z || A.z < B.x || B.z < A.x || A.y > B.w || B.y > A.w || A.w < B.y || B.w < A.y)
		{
			return false;
		}
		return true;
	}
```

- `public PreviewBrush(Game.Prefabs.TerraformingType type, Colossal.Mathematics.Bounds2 area, Game.Tools.Brush brush, UnityEngine.Texture texture) : System.Void`  

```csharp
public void PreviewBrush(TerraformingType type, Bounds2 area, Brush brush, Texture texture)
	{
	}
```

- `private RenderCascade(System.Int32 cascadeIndex, Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer) : System.Void`  

```csharp
private void RenderCascade(int cascadeIndex, float4 area, float4 viewport, ref CommandBuffer cmdBuffer)
	{
		bool flag = true;
		bool flag2 = viewport.x == 0f && viewport.y == 0f && viewport.z == 1f && viewport.w == 1f;
		Rect scissor = new Rect(viewport.x * (float)m_HeightmapCascade.width, viewport.y * (float)m_HeightmapCascade.height, viewport.z * (float)m_HeightmapCascade.width, viewport.w * (float)m_HeightmapCascade.height);
		RenderTargetBinding binding = new RenderTargetBinding(m_HeightmapCascade, (flag2 && flag) ? RenderBufferLoadAction.DontCare : RenderBufferLoadAction.Load, RenderBufferStoreAction.Store, m_HeightmapDepth, RenderBufferLoadAction.DontCare, RenderBufferStoreAction.DontCare);
		cmdBuffer.SetRenderTarget(binding, 0, CubemapFace.Unknown, cascadeIndex);
		cmdBuffer.ClearRenderTarget(clearDepth: true, clearColor: false, UnityEngine.Color.black, 1f);
		cmdBuffer.EnableScissorRect(scissor);
		if (flag)
		{
			float num = ((cascadeIndex < baseLod) ? math.pow(2f, -(cascadeIndex - baseLod)) : (1f / math.pow(2f, cascadeIndex - baseLod)));
			float2 @float = new Vector2(num, num);
			float2 float2 = (area.xy - playableOffset) / playableArea;
			if (cascadeIndex == baseLod || baseLod == 0)
			{
				cmdBuffer.Blit(heightmap, BuiltinRenderTextureType.CurrentActive, @float, float2);
			}
			else
			{
				cmdBuffer.SetGlobalVector("_CascadeHeightmapOffsetScale", new float4(float2, @float));
				@float = (area.zw - area.xy) / worldSize;
				float2 = (area.xy - worldOffset) / worldSize;
				cmdBuffer.SetGlobalVector("_CascadeWorldOffsetScale", new float4(float2, @float));
				cmdBuffer.Blit(heightmap, BuiltinRenderTextureType.CurrentActive, m_TerrainBlit);
			}
		}
		Matrix4x4 proj = Matrix4x4.Ortho(area.x, area.z, area.w, area.y, heightScaleOffset.x + heightScaleOffset.y, heightScaleOffset.y);
		proj.m02 *= -1f;
		proj.m12 *= -1f;
		proj.m22 *= -1f;
		proj.m32 *= -1f;
		cmdBuffer.SetViewProjectionMatrices(GL.GetGPUProjectionMatrix(proj, renderIntoTexture: true), Matrix4x4.identity);
		CascadeCullInfo cascadeCullInfo = m_CascadeCulling[cascadeIndex];
		cascadeCullInfo.m_BuildingHandle.Complete();
		cascadeCullInfo.m_LaneHandle.Complete();
		cascadeCullInfo.m_AreaHandle.Complete();
		if (cascadeCullInfo.m_BuildingRenderList.IsCreated || cascadeCullInfo.m_LaneRenderList.IsCreated || cascadeCullInfo.m_TriangleRenderList.IsCreated || cascadeCullInfo.m_EdgeRenderList.IsCreated)
		{
			NativeArray<BuildingLotDraw> lots = default(NativeArray<BuildingLotDraw>);
			NativeArray<LaneDraw> lanes = default(NativeArray<LaneDraw>);
			NativeArray<AreaTriangle> triangles = default(NativeArray<AreaTriangle>);
			NativeArray<AreaEdge> edges = default(NativeArray<AreaEdge>);
			if (cascadeCullInfo.m_BuildingRenderList.IsCreated)
			{
				lots = cascadeCullInfo.m_BuildingRenderList.AsArray();
			}
			if (cascadeCullInfo.m_LaneRenderList.IsCreated)
			{
				lanes = cascadeCullInfo.m_LaneRenderList.AsArray();
			}
			if (cascadeCullInfo.m_TriangleRenderList.IsCreated)
			{
				triangles = cascadeCullInfo.m_TriangleRenderList.AsArray();
			}
			if (cascadeCullInfo.m_EdgeRenderList.IsCreated)
			{
				edges = cascadeCullInfo.m_EdgeRenderList.AsArray();
			}
			DrawHeightAdjustments(ref cmdBuffer, cascadeIndex, area, viewport, binding, ref lots, ref lanes, ref triangles, ref edges, ref cascadeCullInfo.m_LotMaterial, ref cascadeCullInfo.m_LaneMaterial, ref cascadeCullInfo.m_AreaMaterial);
			if (cascadeCullInfo.m_BuildingRenderList.IsCreated)
			{
				cascadeCullInfo.m_BuildingRenderList.Dispose();
			}
			if (cascadeCullInfo.m_LaneRenderList.IsCreated)
			{
				cascadeCullInfo.m_LaneRenderList.Dispose();
			}
			if (cascadeCullInfo.m_TriangleRenderList.IsCreated)
			{
				cascadeCullInfo.m_TriangleRenderList.Dispose();
			}
			if (cascadeCullInfo.m_EdgeRenderList.IsCreated)
			{
				cascadeCullInfo.m_EdgeRenderList.Dispose();
			}
		}
		cmdBuffer.DisableScissorRect();
	}
```

- `public RenderCascades() : System.Void`  

```csharp
public void RenderCascades()
	{
		if (heightMapRenderRequired)
		{
			m_GroundHeightSystem.BeforeUpdateHeights();
			m_CascadeCB.Clear();
			m_BuildingInstanceData.StartFrame();
			m_LaneInstanceData.StartFrame();
			m_TriangleInstanceData.StartFrame();
			m_EdgeInstanceData.StartFrame();
			if (baseLod != 0)
			{
				Texture value = ((m_WorldMapEditable != null) ? m_WorldMapEditable : worldHeightmap);
				m_TerrainBlit.SetTexture("_WorldMap", value);
			}
			for (int num = 3; num >= baseLod; num--)
			{
				if (heightMapSliceUpdated[num])
				{
					RenderCascade(num, m_CascadeRanges[num], heightMapViewport[num], ref m_CascadeCB);
				}
			}
			if (baseLod > 0 && heightMapSliceUpdated[0])
			{
				int4 lastWorldWrite = new int4((int)(heightMapViewport[0].x * (float)m_HeightmapCascade.width), (int)(heightMapViewport[0].y * (float)m_HeightmapCascade.height), (int)(heightMapViewport[0].z * (float)m_HeightmapCascade.width), (int)(heightMapViewport[0].w * (float)m_HeightmapCascade.height));
				if (m_LastWorldWrite.z == 0)
				{
					m_LastWorldWrite = lastWorldWrite;
				}
				else
				{
					int2 @int = new int2(math.min(m_LastWorldWrite.x, lastWorldWrite.x), math.min(m_LastWorldWrite.y, lastWorldWrite.y));
					int2 int2 = new int2(math.max(m_LastWorldWrite.x + m_LastWorldWrite.z, lastWorldWrite.x + lastWorldWrite.z), math.max(m_LastWorldWrite.y + m_LastWorldWrite.w, lastWorldWrite.y + lastWorldWrite.w));
					m_LastWorldWrite.xy = @int;
					m_LastWorldWrite.zw = int2 - @int;
				}
				RenderWorldMapToCascade(m_CascadeRanges[0], heightMapViewport[0], ref m_CascadeCB);
			}
			m_BuildingInstanceData.EndFrame();
			m_LaneInstanceData.EndFrame();
			m_TriangleInstanceData.EndFrame();
			m_EdgeInstanceData.EndFrame();
			Graphics.ExecuteCommandBuffer(m_CascadeCB);
			if (heightMapSliceUpdated[baseLod])
			{
				int4 lastWrite = new int4((int)(heightMapViewport[baseLod].x * (float)m_HeightmapCascade.width), (int)(heightMapViewport[baseLod].y * (float)m_HeightmapCascade.height), (int)(heightMapViewport[baseLod].z * (float)m_HeightmapCascade.width), (int)(heightMapViewport[baseLod].w * (float)m_HeightmapCascade.height));
				if (m_LastWrite.z == 0)
				{
					m_LastWrite = lastWrite;
				}
				else
				{
					int2 int3 = new int2(math.min(m_LastWrite.x, lastWrite.x), math.min(m_LastWrite.y, lastWrite.y));
					int2 int4 = new int2(math.max(m_LastWrite.x + m_LastWrite.z, lastWrite.x + lastWrite.z), math.max(m_LastWrite.y + m_LastWrite.w, lastWrite.y + lastWrite.w));
					m_LastWrite.xy = int3;
					m_LastWrite.zw = int4 - int3;
				}
				TriggerAsyncChange();
			}
		}
		m_CascadeReset = false;
	}
```

- `private RenderWorldMapToCascade(Unity.Mathematics.float4 area, Unity.Mathematics.float4 viewport, UnityEngine.Rendering.CommandBuffer& cmdBuffer) : System.Void`  

```csharp
private void RenderWorldMapToCascade(float4 area, float4 viewport, ref CommandBuffer cmdBuffer)
	{
		if (m_WorldMapEditable != null)
		{
			bool flag = viewport.x == 0f && viewport.y == 0f && viewport.z == 1f && viewport.w == 1f;
			Texture source = m_WorldMapEditable;
			Rect scissor = new Rect(viewport.x * (float)m_HeightmapCascade.width, viewport.y * (float)m_HeightmapCascade.height, viewport.z * (float)m_HeightmapCascade.width, viewport.w * (float)m_HeightmapCascade.height);
			RenderTargetBinding binding = new RenderTargetBinding(m_HeightmapCascade, flag ? RenderBufferLoadAction.DontCare : RenderBufferLoadAction.Load, RenderBufferStoreAction.Store, m_HeightmapDepth, RenderBufferLoadAction.DontCare, RenderBufferStoreAction.DontCare);
			cmdBuffer.SetRenderTarget(binding, 0, CubemapFace.Unknown, 0);
			cmdBuffer.ClearRenderTarget(clearDepth: true, clearColor: false, UnityEngine.Color.black, 1f);
			cmdBuffer.EnableScissorRect(scissor);
			Vector2 scale = new Vector2(1f, 1f);
			Vector2 offset = new Vector2
			{
				x = (area.x - worldOffset.x) / worldSize.x,
				y = (area.y - worldOffset.y) / worldSize.y
			};
			cmdBuffer.Blit(source, BuiltinRenderTextureType.CurrentActive, scale, offset);
		}
	}
```

- `public ReplaceHeightmap(UnityEngine.Texture2D inMap) : System.Void`  

```csharp
public void ReplaceHeightmap(Texture2D inMap)
	{
		Texture2D texture2D = ((inMap != null) ? inMap : CreateDefaultHeightmap((worldHeightmap != null) ? worldHeightmap.width : kDefaultHeightmapWidth, (worldHeightmap != null) ? worldHeightmap.height : kDefaultHeightmapHeight));
		Texture2D texture2D2 = ToR16(texture2D);
		SetHeightmap(texture2D2);
		FinalizeTerrainData(texture2D2, null, heightScaleOffset, kDefaultMapOffset, kDefaultMapSize, kDefaultWorldOffset, kDefaultWorldSize, worldHeightMinMax);
		if (texture2D2 != texture2D)
		{
			UnityEngine.Object.Destroy(texture2D2);
		}
		if (texture2D != inMap)
		{
			UnityEngine.Object.Destroy(texture2D);
		}
	}
```

- `public ReplaceWorldHeightmap(UnityEngine.Texture2D inMap) : System.Void`  

```csharp
public void ReplaceWorldHeightmap(Texture2D inMap)
	{
		Texture2D texture2D = ToR16(inMap);
		SetWorldHeightmap(texture2D, m_ToolSystem.actionMode.IsEditor());
		FinalizeTerrainData(null, texture2D, heightScaleOffset, kDefaultMapOffset, kDefaultMapSize, kDefaultWorldOffset, kDefaultWorldSize, float2.zero);
		if (texture2D != inMap && texture2D != worldHeightmap)
		{
			UnityEngine.Object.Destroy(texture2D);
		}
	}
```

- `private SaveBitmap(Unity.Collections.NativeArray<System.UInt16> buffer, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
private void SaveBitmap(NativeArray<ushort> buffer, int width, int height)
	{
		using System.IO.BinaryWriter binaryWriter = new System.IO.BinaryWriter(File.OpenWrite("heightmapResult.raw"));
		for (int i = 0; i < height; i++)
		{
			for (int j = 0; j < width; j++)
			{
				binaryWriter.Write(buffer[j + i * width]);
			}
		}
	}
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
public void SetBuildingUpgradeWriterDependency(JobHandle handle)
	{
		m_BuildingUpgradeDependencies = handle;
	}
```

- `private static SetDefaultHeights(UnityEngine.Texture2D targetHeightmap) : System.Void`  

```csharp
private static void SetDefaultHeights(Texture2D targetHeightmap)
	{
		NativeArray<ushort> rawTextureData = targetHeightmap.GetRawTextureData<ushort>();
		ushort value = 8191;
		for (int i = 0; i < rawTextureData.Length; i++)
		{
			rawTextureData[i] = value;
		}
		targetHeightmap.Apply(updateMipmaps: false, makeNoLongerReadable: false);
	}
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_Loaded = true;
		LoadTerrain();
	}
```

- `private SetHeightmap(UnityEngine.Texture2D map) : System.Void`  

```csharp
private void SetHeightmap(Texture2D map)
	{
		if (m_Heightmap == null || m_Heightmap.width != map.width || m_Heightmap.height != map.height)
		{
			if (m_Heightmap != null)
			{
				m_Heightmap.Release();
				UnityEngine.Object.Destroy(m_Heightmap);
			}
			m_Heightmap = new RenderTexture(map.width, map.height, 0, GraphicsFormat.R16_UNorm)
			{
				hideFlags = HideFlags.HideAndDontSave,
				enableRandomWrite = true,
				name = "TerrainHeights",
				filterMode = FilterMode.Bilinear,
				wrapMode = TextureWrapMode.Clamp
			};
			m_Heightmap.Create();
		}
		Graphics.CopyTexture(map, m_Heightmap);
		if (worldHeightmap != null && (worldHeightmap.width != m_Heightmap.width || worldHeightmap.height != m_Heightmap.height))
		{
			DestroyWorldMap();
		}
	}
```

- `public SetTerrainProperties(Unity.Mathematics.float2 heightScaleOffset) : System.Void`  

```csharp
public void SetTerrainProperties(float2 heightScaleOffset)
	{
		FinalizeTerrainData(null, null, heightScaleOffset, playableOffset, playableArea, worldOffset, worldSize, worldHeightMinMax);
	}
```

- `private SetWorldHeightmap(UnityEngine.Texture2D map, System.Boolean isEditor) : System.Void`  

```csharp
private void SetWorldHeightmap(Texture2D map, bool isEditor)
	{
		if (map == null || map.width != m_Heightmap.width || map.height != m_Heightmap.height)
		{
			DestroyWorldMap();
		}
		else if (isEditor)
		{
			if (m_WorldMapEditable == null || worldHeightmap != m_WorldMapEditable || m_WorldMapEditable.width != map.width || m_WorldMapEditable.height != map.height)
			{
				DestroyWorldMap();
				m_WorldMapEditable = new RenderTexture(map.width, map.height, 0, GraphicsFormat.R16_UNorm)
				{
					hideFlags = HideFlags.HideAndDontSave,
					enableRandomWrite = true,
					name = "TerrainWorldHeights",
					filterMode = FilterMode.Bilinear,
					wrapMode = TextureWrapMode.Clamp
				};
				m_WorldMapEditable.Create();
				worldHeightmap = m_WorldMapEditable;
			}
			Graphics.CopyTexture(map, m_WorldMapEditable);
		}
		else
		{
			if (map != worldHeightmap && (m_WorldMapEditable != null || worldHeightmap != null))
			{
				DestroyWorldMap();
			}
			worldHeightmap = map;
		}
	}
```

- `public TerrainHeightsReadyAfterLoading() : System.Void`  

```csharp
public void TerrainHeightsReadyAfterLoading()
	{
		m_HeightsReadyAfterLoading = true;
	}
```

- `private static ToR16(UnityEngine.Texture2D textureRGBA64) : UnityEngine.Texture2D`  

```csharp
private static Texture2D ToR16(Texture2D textureRGBA64)
	{
		if (textureRGBA64 != null && textureRGBA64.graphicsFormat != GraphicsFormat.R16_UNorm)
		{
			NativeArray<ushort> rawTextureData = textureRGBA64.GetRawTextureData<ushort>();
			NativeArray<ushort> data = new NativeArray<ushort>(textureRGBA64.width * textureRGBA64.height, Allocator.Temp);
			for (int i = 0; i < data.Length; i++)
			{
				data[i] = rawTextureData[i * 4];
			}
			Texture2D texture2D = new Texture2D(textureRGBA64.width, textureRGBA64.height, GraphicsFormat.R16_UNorm, TextureCreationFlags.DontInitializePixels | TextureCreationFlags.DontUploadUponCreate);
			texture2D.SetPixelData(data, 0);
			texture2D.Apply();
			return texture2D;
		}
		return textureRGBA64;
	}
```

- `public TriggerAsyncChange() : System.Void`  

```csharp
public void TriggerAsyncChange()
	{
		m_UpdateOutOfDate = m_AsyncGPUReadback.isPending;
		m_HeightMapChanged = true;
		if (!m_UpdateOutOfDate)
		{
			OnHeightsChanged();
		}
	}
```

- `private UpdateCascades(System.Boolean isLoaded, System.Boolean heightsReadyAfterLoading) : System.Void`  

```csharp
private void UpdateCascades(bool isLoaded, bool heightsReadyAfterLoading)
	{
		float3 position = m_CameraUpdateSystem.position;
		float4 @float = new float4(0);
		float4 A = m_UpdateArea;
		heightMapRenderRequired = math.lengthsq(A) > 0f;
		m_UpdateArea = float4.zero;
		m_RoadUpdate = m_CascadeReset;
		m_AreaUpdate = m_CascadeReset;
		if (m_CascadeReset)
		{
			heightMapRenderRequired = true;
			A = m_CascadeRanges[baseLod];
		}
		NativeList<Bounds2> updateBuffer = m_GroundHeightSystem.GetUpdateBuffer();
		bool flag = isLoaded || !m_BuildingsChanged.IsEmptyIgnoreFilter;
		if (flag || (m_ToolSystem.actionMode.IsEditor() && !m_EditorLotQuery.IsEmpty))
		{
			ComponentTypeHandle<Game.Objects.Transform> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Updated> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentLookup<ObjectGeometryData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef);
			float4 area;
			if (flag)
			{
				m_BuildingUpgradeDependencies.Complete();
				m_BuildingUpgradeDependencies = default(JobHandle);
				NativeArray<ArchetypeChunk> nativeArray = (isLoaded ? m_BuildingGroup : m_BuildingsChanged).ToArchetypeChunkArray(Allocator.Temp);
				CompleteDependency();
				for (int i = 0; i < nativeArray.Length; i++)
				{
					NativeArray<Entity> nativeArray2 = nativeArray[i].GetNativeArray(entityTypeHandle);
					NativeArray<Game.Objects.Transform> nativeArray3 = nativeArray[i].GetNativeArray(ref typeHandle);
					NativeArray<PrefabRef> nativeArray4 = nativeArray[i].GetNativeArray(ref typeHandle2);
					bool flag2 = nativeArray[i].Has(ref typeHandle3);
					if (isLoaded)
					{
						heightMapRenderRequired = true;
						m_WaterSystem.TerrainWillChange();
						A = m_CascadeRanges[baseLod];
						break;
					}
					for (int j = 0; j < nativeArray3.Length; j++)
					{
						PrefabRef prefabRef = nativeArray4[j];
						if (CalculateBuildingCullArea(nativeArray3[j], prefabRef.m_Prefab, componentLookup, out area))
						{
							updateBuffer.Add(new Bounds2(area.xy, area.zw));
							m_WaterSystem.TerrainWillChange();
							if (!heightMapRenderRequired)
							{
								heightMapRenderRequired = true;
								A = area;
							}
							else
							{
								A.xy = math.min(A.xy, area.xy);
								A.zw = math.max(A.zw, area.zw);
							}
						}
						if (!flag2 || !m_BuildingUpgrade.TryGetValue(nativeArray2[j], out var item))
						{
							continue;
						}
						if (item != prefabRef.m_Prefab && CalculateBuildingCullArea(nativeArray3[j], item, componentLookup, out area))
						{
							if (!heightMapRenderRequired)
							{
								heightMapRenderRequired = true;
								A = area;
							}
							else
							{
								A.xy = math.min(A.xy, area.xy);
								A.zw = math.max(A.zw, area.zw);
							}
						}
						m_BuildingUpgrade.Remove(nativeArray2[j]);
					}
				}
				nativeArray.Dispose();
			}
			if (m_ToolSystem.actionMode.IsEditor() && !m_EditorLotQuery.IsEmpty)
			{
				NativeArray<ArchetypeChunk> nativeArray5 = m_EditorLotQuery.ToArchetypeChunkArray(Allocator.Temp);
				CompleteDependency();
				for (int k = 0; k < nativeArray5.Length; k++)
				{
					NativeArray<Game.Objects.Transform> nativeArray6 = nativeArray5[k].GetNativeArray(ref typeHandle);
					NativeArray<PrefabRef> nativeArray7 = nativeArray5[k].GetNativeArray(ref typeHandle2);
					for (int l = 0; l < nativeArray6.Length; l++)
					{
						PrefabRef prefabRef2 = nativeArray7[l];
						if (CalculateBuildingCullArea(nativeArray6[l], prefabRef2.m_Prefab, componentLookup, out area))
						{
							m_WaterSystem.TerrainWillChange();
							if (!heightMapRenderRequired)
							{
								heightMapRenderRequired = true;
								A = area;
							}
							else
							{
								A.xy = math.min(A.xy, area.xy);
								A.zw = math.max(A.zw, area.zw);
							}
						}
					}
				}
				nativeArray5.Dispose();
			}
			m_BuildingUpgrade.Clear();
		}
		if (isLoaded || !m_RoadsChanged.IsEmptyIgnoreFilter)
		{
			NativeArray<ArchetypeChunk> nativeArray8 = (isLoaded ? m_RoadsGroup : m_RoadsChanged).ToArchetypeChunkArray(Allocator.Temp);
			EntityTypeHandle entityTypeHandle2 = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentLookup<NetData> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<NetGeometryData> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Composition> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Orphan> componentLookup5 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<NodeGeometry> componentLookup6 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<EdgeGeometry> componentLookup7 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<StartNodeGeometry> componentLookup8 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<EndNodeGeometry> componentLookup9 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef);
			CompleteDependency();
			for (int m = 0; m < nativeArray8.Length; m++)
			{
				NativeArray<Entity> nativeArray9 = nativeArray8[m].GetNativeArray(entityTypeHandle2);
				NativeArray<PrefabRef> nativeArray10 = nativeArray8[m].GetNativeArray(ref typeHandle4);
				if (isLoaded)
				{
					heightMapRenderRequired = true;
					A = m_CascadeRanges[baseLod];
					m_WaterSystem.TerrainWillChange();
					break;
				}
				for (int n = 0; n < nativeArray9.Length; n++)
				{
					Entity entity = nativeArray9[n];
					if (!componentLookup3.TryGetComponent(nativeArray10[n].m_Prefab, out var componentData) || (componentData.m_Flags & (Game.Net.GeometryFlags.FlattenTerrain | Game.Net.GeometryFlags.ClipTerrain)) == 0)
					{
						continue;
					}
					m_RoadUpdate = true;
					if ((componentData.m_Flags & Game.Net.GeometryFlags.FlattenTerrain) == 0)
					{
						continue;
					}
					Bounds3 bounds = new Bounds3(float.MaxValue, float.MinValue);
					if (componentLookup4.HasComponent(entity))
					{
						EdgeGeometry edgeGeometry = componentLookup7[entity];
						StartNodeGeometry startNodeGeometry = componentLookup8[entity];
						EndNodeGeometry endNodeGeometry = componentLookup9[entity];
						if (math.any(edgeGeometry.m_Start.m_Length + edgeGeometry.m_End.m_Length > 0.1f))
						{
							bounds |= edgeGeometry.m_Bounds;
						}
						if (math.any(startNodeGeometry.m_Geometry.m_Left.m_Length > 0.05f) | math.any(startNodeGeometry.m_Geometry.m_Right.m_Length > 0.05f))
						{
							bounds |= startNodeGeometry.m_Geometry.m_Bounds;
						}
						if (math.any(endNodeGeometry.m_Geometry.m_Left.m_Length > 0.05f) | math.any(endNodeGeometry.m_Geometry.m_Right.m_Length > 0.05f))
						{
							bounds |= endNodeGeometry.m_Geometry.m_Bounds;
						}
					}
					else if (componentLookup5.HasComponent(entity))
					{
						bounds |= componentLookup6[entity].m_Bounds;
					}
					if (bounds.min.x <= bounds.max.x)
					{
						NetData netData = componentLookup2[nativeArray10[n].m_Prefab];
						bounds = MathUtils.Expand(bounds, NetUtils.GetTerrainSmoothingWidth(netData) - 8f);
						updateBuffer.Add(bounds.xz);
						m_WaterSystem.TerrainWillChange();
						if (!heightMapRenderRequired)
						{
							heightMapRenderRequired = true;
							A = new float4(bounds.min.xz, bounds.max.xz);
						}
						else
						{
							A.xy = math.min(A.xy, bounds.min.xz);
							A.zw = math.max(A.zw, bounds.max.xz);
						}
					}
				}
			}
			nativeArray8.Dispose();
		}
		bool num = isLoaded || !m_AreasChanged.IsEmptyIgnoreFilter;
		bool flag3 = isLoaded || heightsReadyAfterLoading;
		if (num)
		{
			NativeArray<ArchetypeChunk> nativeArray11 = (isLoaded ? m_AreasQuery : m_AreasChanged).ToArchetypeChunkArray(Allocator.Temp);
			ComponentTypeHandle<Game.Areas.Terrain> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Terrain_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Clip> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Clip_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Geometry> typeHandle7 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			for (int num2 = 0; num2 < nativeArray11.Length; num2++)
			{
				flag3 |= nativeArray11[num2].Has(ref typeHandle6);
				if (!nativeArray11[num2].Has(ref typeHandle5))
				{
					continue;
				}
				m_AreaUpdate = true;
				NativeArray<Geometry> nativeArray12 = nativeArray11[num2].GetNativeArray(ref typeHandle7);
				if (isLoaded)
				{
					heightMapRenderRequired = true;
					A = m_CascadeRanges[baseLod];
					break;
				}
				for (int num3 = 0; num3 < nativeArray12.Length; num3++)
				{
					Bounds3 bounds2 = nativeArray12[num3].m_Bounds;
					if (bounds2.min.x <= bounds2.max.x)
					{
						updateBuffer.Add(bounds2.xz);
						if (!heightMapRenderRequired)
						{
							heightMapRenderRequired = true;
							A = new float4(bounds2.min.xz, bounds2.max.xz);
						}
						else
						{
							A.xy = math.min(A.xy, bounds2.min.xz);
							A.zw = math.max(A.zw, bounds2.max.xz);
						}
					}
				}
			}
			nativeArray11.Dispose();
		}
		if (heightMapRenderRequired)
		{
			A += new float4(-10f, -10f, 10f, 10f);
		}
		float4 area2 = A;
		for (int num4 = 0; num4 <= baseLod; num4++)
		{
			if (heightMapRenderRequired)
			{
				heightMapViewport[num4] = new float4(A.x - m_CascadeRanges[num4].x, A.y - m_CascadeRanges[num4].y, A.z - m_CascadeRanges[num4].x, A.w - m_CascadeRanges[num4].y);
				heightMapViewport[num4] /= new float4(m_CascadeRanges[num4].z - m_CascadeRanges[num4].x, m_CascadeRanges[num4].w - m_CascadeRanges[num4].y, m_CascadeRanges[num4].z - m_CascadeRanges[num4].x, m_CascadeRanges[num4].w - m_CascadeRanges[num4].y);
				heightMapViewport[num4].zw -= heightMapViewport[num4].xy;
				heightMapViewport[num4] = ClipViewport(heightMapViewport[num4]);
				heightMapSliceUpdated[num4] = heightMapViewport[num4].w > 0f && heightMapViewport[num4].z > 0f;
				area2.xy = math.min(area2.xy, m_CascadeRanges[num4].xy + heightMapViewport[num4].xy * (m_CascadeRanges[num4].zw - m_CascadeRanges[num4].xy));
				area2.zw = math.max(area2.zw, m_CascadeRanges[num4].xy + (heightMapViewport[num4].xy + heightMapViewport[num4].zw) * (m_CascadeRanges[num4].zw - m_CascadeRanges[num4].xy));
			}
			else
			{
				heightMapViewport[num4] = float4.zero;
				heightMapSliceUpdated[num4] = false;
			}
		}
		for (int num5 = baseLod + 1; num5 < 4; num5++)
		{
			float2 float2 = m_CascadeRanges[baseLod].zw - m_CascadeRanges[baseLod].xy;
			float2 /= math.pow(2f, num5 - baseLod);
			float num6 = math.min(float2.x, float2.y) / 4f;
			@float.xy = position.xz - float2 * 0.5f;
			@float.zw = position.xz + float2 * 0.5f;
			if (@float.x < m_CascadeRanges[0].x)
			{
				float num7 = m_CascadeRanges[0].x - @float.x;
				@float.x += num7;
				@float.z += num7;
			}
			if (@float.y < m_CascadeRanges[0].y)
			{
				float num8 = m_CascadeRanges[0].y - @float.y;
				@float.y += num8;
				@float.w += num8;
			}
			if (@float.z > m_CascadeRanges[0].z)
			{
				float num9 = m_CascadeRanges[0].z - @float.z;
				@float.x += num9;
				@float.z += num9;
			}
			if (@float.w > m_CascadeRanges[0].w)
			{
				float num10 = m_CascadeRanges[0].w - @float.w;
				@float.y += num10;
				@float.w += num10;
			}
			float2 float3 = math.abs(@float.xy - new float2(m_CascadeRanges[num5].x, m_CascadeRanges[num5].y));
			if (math.lengthsq(m_CascadeRanges[num5]) == 0f || float3.x > num6 || float3.y > num6)
			{
				heightMapSliceUpdated[num5] = true;
				heightMapViewport[num5] = new float4(0f, 0f, 1f, 1f);
				m_CascadeRanges[num5] = @float;
				if (heightMapRenderRequired)
				{
					A.xy = math.min(A.xy, m_CascadeRanges[num5].xy);
					A.zw = math.max(A.zw, m_CascadeRanges[num5].zw);
					area2.xy = math.min(area2.xy, m_CascadeRanges[num5].xy);
					area2.zw = math.max(area2.zw, m_CascadeRanges[num5].zw);
				}
				else
				{
					heightMapRenderRequired = true;
					A = m_CascadeRanges[num5];
					area2 = A;
				}
			}
			else if (math.lengthsq(A) > 0f && Overlap(ref A, ref m_CascadeRanges[num5]))
			{
				heightMapViewport[num5] = new float4(math.clamp(A.x, m_CascadeRanges[num5].x, m_CascadeRanges[num5].z) - m_CascadeRanges[num5].x, math.clamp(A.y, m_CascadeRanges[num5].y, m_CascadeRanges[num5].w) - m_CascadeRanges[num5].y, math.clamp(A.z, m_CascadeRanges[num5].x, m_CascadeRanges[num5].z) - m_CascadeRanges[num5].x, math.clamp(A.w, m_CascadeRanges[num5].y, m_CascadeRanges[num5].w) - m_CascadeRanges[num5].y);
				heightMapViewport[num5] /= new float4(m_CascadeRanges[num5].z - m_CascadeRanges[num5].x, m_CascadeRanges[num5].w - m_CascadeRanges[num5].y, m_CascadeRanges[num5].z - m_CascadeRanges[num5].x, m_CascadeRanges[num5].w - m_CascadeRanges[num5].y);
				heightMapViewport[num5].zw -= heightMapViewport[num5].xy;
				heightMapViewport[num5] = ClipViewport(heightMapViewport[num5]);
				heightMapSliceUpdated[num5] = heightMapViewport[num5].w > 0f && heightMapViewport[num5].z > 0f;
				area2.xy = math.min(area2.xy, m_CascadeRanges[num5].xy + heightMapViewport[num5].xy * (m_CascadeRanges[num5].zw - m_CascadeRanges[num5].xy));
				area2.zw = math.max(area2.zw, m_CascadeRanges[num5].xy + (heightMapViewport[num5].xy + heightMapViewport[num5].zw) * (m_CascadeRanges[num5].zw - m_CascadeRanges[num5].xy));
			}
			else
			{
				heightMapSliceUpdated[num5] = false;
				heightMapViewport[num5] = float4.zero;
			}
		}
		if (heightMapRenderRequired || m_RoadUpdate || flag3)
		{
			if (heightMapRenderRequired)
			{
				area2 += new float4(-10f, -10f, 10f, 10f);
				m_LastCullArea = area2;
				heightMapSliceUpdatedLast = heightMapSliceUpdated;
				heightMapViewportUpdated = heightMapViewport;
			}
			CullForCascades(area2, heightMapRenderRequired, m_RoadUpdate, m_AreaUpdate, flag3, out var laneCount);
			if (heightMapRenderRequired)
			{
				for (int num11 = 3; num11 >= baseLod; num11--)
				{
					if (heightMapSliceUpdated[num11])
					{
						CullCascade(num11, m_CascadeRanges[num11], heightMapViewport[num11], laneCount);
					}
					else
					{
						heightMapCullArea[num11] = float4.zero;
					}
				}
			}
			JobHandle.ScheduleBatchedJobs();
		}
		for (int num12 = 0; num12 < 4; num12++)
		{
			float4 float4 = m_CascadeRanges[num12];
			float4.zw = 1f / math.max(0.001f, float4.zw - float4.xy);
			float4.xy *= float4.zw;
			m_ShaderCascadeRanges[num12] = float4;
		}
		Shader.SetGlobalVectorArray(ShaderID._CascadeRangesID, m_ShaderCascadeRanges);
		m_CascadeReset = false;
	}
```

- `private UpdateGPUReadback() : System.Void`  

```csharp
private void UpdateGPUReadback()
	{
		m_TerrainMinMax.Update();
		if (m_AsyncGPUReadback.isPending)
		{
			if (!m_AsyncGPUReadback.hasError)
			{
				if (m_AsyncGPUReadback.done)
				{
					NativeArray<ushort> data = m_AsyncGPUReadback.GetData<ushort>();
					WriteCPUHeights(data, m_LastRequest);
					if (m_UpdateOutOfDate)
					{
						m_UpdateOutOfDate = false;
						OnHeightsChanged();
					}
					else
					{
						m_HeightMapChanged = false;
					}
					m_FailCount = 0;
				}
				m_AsyncGPUReadback.IncrementFrame();
			}
			else if (++m_FailCount < 10)
			{
				m_GroundHeightSystem.BeforeReadHeights();
				m_AsyncGPUReadback.Request(m_HeightmapCascade, 0, m_LastRequest.x, m_LastRequest.z, m_LastRequest.y, m_LastRequest.w, baseLod, 1);
			}
			else
			{
				COSystemBase.baseLog.Error("m_AsyncGPUReadback.hasError");
				m_LastRequest = new int4(0, 0, m_HeightmapCascade.width, m_HeightmapCascade.height);
				m_GroundHeightSystem.BeforeReadHeights();
				m_AsyncGPUReadback.Request(m_HeightmapCascade, 0, 0, m_HeightmapCascade.width, 0, m_HeightmapCascade.height, baseLod, 1);
			}
		}
		else
		{
			m_HeightMapChanged = false;
		}
	}
```

- `private UpdateGPUTerrain() : System.Void`  

```csharp
private void UpdateGPUTerrain()
	{
		TerrainSurface validSurface = TerrainSurface.GetValidSurface();
		if (!(validSurface != null))
		{
			return;
		}
		validSurface.UsesCascade = true;
		GetCascadeInfo(out var _, out validSurface.BaseLOD, out var areas, out var ranges, out var size);
		validSurface.CascadeArea = areas;
		validSurface.CascadeRanges = ranges;
		validSurface.CascadeSizes = size;
		validSurface.CascadeTexture = m_HeightmapCascade;
		validSurface.TerrainHeightOffset = heightScaleOffset.y;
		validSurface.TerrainHeightScale = heightScaleOffset.x;
		if (validSurface.RenderClipAreas != null)
		{
			return;
		}
		validSurface.RenderClipAreas = delegate(RenderGraphContext ctx, HDCamera hdCamera)
		{
			Camera camera = hdCamera.camera;
			bool flag = false;
			float w = math.tan(math.radians(camera.fieldOfView) * 0.5f) * 0.002f;
			m_ClipMaterial.SetBuffer(ShaderID._RoadData, clipMapBuffer);
			m_ClipMaterial.SetVector(ShaderID._ClipOffset, new float4(camera.transform.position, w));
			if (clipMapInstances > 0)
			{
				ctx.cmd.DrawMeshInstancedProcedural(m_ClipMesh, 0, m_ClipMaterial, 0, clipMapInstances);
			}
			if (m_RenderingSystem.hideOverlay || m_ToolSystem.activeTool == null || (m_ToolSystem.activeTool.requireAreas & AreaTypeMask.Surfaces) == 0)
			{
				ctx.cmd.DrawMesh(areaClipMesh, Matrix4x4.identity, m_ClipMaterial, 0, 2);
			}
			ctx.cmd.DrawProcedural(Matrix4x4.identity, m_ClipMaterial, flag ? 4 : 3, MeshTopology.Triangles, 3, 1);
		};
	}
```

- `public UpdateMinMax(Game.Tools.Brush brush, Colossal.Mathematics.Bounds2 area) : System.Void`  

```csharp
public void UpdateMinMax(Brush brush, Bounds2 area)
	{
		if (worldHeightmap != null)
		{
			area.min -= worldOffset;
			area.max -= worldOffset;
			area.min /= worldSize;
			area.max /= worldSize;
		}
		else
		{
			area.min -= playableOffset;
			area.max -= playableOffset;
			area.min /= playableArea;
			area.max /= playableArea;
		}
		int4 area2 = new int4((int)math.max(math.floor(area.min.x * (float)m_Heightmap.width) - 1f, 0f), (int)math.max(math.floor(area.min.y * (float)m_Heightmap.height) - 1f, 0f), (int)math.min(math.ceil(area.max.x * (float)m_Heightmap.width) + 1f, m_Heightmap.width - 1), (int)math.min(math.ceil(area.max.y * (float)m_Heightmap.height) + 1f, m_Heightmap.height - 1));
		area2.zw -= area2.xy;
		area2.zw = math.clamp(area2.zw, new int2(m_Heightmap.width / m_TerrainMinMax.size, m_Heightmap.height / m_TerrainMinMax.size), new int2(m_Heightmap.width, m_Heightmap.height));
		m_TerrainMinMax.RequestUpdate(this, m_Heightmap, worldHeightmap, area2);
	}
```

- `private WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer) : System.Void`  

```csharp
private void WriteCPUHeights(NativeArray<ushort> buffer, int4 offsets)
	{
		for (int i = 0; i < offsets.w; i++)
		{
			int dstIndex = (offsets.y + i) * m_HeightmapCascade.width + offsets.x;
			NativeArray<ushort>.Copy(buffer, i * offsets.z, m_CPUHeights, dstIndex, offsets.z);
		}
		m_GroundHeightSystem.AfterReadHeights();
	}
```

- `private WriteCPUHeights(Unity.Collections.NativeArray<System.UInt16> buffer, Unity.Mathematics.int4 offsets) : System.Void`  

```csharp
private void WriteCPUHeights(NativeArray<ushort> buffer, int4 offsets)
	{
		for (int i = 0; i < offsets.w; i++)
		{
			int dstIndex = (offsets.y + i) * m_HeightmapCascade.width + offsets.x;
			NativeArray<ushort>.Copy(buffer, i * offsets.z, m_CPUHeights, dstIndex, offsets.z);
		}
		m_GroundHeightSystem.AfterReadHeights();
	}
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


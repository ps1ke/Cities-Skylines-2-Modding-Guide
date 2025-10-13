# Game.Tools.ObjectToolBaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class abstract public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public abstract class ObjectToolBaseSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    protected Game.Objects.SearchSystem m_ObjectSearchSystem;
    protected Game.Simulation.WaterSystem m_WaterSystem;
    protected Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle;

    protected ObjectToolBaseSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected Unity.Jobs.JobHandle CreateDefinitions(Unity.Entities.Entity objectPrefab, Unity.Entities.Entity transformPrefab, Unity.Entities.Entity brushPrefab, Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity laneEditor, Unity.Entities.Entity theme, Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeReference<Game.Tools.ObjectToolBaseSystem+AttachmentData> attachmentPrefab, System.Boolean editorMode, System.Boolean lefthandTraffic, System.Boolean removing, System.Boolean stamping, System.Single brushSize, System.Single brushAngle, System.Single brushStrength, System.Single distance, System.Single deltaTime, Game.Common.RandomSeed randomSeed, Game.Tools.Snap snap, Game.Tools.AgeMask ageMask, Unity.Jobs.JobHandle inputDeps);
    public static System.Int32 GetFirstNodeIndex(Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> nodes, Unity.Mathematics.int2 range);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
}
```


## Fields

- `protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `protected Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
protected Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `protected Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
protected Game.Simulation.WaterSystem m_WaterSystem;
```

- `protected Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
protected Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle;
```


## Constructors

- `protected ObjectToolBaseSystem()`  

```csharp
[Preserve]
	protected ObjectToolBaseSystem()
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

- `protected CreateDefinitions(Unity.Entities.Entity objectPrefab, Unity.Entities.Entity transformPrefab, Unity.Entities.Entity brushPrefab, Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity laneEditor, Unity.Entities.Entity theme, Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeReference<Game.Tools.ObjectToolBaseSystem+AttachmentData> attachmentPrefab, System.Boolean editorMode, System.Boolean lefthandTraffic, System.Boolean removing, System.Boolean stamping, System.Single brushSize, System.Single brushAngle, System.Single brushStrength, System.Single distance, System.Single deltaTime, Game.Common.RandomSeed randomSeed, Game.Tools.Snap snap, Game.Tools.AgeMask ageMask, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected JobHandle CreateDefinitions(Entity objectPrefab, Entity transformPrefab, Entity brushPrefab, Entity owner, Entity original, Entity laneEditor, Entity theme, NativeList<ControlPoint> controlPoints, NativeReference<AttachmentData> attachmentPrefab, bool editorMode, bool lefthandTraffic, bool removing, bool stamping, float brushSize, float brushAngle, float brushStrength, float distance, float deltaTime, RandomSeed randomSeed, Snap snap, AgeMask ageMask, JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle deps;
		JobHandle jobHandle = IJobExtensions.Schedule(new CreateDefinitionsJob
		{
			m_EditorMode = editorMode,
			m_LefthandTraffic = lefthandTraffic,
			m_Removing = removing,
			m_Stamping = stamping,
			m_BrushSize = brushSize,
			m_BrushAngle = brushAngle,
			m_BrushStrength = brushStrength,
			m_Distance = distance,
			m_DeltaTime = deltaTime,
			m_ObjectPrefab = objectPrefab,
			m_TransformPrefab = transformPrefab,
			m_BrushPrefab = brushPrefab,
			m_Owner = owner,
			m_Original = original,
			m_LaneEditor = laneEditor,
			m_Theme = theme,
			m_RandomSeed = randomSeed,
			m_Snap = snap,
			m_AgeMask = ageMask,
			m_ControlPoints = controlPoints,
			m_AttachmentPrefab = attachmentPrefab,
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaClearData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Clear_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaSpaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Space_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaLotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAssetStampData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AssetStampData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBrushData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BrushData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingTerraformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCreatureSpawnData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CreatureSpawnData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceholderBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_CachedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabPlaceholderElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabRequirementElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ObjectRequirementElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabServiceUpgradeBuilding = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeBuilding_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabBrushCells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BrushCell_RO_BufferLookup, ref base.CheckedStateRef),
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(inputDeps, dependencies, deps));
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		return jobHandle;
	}
```

- `public static GetFirstNodeIndex(Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> nodes, Unity.Mathematics.int2 range) : System.Int32`  

```csharp
public static int GetFirstNodeIndex(DynamicBuffer<SubAreaNode> nodes, int2 range)
	{
		int result = 0;
		float num = float.MaxValue;
		for (int i = range.x; i < range.y; i++)
		{
			int index = math.select(i + 1, range.x, i + 1 == range.y);
			float t;
			float num2 = MathUtils.Distance(new Line2.Segment(nodes[i].m_Position.xz, nodes[index].m_Position.xz), default(float2), out t);
			if (num2 < num)
			{
				result = i;
				num = num2;
			}
		}
		return result;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
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


## Nested types

- `Game.Tools.ObjectToolBaseSystem+AttachmentData`  
- `Game.Tools.ObjectToolBaseSystem+CreateDefinitionsJob`  
- `Game.Tools.ObjectToolBaseSystem+TypeHandle`  


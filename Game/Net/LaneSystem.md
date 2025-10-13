# Game.Net.LaneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Net.LaneReferencesSystem m_LaneReferencesSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_OwnerQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_DeletedTempTypes;
    private Unity.Entities.ComponentTypeSet m_TempOwnerTypes;
    private Unity.Entities.ComponentTypeSet m_HideLaneTypes;
    private Game.Net.LaneSystem+TypeHandle __TypeHandle;

    public LaneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Net.LaneReferencesSystem m_LaneReferencesSystem`  

```csharp
private Game.Net.LaneReferencesSystem m_LaneReferencesSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_OwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnerQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_DeletedTempTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_DeletedTempTypes;
```

- `private Unity.Entities.ComponentTypeSet m_TempOwnerTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TempOwnerTypes;
```

- `private Unity.Entities.ComponentTypeSet m_HideLaneTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HideLaneTypes;
```

- `private Game.Net.LaneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneSystem()`  

```csharp
[Preserve]
	public LaneSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_LaneReferencesSystem = base.World.GetOrCreateSystemManaged<LaneReferencesSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_OwnerQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<SubLane>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<OutsideConnection>(),
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<Area>()
			}
		});
		m_BuildingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		m_AppliedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		m_DeletedTempTypes = new ComponentTypeSet(ComponentType.ReadWrite<Deleted>(), ComponentType.ReadWrite<Temp>());
		m_TempOwnerTypes = new ComponentTypeSet(ComponentType.ReadWrite<Temp>(), ComponentType.ReadWrite<Owner>());
		m_HideLaneTypes = new ComponentTypeSet(ComponentType.ReadWrite<CullingInfo>(), ComponentType.ReadWrite<MeshBatch>(), ComponentType.ReadWrite<MeshColor>());
		RequireForUpdate(m_OwnerQuery);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateLanesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OrphanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PseudoRandomSeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElevationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnderConstructionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ConnectedNodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneSignalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneSignal_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildOrderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_BuildOrder_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OverriddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaClearData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Clear_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterwayComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathwayComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TaxiwayComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneArchetypeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneArchetypeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_CutRanges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_CutRange_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabCompositionLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabCompositionCrosswalks = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionCrosswalk_RO_BufferLookup, ref base.CheckedStateRef),
			m_DefaultNetLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_DefaultNetLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PlaceholderObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ObjectRequirements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ObjectRequirementElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabAuxiliaryLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AuxiliaryNetLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabCompositionPieces = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionPiece_RO_BufferLookup, ref base.CheckedStateRef),
			m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_RandomSeed = RandomSeed.Next(),
			m_DefaultTheme = m_CityConfigurationSystem.defaultTheme,
			m_AppliedTypes = m_AppliedTypes,
			m_DeletedTempTypes = m_DeletedTempTypes,
			m_TempOwnerTypes = m_TempOwnerTypes,
			m_HideLaneTypes = m_HideLaneTypes,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_BuildingConfigurationData = m_BuildingSettingsQuery.GetSingleton<BuildingConfigurationData>(),
			m_SkipLaneQueue = m_LaneReferencesSystem.GetSkipLaneQueue().AsParallelWriter(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_OwnerQuery, base.Dependency);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_LaneReferencesSystem.AddSkipLaneWriter(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Net.LaneSystem+LaneKey`  
- `Game.Net.LaneSystem+ConnectionKey`  
- `Game.Net.LaneSystem+ConnectPosition`  
- `Game.Net.LaneSystem+EdgeTarget`  
- `Game.Net.LaneSystem+MiddleConnection`  
- `Game.Net.LaneSystem+SourcePositionComparer`  
- `Game.Net.LaneSystem+TargetPositionComparer`  
- `Game.Net.LaneSystem+MiddleConnectionComparer`  
- `Game.Net.LaneSystem+LaneAnchor`  
- `Game.Net.LaneSystem+LaneBuffer`  
- `Game.Net.LaneSystem+CompositionData`  
- `Game.Net.LaneSystem+UpdateLanesJob`  
- `Game.Net.LaneSystem+TypeHandle`  


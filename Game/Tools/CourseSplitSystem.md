# Game.Tools.CourseSplitSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CourseSplitSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier;
    private Game.Net.SearchSystem m_SearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_CourseQuery;
    private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle;

    public CourseSplitSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Boolean GetAuxCourse(Game.Tools.NetCourse& courseData, Game.Prefabs.AuxiliaryNet auxiliaryNet, System.Boolean invert);
    private static Game.Tools.CreationDefinition GetAuxDefinition(Game.Tools.CreationDefinition creationDefinition, Game.Prefabs.AuxiliaryNet auxiliaryNet);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier`  

```csharp
private Game.Tools.ToolReadyBarrier m_ToolReadyBarrier;
```

- `private Game.Net.SearchSystem m_SearchSystem`  

```csharp
private Game.Net.SearchSystem m_SearchSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_CourseQuery`  

```csharp
private Unity.Entities.EntityQuery m_CourseQuery;
```

- `private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.CourseSplitSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CourseSplitSystem()`  

```csharp
[Preserve]
	public CourseSplitSystem()
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

- `private static GetAuxCourse(Game.Tools.NetCourse& courseData, Game.Prefabs.AuxiliaryNet auxiliaryNet, System.Boolean invert) : System.Boolean`  

```csharp
private static bool GetAuxCourse(ref NetCourse courseData, AuxiliaryNet auxiliaryNet, bool invert)
	{
		courseData.m_StartPosition.m_Flags |= CoursePosFlags.IsParallel;
		courseData.m_EndPosition.m_Flags |= CoursePosFlags.IsParallel;
		courseData.m_FixedIndex = -1;
		if (auxiliaryNet.m_Position.x != 0f)
		{
			if ((courseData.m_StartPosition.m_Flags & (CoursePosFlags.IsFirst | CoursePosFlags.IsLast)) == (CoursePosFlags.IsFirst | CoursePosFlags.IsLast))
			{
				return false;
			}
			courseData.m_Curve = MathUtils.Cut(courseData.m_Curve, new Bounds1(courseData.m_StartPosition.m_CourseDelta, courseData.m_EndPosition.m_CourseDelta));
			courseData.m_Curve = NetUtils.OffsetCurveLeftSmooth(courseData.m_Curve, 0f - auxiliaryNet.m_Position.x);
			courseData.m_Length = MathUtils.Length(courseData.m_Curve);
			courseData.m_StartPosition.m_CourseDelta = 0f;
			courseData.m_EndPosition.m_CourseDelta = 1f;
			courseData.m_StartPosition.m_Position.x += auxiliaryNet.m_Position.x * 0.01f;
			courseData.m_EndPosition.m_Position.x += auxiliaryNet.m_Position.x * 0.01f;
		}
		if (auxiliaryNet.m_Position.z != 0f)
		{
			Bounds1 t = new Bounds1(courseData.m_StartPosition.m_CourseDelta, courseData.m_EndPosition.m_CourseDelta);
			float num = math.abs(auxiliaryNet.m_Position.z);
			float num2 = courseData.m_Length - num * 2f;
			if (!(num2 > math.max(0.9f, num - 0.5f)) || !MathUtils.ClampLength(courseData.m_Curve.xz, ref t, courseData.m_Length - num) || !MathUtils.ClampLengthInverse(courseData.m_Curve.xz, ref t, num2))
			{
				return false;
			}
			courseData.m_Curve = MathUtils.Cut(courseData.m_Curve, t);
			courseData.m_Length = num2;
			courseData.m_StartPosition.m_CourseDelta = 0f;
			courseData.m_EndPosition.m_CourseDelta = 1f;
		}
		if (auxiliaryNet.m_Position.y != 0f)
		{
			courseData.m_Curve.y += auxiliaryNet.m_Position.y;
			courseData.m_StartPosition.m_Position.y += auxiliaryNet.m_Position.y;
			courseData.m_EndPosition.m_Position.y += auxiliaryNet.m_Position.y;
		}
		if (invert)
		{
			courseData.m_Curve = MathUtils.Invert(courseData.m_Curve);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_Entity, ref courseData.m_EndPosition.m_Entity);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_CourseDelta, ref courseData.m_EndPosition.m_CourseDelta);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_SplitPosition, ref courseData.m_EndPosition.m_SplitPosition);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_Position, ref courseData.m_EndPosition.m_Position);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_Rotation, ref courseData.m_EndPosition.m_Rotation);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_Elevation, ref courseData.m_EndPosition.m_Elevation);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_Flags, ref courseData.m_EndPosition.m_Flags);
			CommonUtils.Swap(ref courseData.m_StartPosition.m_ParentMesh, ref courseData.m_EndPosition.m_ParentMesh);
			quaternion a = quaternion.RotateY(MathF.PI);
			courseData.m_StartPosition.m_Rotation = math.mul(a, courseData.m_StartPosition.m_Rotation);
			courseData.m_EndPosition.m_Rotation = math.mul(a, courseData.m_EndPosition.m_Rotation);
			courseData.m_StartPosition.m_CourseDelta = 1f - courseData.m_StartPosition.m_CourseDelta;
			courseData.m_EndPosition.m_CourseDelta = 1f - courseData.m_EndPosition.m_CourseDelta;
		}
		return true;
	}
```

- `private static GetAuxDefinition(Game.Tools.CreationDefinition creationDefinition, Game.Prefabs.AuxiliaryNet auxiliaryNet) : Game.Tools.CreationDefinition`  

```csharp
private static CreationDefinition GetAuxDefinition(CreationDefinition creationDefinition, AuxiliaryNet auxiliaryNet)
	{
		return new CreationDefinition
		{
			m_Prefab = auxiliaryNet.m_Prefab,
			m_Flags = creationDefinition.m_Flags,
			m_RandomSeed = creationDefinition.m_RandomSeed
		};
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ToolReadyBarrier = base.World.GetOrCreateSystemManaged<ToolReadyBarrier>();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_CourseQuery = GetEntityQuery(ComponentType.ReadOnly<CreationDefinition>(), ComponentType.ReadOnly<NetCourse>(), ComponentType.ReadOnly<Updated>());
		RequireForUpdate(m_CourseQuery);
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
		NativeHashMap<Entity, bool> deletedEntities = new NativeHashMap<Entity, bool>(100, Allocator.TempJob);
		NativeList<Course> nativeList = new NativeList<Course>(Allocator.TempJob);
		NativeQueue<Overlap> overlapQueue = new NativeQueue<Overlap>(Allocator.TempJob);
		NativeList<Overlap> nativeList2 = new NativeList<Overlap>(Allocator.TempJob);
		NativeParallelQueue<IntersectPos> nativeParallelQueue = new NativeParallelQueue<IntersectPos>(Allocator.TempJob);
		CheckCoursesJob jobData = new CheckCoursesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpgradedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedEntities = deletedEntities,
			m_CourseList = nativeList
		};
		JobHandle dependencies;
		FindOverlapsJob jobData2 = new FindOverlapsJob
		{
			m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AuxiliaryNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AuxiliaryNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_SearchTree = m_SearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_CourseList = nativeList,
			m_OverlapQueue = overlapQueue.AsParallelWriter()
		};
		DequeueOverlapsJob jobData3 = new DequeueOverlapsJob
		{
			m_OverlapQueue = overlapQueue,
			m_OverlapList = nativeList2
		};
		CheckCourseIntersectionsJob jobData4 = new CheckCourseIntersectionsJob
		{
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabAuxiliaryNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AuxiliaryNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_CourseList = nativeList,
			m_OverlapList = nativeList2,
			m_DeletedEntities = deletedEntities,
			m_Results = nativeParallelQueue.AsWriter()
		};
		JobHandle deps;
		CheckCourseIntersectionResultsJob jobData5 = new CheckCourseIntersectionResultsJob
		{
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalCurveCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalCurveCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceableData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabFixedNetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_FixedNetElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabAuxiliaryNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AuxiliaryNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_LefthandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_CourseList = nativeList,
			m_DeletedEntities = deletedEntities,
			m_IntersectionQueue = nativeParallelQueue.AsReader(),
			m_CommandBuffer = m_ToolReadyBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle jobHandle = IJobParallelForDeferExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(JobChunkExtensions.Schedule(jobData, m_CourseQuery, base.Dependency), dependencies), jobData: jobData2, list: nativeList, innerloopBatchCount: 1);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData3, jobHandle);
		JobHandle jobHandle3 = jobData4.Schedule(nativeList2, 1, jobHandle2);
		JobHandle jobHandle4 = jobData5.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle3, deps));
		deletedEntities.Dispose(jobHandle4);
		nativeList.Dispose(jobHandle4);
		overlapQueue.Dispose(jobHandle2);
		nativeList2.Dispose(jobHandle3);
		nativeParallelQueue.Dispose(jobHandle4);
		m_SearchSystem.AddNetSearchTreeReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle4);
		m_WaterSystem.AddSurfaceReader(jobHandle4);
		m_ToolReadyBarrier.AddJobHandleForProducer(jobHandle4);
		base.Dependency = jobHandle4;
	}
```


## Nested types

- `Game.Tools.CourseSplitSystem+IntersectPos`  
- `Game.Tools.CourseSplitSystem+Course`  
- `Game.Tools.CourseSplitSystem+Overlap`  
- `Game.Tools.CourseSplitSystem+CheckCoursesJob`  
- `Game.Tools.CourseSplitSystem+FindOverlapsJob`  
- `Game.Tools.CourseSplitSystem+DequeueOverlapsJob`  
- `Game.Tools.CourseSplitSystem+CheckCourseIntersectionsJob`  
- `Game.Tools.CourseSplitSystem+CourseHeightItem`  
- `Game.Tools.CourseSplitSystem+CourseHeightData`  
- `Game.Tools.CourseSplitSystem+CheckCourseIntersectionResultsJob`  
- `Game.Tools.CourseSplitSystem+TypeHandle`  


# Game.Areas.AreaResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaResourceSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers;
    private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_596039173_0;

    public AreaResourceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single CalculateBuildable(Unity.Mathematics.float3 worldPos, Unity.Mathematics.float2 cellSize, Game.Simulation.WaterSurfaceData m_WaterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Colossal.Mathematics.Bounds1 buildableLandMaxSlope);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  

```csharp
private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers;
```

- `private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_596039173_0`  

```csharp
private Unity.Entities.EntityQuery __query_596039173_0;
```


## Constructors

- `public AreaResourceSystem()`  

```csharp
[Preserve]
	public AreaResourceSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<AreasConfigurationData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_596039173_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public static CalculateBuildable(Unity.Mathematics.float3 worldPos, Unity.Mathematics.float2 cellSize, Game.Simulation.WaterSurfaceData m_WaterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Colossal.Mathematics.Bounds1 buildableLandMaxSlope) : System.Single`  

```csharp
public static float CalculateBuildable(float3 worldPos, float2 cellSize, WaterSurfaceData m_WaterSurfaceData, TerrainHeightData terrainHeightData, Bounds1 buildableLandMaxSlope)
	{
		float num = WaterUtils.SampleDepth(ref m_WaterSurfaceData, worldPos);
		float result = 0f;
		if (num < 0.1f)
		{
			float num2 = TerrainUtils.SampleHeight(ref terrainHeightData, worldPos + new float3(-0.5f * cellSize.x, 0f, 0f));
			float num3 = TerrainUtils.SampleHeight(ref terrainHeightData, worldPos + new float3(0.5f * cellSize.x, 0f, 0f));
			float3 x = new float3(cellSize.x, num3 - num2, 0f);
			float num4 = TerrainUtils.SampleHeight(ref terrainHeightData, worldPos + new float3(0f, 0f, 0f - cellSize.y));
			float num5 = TerrainUtils.SampleHeight(ref terrainHeightData, worldPos + new float3(0f, 0f, cellSize.y));
			float3 y = new float3(0f, num5 - num4, cellSize.y);
			float3 x2 = math.cross(x, y);
			float3 y2 = math.up();
			float x3 = math.length(math.cross(x2, y2)) / math.dot(x2, y2);
			result = math.saturate(math.unlerp(buildableLandMaxSlope.max, buildableLandMaxSlope.min, math.abs(x3)));
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
		m_ObjectUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Objects.UpdateCollectSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_UpdatedAreaQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Extractor>(),
				ComponentType.ReadOnly<MapFeatureElement>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_MapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapFeatureElement>(), ComponentType.Exclude<Native>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Updated>());
		m_BrushQuery = GetEntityQuery(ComponentType.ReadOnly<Brush>(), ComponentType.ReadOnly<Applied>());
		m_LastCityModifiers = new NativeArray<float2>(2, Allocator.Persistent);
		RequireForUpdate<AreasConfigurationData>();
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
		base.OnDestroy();
		m_LastCityModifiers.Dispose();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (m_CitySystem.City != Entity.Null)
		{
			DynamicBuffer<CityModifier> buffer = base.EntityManager.GetBuffer<CityModifier>(m_CitySystem.City, isReadOnly: true);
			m_LastCityModifiers[0] = CityUtils.GetModifier(buffer, CityModifierType.OreResourceAmount);
			m_LastCityModifiers[1] = CityUtils.GetModifier(buffer, CityModifierType.OilResourceAmount);
		}
		else
		{
			ref NativeArray<float2> reference = ref m_LastCityModifiers;
			float2 value = (m_LastCityModifiers[1] = default(float2));
			reference[0] = value;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = !m_BrushQuery.IsEmptyIgnoreFilter;
		if (!m_UpdatedAreaQuery.IsEmptyIgnoreFilter || flag || m_ObjectUpdateCollectSystem.isUpdated)
		{
			NativeQueue<Entity> updateBuffer = new NativeQueue<Entity>(Allocator.TempJob);
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			NativeQueue<Entity>.ParallelWriter updateBuffer2 = updateBuffer.AsParallelWriter();
			if (flag)
			{
				JobHandle outJobHandle;
				NativeList<Brush> list = m_BrushQuery.ToComponentDataListAsync<Brush>(Allocator.TempJob, out outJobHandle);
				JobHandle dependencies;
				JobHandle jobHandle = new FindUpdatedAreasWithBrushesJob
				{
					m_Brushes = list.AsDeferredJobArray(),
					m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
					m_WoodResourceData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_WoodResource_RO_BufferLookup, ref base.CheckedStateRef),
					m_MapFeatureElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
					m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
					m_UpdateBuffer = updateBuffer2
				}.Schedule(list, 1, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
				list.Dispose(jobHandle);
				m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
				base.Dependency = jobHandle;
			}
			if (m_ObjectUpdateCollectSystem.isUpdated)
			{
				JobHandle dependencies2;
				NativeList<Bounds2> updatedBounds = m_ObjectUpdateCollectSystem.GetUpdatedBounds(out dependencies2);
				JobHandle dependencies3;
				JobHandle jobHandle2 = new FindUpdatedAreasWithBoundsJob
				{
					m_Bounds = updatedBounds.AsDeferredJobArray(),
					m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
					m_WoodResourceData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_WoodResource_RO_BufferLookup, ref base.CheckedStateRef),
					m_MapFeatureElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
					m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
					m_UpdateBuffer = updateBuffer2
				}.Schedule(updatedBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies3));
				m_ObjectUpdateCollectSystem.AddBoundsReader(jobHandle2);
				m_AreaSearchSystem.AddSearchTreeReader(jobHandle2);
				base.Dependency = jobHandle2;
			}
			JobHandle outJobHandle2;
			NativeList<ArchetypeChunk> updatedAreaChunks = m_UpdatedAreaQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
			JobHandle outJobHandle3;
			NativeList<ArchetypeChunk> mapTileChunks = m_MapTileQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle3);
			CollectUpdatedAreasJob jobData = new CollectUpdatedAreasJob
			{
				m_UpdatedAreaChunks = updatedAreaChunks,
				m_MapTileChunks = mapTileChunks,
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_UpdateBuffer = updateBuffer,
				m_UpdateList = nativeList,
				m_LastCityModifiers = m_LastCityModifiers,
				m_City = m_CitySystem.City
			};
			JobHandle dependencies4;
			JobHandle dependencies5;
			JobHandle dependencies6;
			JobHandle deps;
			UpdateAreaResourcesJob jobData2 = new UpdateAreaResourcesJob
			{
				m_City = m_CitySystem.City,
				m_FullUpdate = true,
				m_UpdateList = nativeList.AsDeferredJobArray(),
				m_ObjectTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies4),
				m_NaturalResourceData = m_NaturalResourceSystem.GetData(readOnly: true, out dependencies5),
				m_GroundWaterResourceData = m_GroundWaterSystem.GetData(readOnly: true, out dependencies6),
				m_GeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ExtractorAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ExtractorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RW_ComponentLookup, ref base.CheckedStateRef),
				m_WoodResources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_WoodResource_RW_BufferLookup, ref base.CheckedStateRef),
				m_MapFeatureElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_MapFeatureElement_RW_BufferLookup, ref base.CheckedStateRef),
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
				m_BuildableLandMaxSlope = __query_596039173_0.GetSingleton<AreasConfigurationData>().m_BuildableLandMaxSlope
			};
			JobHandle jobHandle3 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle2, outJobHandle3));
			JobHandle jobHandle4 = jobData2.Schedule(nativeList, 1, JobUtils.CombineDependencies(jobHandle3, dependencies4, dependencies5, deps, dependencies6));
			updateBuffer.Dispose(jobHandle3);
			nativeList.Dispose(jobHandle4);
			updatedAreaChunks.Dispose(jobHandle3);
			mapTileChunks.Dispose(jobHandle3);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle4);
			m_NaturalResourceSystem.AddReader(jobHandle4);
			m_WaterSystem.AddSurfaceReader(jobHandle4);
			m_TerrainSystem.AddCPUHeightReader(jobHandle4);
			m_GroundWaterSystem.AddReader(jobHandle4);
			base.Dependency = jobHandle4;
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (!context.format.Has(FormatTags.FishResource))
		{
			using (EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<MapFeatureElement>()))
			{
				base.EntityManager.AddComponent<Updated>(entityQuery);
			}
		}
	}
```


## Nested types

- `Game.Areas.AreaResourceSystem+FindUpdatedAreasWithBrushesJob`  
- `Game.Areas.AreaResourceSystem+FindUpdatedAreasWithBoundsJob`  
- `Game.Areas.AreaResourceSystem+CollectUpdatedAreasJob`  
- `Game.Areas.AreaResourceSystem+UpdateAreaResourcesJob`  
- `Game.Areas.AreaResourceSystem+TreeIterator`  
- `Game.Areas.AreaResourceSystem+WoodIterator`  
- `Game.Areas.AreaResourceSystem+TypeHandle`  


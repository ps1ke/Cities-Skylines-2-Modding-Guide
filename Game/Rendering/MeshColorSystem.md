# Game.Rendering.MeshColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeshColorSystem : Game.GameSystemBase
{
    private System.Boolean <smoothColorsUpdated>k__BackingField;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private Unity.Entities.EntityQuery m_PlantQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.Entity m_LastSeason1;
    private Unity.Entities.Entity m_LastSeason2;
    private Unity.Entities.Entity m_OverrideEntity;
    private System.UInt32 m_LastUpdateGroup;
    private System.UInt32 m_UpdateGroupCount;
    private System.Int32 m_OverrideIndex;
    private System.Single m_LastSeasonBlend;
    private System.Boolean m_Loaded;
    private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle;

    public System.Boolean smoothColorsUpdated { get; private set; }

    public MeshColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Rendering.ColorGroupID GetColorGroupID(System.String name);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private static System.Void RandomizeAlphas(Game.Rendering.ColorSet& colorSet, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
    private static System.Void RandomizeColor(UnityEngine.Color& color, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
    public System.Void SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 variationIndex);
}
```


## Fields

- `private System.Boolean <smoothColorsUpdated>k__BackingField`  

```csharp
private System.Boolean <smoothColorsUpdated>k__BackingField;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.RenderPrefabBase m_OverridePrefab`  

```csharp
private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private Unity.Entities.EntityQuery m_PlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlantQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.Entity m_LastSeason1`  

```csharp
private Unity.Entities.Entity m_LastSeason1;
```

- `private Unity.Entities.Entity m_LastSeason2`  

```csharp
private Unity.Entities.Entity m_LastSeason2;
```

- `private Unity.Entities.Entity m_OverrideEntity`  

```csharp
private Unity.Entities.Entity m_OverrideEntity;
```

- `private System.UInt32 m_LastUpdateGroup`  

```csharp
private System.UInt32 m_LastUpdateGroup;
```

- `private System.UInt32 m_UpdateGroupCount`  

```csharp
private System.UInt32 m_UpdateGroupCount;
```

- `private System.Int32 m_OverrideIndex`  

```csharp
private System.Int32 m_OverrideIndex;
```

- `private System.Single m_LastSeasonBlend`  

```csharp
private System.Single m_LastSeasonBlend;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean smoothColorsUpdated { get; private set }`  

```csharp
public System.Boolean smoothColorsUpdated { get; private set; }
```


## Constructors

- `public MeshColorSystem()`  

```csharp
[Preserve]
	public MeshColorSystem()
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

- `public GetColorGroupID(System.String name) : Game.Rendering.ColorGroupID`  

```csharp
public ColorGroupID GetColorGroupID(string name)
	{
		int value = -1;
		if (!string.IsNullOrEmpty(name) && !m_GroupIDs.TryGetValue(name, out value))
		{
			value = m_GroupIDs.Count;
			m_GroupIDs.Add(name, value);
		}
		return new ColorGroupID(value);
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UpdateQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<MeshColor>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Common.Event>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<RentersUpdated>(),
				ComponentType.ReadOnly<ColorUpdated>()
			}
		});
		m_AllQuery = GetEntityQuery(ComponentType.ReadOnly<MeshColor>());
		m_PlantQuery = GetEntityQuery(ComponentType.ReadOnly<MeshColor>(), ComponentType.ReadOnly<Plant>(), ComponentType.ReadOnly<UpdateFrame>());
		m_BuildingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		m_GroupIDs = new Dictionary<string, int>();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = GetLoaded() && !m_AllQuery.IsEmptyIgnoreFilter;
		bool flag2 = !flag && !m_UpdateQuery.IsEmptyIgnoreFilter;
		uint num = (m_SimulationSystem.frameIndex >> 9) & 0xF;
		Entity currentClimate = m_ClimateSystem.currentClimate;
		smoothColorsUpdated = !flag && !m_PlantQuery.IsEmptyIgnoreFilter;
		if (currentClimate != Entity.Null)
		{
			ClimatePrefab prefab = m_PrefabSystem.GetPrefab<ClimatePrefab>(m_ClimateSystem.currentClimate);
			float num2 = m_ClimateSystem.currentDate;
			var (seasonInfo, num3, num4) = prefab.FindSeasonByTime(num2);
			if (num2 < num3)
			{
				num2 += 1f;
			}
			float num5 = (num3 + num4) * 0.5f;
			ClimateSystem.SeasonInfo seasonInfo2;
			float num6;
			float num7;
			if (num2 < num5)
			{
				num6 = num3 - 0.001f;
				if (num6 < 0f)
				{
					num6 += 1f;
				}
				(seasonInfo2, num6, num7) = prefab.FindSeasonByTime(num6);
				if (num6 > num3)
				{
					num5 += 1f;
					num2 += 1f;
				}
			}
			else
			{
				num7 = num4 + 0.001f;
				if (num7 >= 1f)
				{
					num7 -= 1f;
				}
				(seasonInfo2, num6, num7) = prefab.FindSeasonByTime(num7);
				if (num6 < num3)
				{
					num6 += 1f;
					num7 += 1f;
				}
			}
			float xMax = (num6 + num7) * 0.5f;
			float num8 = math.round(math.smoothstep(num5, xMax, num2) * 1600f);
			Entity entity = ((seasonInfo != null) ? m_PrefabSystem.GetEntity(seasonInfo.m_Prefab) : Entity.Null);
			Entity entity2 = ((seasonInfo2 != null) ? m_PrefabSystem.GetEntity(seasonInfo2.m_Prefab) : Entity.Null);
			if (entity != m_LastSeason1 || entity2 != m_LastSeason2 || num8 != m_LastSeasonBlend)
			{
				m_LastSeason1 = entity;
				m_LastSeason2 = entity2;
				m_LastSeasonBlend = num8;
				m_UpdateGroupCount = 16u;
			}
			if (m_UpdateGroupCount != 0 && m_LastUpdateGroup != num)
			{
				m_UpdateGroupCount--;
			}
			else
			{
				smoothColorsUpdated = false;
			}
		}
		m_LastUpdateGroup = num;
		if (flag || flag2 || smoothColorsUpdated)
		{
			NativeList<Entity> list;
			JobHandle outJobHandle;
			if (flag)
			{
				list = m_AllQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
			}
			else if (smoothColorsUpdated)
			{
				m_PlantQuery.ResetFilter();
				m_PlantQuery.SetSharedComponentFilter(new UpdateFrame
				{
					m_Index = num
				});
				list = m_PlantQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
			}
			else
			{
				list = new NativeList<Entity>(Allocator.TempJob);
				outJobHandle = default(JobHandle);
			}
			if (flag2)
			{
				NativeQueue<Entity> queue = new NativeQueue<Entity>(Allocator.TempJob);
				FindUpdatedMeshColorsJob jobData = new FindUpdatedMeshColorsJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_RentersUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RentersUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ColorUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_ColorUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_MeshColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RO_BufferLookup, ref base.CheckedStateRef),
					m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
					m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
					m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_Queue = queue.AsParallelWriter()
				};
				JobHandle jobHandle = IJobExtensions.Schedule(new ListUpdatedMeshColorsJob
				{
					m_Queue = queue,
					m_List = list
				}, JobHandle.CombineDependencies(job1: JobChunkExtensions.ScheduleParallel(jobData, m_UpdateQuery, base.Dependency), job0: outJobHandle));
				outJobHandle = jobHandle;
				queue.Dispose(jobHandle);
			}
			else
			{
				outJobHandle = JobHandle.CombineDependencies(outJobHandle, base.Dependency);
			}
			Entity entity3 = Entity.Null;
			if (m_OverridePrefab != null)
			{
				m_PrefabSystem.TryGetEntity(m_OverridePrefab, out entity3);
			}
			NativeQueue<CopyColorData> copyColors = new NativeQueue<CopyColorData>(Allocator.TempJob);
			SetMeshColorsJob jobData2 = new SetMeshColorsJob
			{
				m_RandomSeed = RandomSeed.Next(),
				m_DefaultBrand = m_BuildingSettingsQuery.GetSingleton<BuildingConfigurationData>().m_DefaultRenterBrand,
				m_Season1 = m_LastSeason1,
				m_Season2 = m_LastSeason2,
				m_SeasonBlend = m_LastSeasonBlend,
				m_OverrideEntity = m_OverrideEntity,
				m_OverrideMesh = entity3,
				m_OverrideIndex = m_OverrideIndex,
				m_Stage = (flag ? UpdateStage.IgnoreSubs : UpdateStage.Default),
				m_Entities = list.AsDeferredJobArray(),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Color_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompanyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BrandData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BrandData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CreatureData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResidentData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
				m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
				m_ColorVariations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ColorVariation_RO_BufferLookup, ref base.CheckedStateRef),
				m_ColorFilters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ColorFilter_RO_BufferLookup, ref base.CheckedStateRef),
				m_OverlayElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_OverlayElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_MeshColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RW_BufferLookup, ref base.CheckedStateRef),
				m_CopyColors = copyColors.AsParallelWriter()
			};
			CopyMeshColorsJob jobData3 = new CopyMeshColorsJob
			{
				m_MeshColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RW_BufferLookup, ref base.CheckedStateRef),
				m_CopyColors = copyColors
			};
			JobHandle jobHandle2 = jobData2.Schedule(list, 4, outJobHandle);
			if (flag)
			{
				jobData2.m_Stage = UpdateStage.IgnoreOwners;
				jobHandle2 = jobData2.Schedule(list, 4, jobHandle2);
			}
			JobHandle jobHandle3 = IJobExtensions.Schedule(jobData3, jobHandle2);
			list.Dispose(jobHandle2);
			copyColors.Dispose(jobHandle3);
			base.Dependency = jobHandle3;
		}
	}
```

- `private static RandomizeAlphas(Game.Rendering.ColorSet& colorSet, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max) : System.Void`  

```csharp
private static void RandomizeAlphas(ref ColorSet colorSet, ref Unity.Mathematics.Random random, float3 min, float3 max)
	{
		float3 @float = new float3(colorSet.m_Channel0.a, colorSet.m_Channel1.a, colorSet.m_Channel2.a);
		float3 float2 = random.NextFloat3(min, max);
		@float = math.saturate(@float + float2);
		colorSet.m_Channel0.a = @float.x;
		colorSet.m_Channel1.a = @float.y;
		colorSet.m_Channel2.a = @float.z;
	}
```

- `private static RandomizeColor(UnityEngine.Color& color, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max) : System.Void`  

```csharp
private static void RandomizeColor(ref UnityEngine.Color color, ref Unity.Mathematics.Random random, float3 min, float3 max)
	{
		float3 @float = default(float3);
		UnityEngine.Color.RGBToHSV(color, out @float.x, out @float.y, out @float.z);
		float a = color.a;
		float3 float2 = random.NextFloat3(min, max);
		@float.x = math.frac(@float.x + float2.x);
		@float.yz = math.saturate(@float.yz * float2.yz);
		color = UnityEngine.Color.HSVToRGB(@float.x, @float.y, @float.z);
		color.a = a;
	}
```

- `public SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 variationIndex) : System.Void`  

```csharp
public void SetOverride(Entity entity, RenderPrefabBase prefab, int variationIndex)
	{
		if (m_OverrideEntity != entity && m_OverrideEntity != Entity.Null && base.EntityManager.Exists(m_OverrideEntity) && !base.EntityManager.HasComponent<Deleted>(m_OverrideEntity))
		{
			base.World.GetExistingSystemManaged<EndFrameBarrier>().CreateCommandBuffer().AddComponent<BatchesUpdated>(m_OverrideEntity);
		}
		m_OverrideEntity = entity;
		m_OverridePrefab = prefab;
		m_OverrideIndex = variationIndex;
	}
```


## Nested types

- `Game.Rendering.MeshColorSystem+FindUpdatedMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+ListUpdatedMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+CopyColorData`  
- `Game.Rendering.MeshColorSystem+UpdateStage`  
- `Game.Rendering.MeshColorSystem+SetMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+CopyMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+TypeHandle`  


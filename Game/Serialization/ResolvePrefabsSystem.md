# Game.Serialization.ResolvePrefabsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResolvePrefabsSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Unity.Entities.EntityQuery m_ActualPrefabQuery;
    private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery;
    private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery;
    private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery;
    private Unity.Entities.EntityQuery m_LoadedZoneCellQuery;
    private Unity.Entities.EntityQuery m_ActualBudgetQuery;
    private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle;

    public ResolvePrefabsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddOrRemoveComponent(Game.Serialization.ResolvePrefabsSystem+ComponentModification componentModification, Game.Prefabs.PrefabComponents mask, Unity.Entities.ComponentType type);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Unity.Entities.EntityQuery m_ActualPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActualPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedZoneCellQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedZoneCellQuery;
```

- `private Unity.Entities.EntityQuery m_ActualBudgetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActualBudgetQuery;
```

- `private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResolvePrefabsSystem()`  

```csharp
[Preserve]
	public ResolvePrefabsSystem()
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

- `private AddOrRemoveComponent(Game.Serialization.ResolvePrefabsSystem+ComponentModification componentModification, Game.Prefabs.PrefabComponents mask, Unity.Entities.ComponentType type) : System.Void`  

```csharp
private void AddOrRemoveComponent(ComponentModification componentModification, PrefabComponents mask, ComponentType type)
	{
		if ((componentModification.m_Remove & mask) != 0)
		{
			base.EntityManager.RemoveComponent(componentModification.m_Entity, type);
		}
		else if ((componentModification.m_Add & mask) != 0)
		{
			base.EntityManager.AddComponent(componentModification.m_Entity, type);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_CheckPrefabReferencesSystem = base.World.GetOrCreateSystemManaged<CheckPrefabReferencesSystem>();
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		entityQueryBuilder = entityQueryBuilder.WithAll<PrefabData, LoadedIndex>();
		entityQueryBuilder = entityQueryBuilder.WithOptions(EntityQueryOptions.IgnoreComponentEnabledState);
		m_ActualPrefabQuery = entityQueryBuilder.Build(this);
		m_EnabledLoadedPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<LoadedIndex>());
		entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		entityQueryBuilder = entityQueryBuilder.WithAll<PrefabData>();
		entityQueryBuilder = entityQueryBuilder.WithNone<LoadedIndex>();
		entityQueryBuilder = entityQueryBuilder.WithOptions(EntityQueryOptions.IgnoreComponentEnabledState);
		m_AllLoadedPrefabQuery = entityQueryBuilder.Build(this);
		m_LoadedZonePrefabQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<ZoneData>(), ComponentType.Exclude<LoadedIndex>());
		m_LoadedZoneCellQuery = GetEntityQuery(ComponentType.ReadOnly<Cell>());
		m_ActualBudgetQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<LoadedIndex>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<CollectedCityServiceBudgetData>(),
				ComponentType.ReadOnly<CollectedCityServiceFeeData>(),
				ComponentType.ReadOnly<CollectedCityServiceUpkeepData>()
			}
		});
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
		int length = m_EnabledLoadedPrefabQuery.CalculateEntityCount();
		NativeArray<Entity> nativeArray = new NativeArray<Entity>(length, Allocator.TempJob);
		NativeArray<PrefabComponents> prefabComponents = new NativeArray<PrefabComponents>(length, Allocator.TempJob);
		NativeArray<ZoneType> zoneTypeArray = new NativeArray<ZoneType>(340, Allocator.TempJob);
		NativeQueue<ComponentModification> nativeQueue = new NativeQueue<ComponentModification>(Allocator.TempJob);
		FillLoadedPrefabsJob jobData = new FillLoadedPrefabsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LockedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PlacedSignatureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlacedSignatureBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabArray = nativeArray,
			m_PrefabComponents = prefabComponents
		};
		CheckActualPrefabsJob jobData2 = new CheckActualPrefabsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SignatureBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PlacedSignatureBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlacedSignatureBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LoadedIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LoadedIndex_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Context = m_LoadGameSystem.context,
			m_PrefabComponents = prefabComponents,
			m_LockedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabArray = nativeArray,
			m_ComponentModifications = nativeQueue.AsParallelWriter()
		};
		CopyBudgetDataJob jobData3 = new CopyBudgetDataJob
		{
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LoadedIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LoadedIndex_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabArray = nativeArray,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_Budgets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceBudgetData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Fees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceFeeData_RW_BufferLookup, ref base.CheckedStateRef),
			m_Upkeeps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceUpkeepData_RW_BufferLookup, ref base.CheckedStateRef)
		};
		FillZoneTypeArrayJob jobData4 = new FillZoneTypeArrayJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabArray = nativeArray,
			m_ZoneTypeArray = zoneTypeArray
		};
		FixZoneTypeJob jobData5 = new FixZoneTypeJob
		{
			m_ZoneTypeArray = zoneTypeArray,
			m_CellType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_Cell_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_VacantLotType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_VacantLot_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, m_EnabledLoadedPrefabQuery, base.Dependency);
		JobHandle.ScheduleBatchedJobs();
		m_PrefabSystem.UpdateLoadedIndices();
		JobHandle dependsOn2 = JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(jobData3, m_ActualBudgetQuery, dependsOn), jobData: jobData2, query: m_ActualPrefabQuery), jobData: jobData4, query: m_LoadedZonePrefabQuery);
		JobHandle dependencies = JobChunkExtensions.ScheduleParallel(jobData5, m_LoadedZoneCellQuery, dependsOn2);
		dependsOn2.Complete();
		base.EntityManager.SetComponentEnabled<PrefabData>(m_ActualPrefabQuery, value: false);
		base.EntityManager.SetComponentEnabled<PrefabData>(m_EnabledLoadedPrefabQuery, value: false);
		m_CheckPrefabReferencesSystem.BeginPrefabCheck(nativeArray, isLoading: true, dependencies);
		m_UpdateSystem.Update(SystemUpdatePhase.PrefabReferences);
		m_CheckPrefabReferencesSystem.EndPrefabCheck(out var dependencies2);
		dependencies2.Complete();
		base.EntityManager.SetComponentEnabled<PrefabData>(m_ActualPrefabQuery, value: true);
		NativeArray<Entity> entities = m_EnabledLoadedPrefabQuery.ToEntityArray(Allocator.TempJob);
		ComponentType type = ComponentType.ReadWrite<PlacedSignatureBuildingData>();
		ComponentModification item;
		while (nativeQueue.TryDequeue(out item))
		{
			AddOrRemoveComponent(item, PrefabComponents.PlacedSignatureBuilding, type);
		}
		if (entities.Length != 0)
		{
			base.EntityManager.AddComponent<LoadedIndex>(entities);
			for (int i = 0; i < entities.Length; i++)
			{
				Entity entity = entities[i];
				PrefabData componentData = base.EntityManager.GetComponentData<PrefabData>(entity);
				PrefabID loadedObsoleteID = m_PrefabSystem.GetLoadedObsoleteID(componentData.m_Index);
				componentData.m_Index = -1 - i;
				base.EntityManager.SetComponentData(entity, componentData);
				base.EntityManager.SetComponentEnabled<PrefabData>(entity, value: false);
				m_PrefabSystem.AddObsoleteID(entity, loadedObsoleteID);
			}
		}
		base.EntityManager.DestroyEntity(m_AllLoadedPrefabQuery);
		nativeArray.Dispose();
		prefabComponents.Dispose();
		zoneTypeArray.Dispose();
		nativeQueue.Dispose();
		entities.Dispose();
	}
```


## Nested types

- `Game.Serialization.ResolvePrefabsSystem+ComponentModification`  
- `Game.Serialization.ResolvePrefabsSystem+FillLoadedPrefabsJob`  
- `Game.Serialization.ResolvePrefabsSystem+CheckActualPrefabsJob`  
- `Game.Serialization.ResolvePrefabsSystem+CopyBudgetDataJob`  
- `Game.Serialization.ResolvePrefabsSystem+FillZoneTypeArrayJob`  
- `Game.Serialization.ResolvePrefabsSystem+FixZoneTypeJob`  
- `Game.Serialization.ResolvePrefabsSystem+TypeHandle`  


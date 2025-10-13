# Game.Serialization.BeginPrefabSerializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BeginPrefabSerializationSystem : Game.GameSystemBase
{
    private Game.Serialization.SaveGameSystem m_SaveGameSystem;
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Unity.Entities.EntityQuery m_EnabledPrefabsQuery;
    private Unity.Entities.EntityQuery m_LoadedPrefabsQuery;
    private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle;

    public BeginPrefabSerializationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SaveGameSystem;
```

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Unity.Entities.EntityQuery m_EnabledPrefabsQuery`  

```csharp
private Unity.Entities.EntityQuery m_EnabledPrefabsQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedPrefabsQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedPrefabsQuery;
```

- `private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.BeginPrefabSerializationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BeginPrefabSerializationSystem()`  

```csharp
[Preserve]
	public BeginPrefabSerializationSystem()
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
		m_SaveGameSystem = base.World.GetOrCreateSystemManaged<SaveGameSystem>();
		m_CheckPrefabReferencesSystem = base.World.GetOrCreateSystemManaged<CheckPrefabReferencesSystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_EnabledPrefabsQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>());
		m_LoadedPrefabsQuery = GetEntityQuery(ComponentType.ReadOnly<LoadedIndex>());
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
		int length = m_LoadedPrefabsQuery.CalculateEntityCountWithoutFiltering();
		NativeArray<Entity> nativeArray = new NativeArray<Entity>(length, Allocator.TempJob);
		JobHandle dependencies = JobChunkExtensions.ScheduleParallel(new BeginPrefabSerializationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabArray = nativeArray
		}, m_LoadedPrefabsQuery, base.Dependency);
		m_CheckPrefabReferencesSystem.BeginPrefabCheck(nativeArray, isLoading: false, dependencies);
		m_UpdateSystem.Update(SystemUpdatePhase.PrefabReferences);
		if (m_SaveGameSystem.context.purpose == Purpose.SaveGame)
		{
			JobHandle dependencies3;
			JobHandle dependencies2 = JobChunkExtensions.ScheduleParallel(new CheckSavedPrefabsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_LockedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SignatureBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlacedSignatureBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlacedSignatureBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CollectedCityServiceBudgetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedCityServiceBudgetData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CollectedCityServiceFeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedCityServiceFeeData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_CollectedCityServiceUpkeepType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedCityServiceUpkeepData_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabReferences = m_CheckPrefabReferencesSystem.GetPrefabReferences(this, out dependencies3)
			}, m_LoadedPrefabsQuery, dependencies3);
			m_CheckPrefabReferencesSystem.AddPrefabReferencesUser(dependencies2);
			m_CheckPrefabReferencesSystem.Update();
		}
		m_CheckPrefabReferencesSystem.EndPrefabCheck(out var dependencies4);
		nativeArray.Dispose(dependencies4);
		dependencies4.Complete();
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> prefabChunks = m_EnabledPrefabsQuery.ToArchetypeChunkListAsync(Allocator.TempJob, dependencies4, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new SetPrefabDataIndexJob
		{
			m_PrefabChunks = prefabChunks,
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LoadedIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LoadedIndex_RW_BufferTypeHandle, ref base.CheckedStateRef)
		}, outJobHandle);
		prefabChunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Serialization.BeginPrefabSerializationSystem+BeginPrefabSerializationJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+CheckSavedPrefabsJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+SetPrefabDataIndexJob`  
- `Game.Serialization.BeginPrefabSerializationSystem+TypeHandle`  


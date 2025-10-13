# Game.Prefabs.ZoneBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneBuiltRequirementSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery;
    private Unity.Entities.EntityQuery m_AllBuildingsQuery;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData;
    private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue;
    private Unity.Jobs.JobHandle m_WriteDeps;
    private Unity.Jobs.JobHandle m_QueueWriteDeps;
    private System.Boolean m_Loaded;
    private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle;

    public ZoneBuiltRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Boolean GetLoaded();
    public Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> GetZoneBuiltLevelQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_AllBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData`  

```csharp
private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData;
```

- `private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue;
```

- `private Unity.Jobs.JobHandle m_WriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_WriteDeps;
```

- `private Unity.Jobs.JobHandle m_QueueWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_QueueWriteDeps;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneBuiltRequirementSystem()`  

```csharp
[Preserve]
	public ZoneBuiltRequirementSystem()
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

- `public AddWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddWriter(JobHandle jobHandle)
	{
		m_QueueWriteDeps = JobHandle.CombineDependencies(jobHandle, m_QueueWriteDeps);
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

- `public GetZoneBuiltLevelQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate>`  

```csharp
public NativeQueue<ZoneBuiltLevelUpdate> GetZoneBuiltLevelQueue(out JobHandle deps)
	{
		deps = m_QueueWriteDeps;
		return m_ZoneBuiltLevelQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_UpdatedBuildingsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Building>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllBuildingsQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Temp>());
		m_RequirementQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneBuiltRequirementData>(), ComponentType.ReadWrite<UnlockRequirementData>(), ComponentType.ReadOnly<Locked>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		m_ZoneBuiltData = new NativeParallelHashMap<ZoneBuiltDataKey, ZoneBuiltDataValue>(20, Allocator.Persistent);
		m_ZoneBuiltLevelQueue = new NativeQueue<ZoneBuiltLevelUpdate>(Allocator.Persistent);
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
		m_ZoneBuiltData.Dispose();
		m_ZoneBuiltLevelQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery entityQuery = (GetLoaded() ? m_AllBuildingsQuery : m_UpdatedBuildingsQuery);
		if (!entityQuery.IsEmptyIgnoreFilter || !m_ZoneBuiltLevelQueue.IsEmpty())
		{
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> buildingChunks = entityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle jobHandle = IJobExtensions.Schedule(new UpdateZoneBuiltDataJob
			{
				m_BuildingChunks = buildingChunks,
				m_ZoneBuiltData = m_ZoneBuiltData,
				m_ZoneBuiltLevelQueue = m_ZoneBuiltLevelQueue,
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef)
			}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, m_QueueWriteDeps));
			buildingChunks.Dispose(jobHandle);
			m_WriteDeps = jobHandle;
			if (!m_RequirementQuery.IsEmptyIgnoreFilter)
			{
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new ZoneBuiltRequirementJob
				{
					m_ZoneBuiltData = m_ZoneBuiltData,
					m_UnlockEventArchetype = m_UnlockEventArchetype,
					m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_ZoneBuiltRequirementType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ZoneBuiltRequirementData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_UnlockRequirementType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UnlockRequirementData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ThemeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ThemeData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ObjectRequirementElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ObjectRequirementElement_RO_BufferLookup, ref base.CheckedStateRef)
				}, m_RequirementQuery, jobHandle);
				m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
				base.Dependency = jobHandle2;
			}
			else
			{
				base.Dependency = jobHandle;
			}
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_WriteDeps.Complete();
		m_ZoneBuiltData.Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Prefabs.ZoneBuiltRequirementSystem+ZoneBuiltData`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+UpdateZoneBuiltDataJob`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+ZoneBuiltRequirementJob`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle`  


# Game.Simulation.CreatureSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CreatureSpawnSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
    private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle;

    public CreatureSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
```

- `private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CreatureSpawnSystem()`  

```csharp
[Preserve]
	public CreatureSpawnSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CreatureQuery = GetEntityQuery(ComponentType.ReadWrite<TripSource>(), ComponentType.ReadOnly<Creature>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CreatureQuery);
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
		NativeList<SpawnData> spawnData = new NativeList<SpawnData>(Allocator.TempJob);
		NativeList<SpawnRange> nativeList = new NativeList<SpawnRange>(Allocator.TempJob);
		JobHandle outJobHandle;
		GroupSpawnSourcesJob jobData = new GroupSpawnSourcesJob
		{
			m_Chunks = m_CreatureQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TripSourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_TripSource_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnData = spawnData,
			m_SpawnGroups = nativeList
		};
		JobHandle jobHandle = new TrySpawnCreaturesJob
		{
			m_SpawnData = spawnData.AsDeferredJobArray(),
			m_SpawnGroups = nativeList.AsDeferredJobArray(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Patients = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Patient_RW_BufferLookup, ref base.CheckedStateRef),
			m_Occupants = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Occupant_RW_BufferLookup, ref base.CheckedStateRef)
		}.Schedule(dependsOn: IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle)), list: nativeList, innerloopBatchCount: 1);
		spawnData.Dispose(jobHandle);
		nativeList.Dispose(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.CreatureSpawnSystem+SpawnData`  
- `Game.Simulation.CreatureSpawnSystem+SpawnRange`  
- `Game.Simulation.CreatureSpawnSystem+GroupSpawnSourcesJob`  
- `Game.Simulation.CreatureSpawnSystem+TrySpawnCreaturesJob`  
- `Game.Simulation.CreatureSpawnSystem+TypeHandle`  


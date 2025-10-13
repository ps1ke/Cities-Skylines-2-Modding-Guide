# Game.Simulation.HouseholdPetSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdPetSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPetQuery;
    private Unity.Entities.EntityQuery m_AnimalPrefabQuery;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.HouseholdPetSpawnSystem+TypeHandle __TypeHandle;

    public HouseholdPetSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPetQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPetQuery;
```

- `private Unity.Entities.EntityQuery m_AnimalPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimalPrefabQuery;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.HouseholdPetSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdPetSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdPetSpawnSystem()`  

```csharp
[Preserve]
	public HouseholdPetSpawnSystem()
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
		m_HouseholdPetQuery = GetEntityQuery(ComponentType.ReadOnly<HouseholdPet>(), ComponentType.ReadOnly<Target>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_AnimalPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<AnimalData>(), ComponentType.ReadOnly<PetData>());
		m_ResetTripArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<ResetTrip>());
		RequireForUpdate(m_HouseholdPetQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> animalPrefabChunks = m_AnimalPrefabQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new HouseholdPetSpawnJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurrentTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PetDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PetData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdPetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HouseholdPetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalPrefabChunks = animalPrefabChunks,
			m_RandomSeed = RandomSeed.Next(),
			m_ResetTripArchetype = m_ResetTripArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_HouseholdPetQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		animalPrefabChunks.Dispose(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.HouseholdPetSpawnSystem+HouseholdPetSpawnJob`  
- `Game.Simulation.HouseholdPetSpawnSystem+TypeHandle`  


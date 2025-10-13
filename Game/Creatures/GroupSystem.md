# Game.Creatures.GroupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroupSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Game.Creatures.GroupSystem+TypeHandle __TypeHandle;

    public GroupSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Game.Creatures.GroupSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Creatures.GroupSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GroupSystem()`  

```csharp
[Preserve]
	public GroupSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_CreatureQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Creature>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<ResetTrip>() }
		});
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
		NativeParallelHashSet<Entity> resetTripSet = new NativeParallelHashSet<Entity>(100, Allocator.TempJob);
		NativeQueue<GroupData> groupQueue = new NativeQueue<GroupData>(Allocator.TempJob);
		ResetTripSetJob jobData = new ResetTripSetJob
		{
			m_ResetTripType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_ResetTrip_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResetTripSet = resetTripSet
		};
		FillGroupQueueJob jobData2 = new FillGroupQueueJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TripSourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_TripSource_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Pet_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WildlifeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Wildlife_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DomesticatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Domesticated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResetTripType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_ResetTrip_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroupMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroupCreatureType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Creatures_GroupCreature_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TripSourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_TripSource_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMemberData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdPetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdPet_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroupMemberData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Pet_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WildlifeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Wildlife_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DomesticatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Domesticated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroupCreatures = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Creatures_GroupCreature_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdAnimals = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RO_BufferLookup, ref base.CheckedStateRef),
			m_OwnedCreatures = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Creatures_OwnedCreature_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResetTripSet = resetTripSet,
			m_GroupQueue = groupQueue.AsParallelWriter()
		};
		GroupCreaturesJob jobData3 = new GroupCreaturesJob
		{
			m_HumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarKeeperData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroupMemberData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_GroupMember_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PathOwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentLookup, ref base.CheckedStateRef),
			m_GroupCreatures = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Creatures_GroupCreature_RW_BufferLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_ResetTripSet = resetTripSet,
			m_GroupQueue = groupQueue,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		};
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.Schedule(jobData, m_CreatureQuery, base.Dependency), jobData: jobData2, query: m_CreatureQuery);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData3, dependsOn);
		resetTripSet.Dispose(jobHandle);
		groupQueue.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Creatures.GroupSystem+GroupData`  
- `Game.Creatures.GroupSystem+ResetTripSetJob`  
- `Game.Creatures.GroupSystem+FillGroupQueueJob`  
- `Game.Creatures.GroupSystem+GroupCreaturesJob`  
- `Game.Creatures.GroupSystem+TypeHandle`  


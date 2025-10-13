# Game.Citizens.HouseholdAndCitizenRemoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdAndCitizenRemoveSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle __TypeHandle;

    public HouseholdAndCitizenRemoveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdAndCitizenRemoveSystem()`  

```csharp
[Preserve]
	public HouseholdAndCitizenRemoveSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_DeletedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Household>(),
				ComponentType.ReadOnly<Citizen>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_RentEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<RentersUpdated>());
		RequireForUpdate(m_DeletedQuery);
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
		JobHandle jobHandle = JobChunkExtensions.Schedule(new HouseholdAndCitizenRemoveJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdPets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdPet_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HasSchoolSeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HasSchoolSeeker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HasJobSeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_HasJobSeeker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Vehicles = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentTransports = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Creatures = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Deleteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SchoolStudents = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Student_RW_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RW_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdAnimals = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RW_BufferLookup, ref base.CheckedStateRef),
			m_Patients = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Patient_RW_BufferLookup, ref base.CheckedStateRef),
			m_Occupants = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Occupant_RW_BufferLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferLookup, ref base.CheckedStateRef),
			m_RentEventArchetype = m_RentEventArchetype,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, m_DeletedQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Citizens.HouseholdAndCitizenRemoveSystem+HouseholdAndCitizenRemoveJob`  
- `Game.Citizens.HouseholdAndCitizenRemoveSystem+TypeHandle`  


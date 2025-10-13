# Game.Creatures.TripResetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TripResetSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ResetQuery;
    private Game.Creatures.TripResetSystem+TypeHandle __TypeHandle;

    public TripResetSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ResetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResetQuery;
```

- `private Game.Creatures.TripResetSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Creatures.TripResetSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TripResetSystem()`  

```csharp
[Preserve]
	public TripResetSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_ResetQuery = GetEntityQuery(ComponentType.ReadOnly<ResetTrip>());
		RequireForUpdate(m_ResetQuery);
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
		CreatureTripResetJob jobData = new CreatureTripResetJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ResetTripType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_ResetTrip_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Deleted = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TravelPurpose = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TripNeeded = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_TripNeeded_RO_BufferLookup, ref base.CheckedStateRef),
			m_GroupCreatures = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Creatures_GroupCreature_RO_BufferLookup, ref base.CheckedStateRef),
			m_HumanCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Resident = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Pet = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Pet_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Target = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Divert = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Divert_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PathOwner = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_ResetQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Creatures.TripResetSystem+CreatureTripResetJob`  
- `Game.Creatures.TripResetSystem+TypeHandle`  


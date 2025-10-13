# Game.Simulation.ResidentPurposeCounterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `DebugWatchOnly`, `CompilerGenerated`  

## Code

```csharp
public class ResidentPurposeCounterSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.Simulation.ResidentPurposeCounterSystem+TypeHandle __TypeHandle;

    public ResidentPurposeCounterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.Simulation.ResidentPurposeCounterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResidentPurposeCounterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResidentPurposeCounterSystem()`  

```csharp
[Preserve]
	public ResidentPurposeCounterSystem()
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
		return 256;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CreatureQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Creatures.Resident>(), ComponentType.ReadOnly<Human>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<PathOwner>(), ComponentType.ReadOnly<Target>(), ComponentType.Exclude<Unspawned>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Stumbling>());
		m_Results = new NativeArray<int>(12, Allocator.Persistent);
		base.Enabled = false;
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
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		PurposeCountJob jobData = new PurposeCountJob
		{
			m_Chunks = m_CreatureQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ResidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_DivertType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Divert_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TravelPurposeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
	}
```


## Nested types

- `Game.Simulation.ResidentPurposeCounterSystem+CountPurpose`  
- `Game.Simulation.ResidentPurposeCounterSystem+PurposeCountJob`  
- `Game.Simulation.ResidentPurposeCounterSystem+TypeHandle`  


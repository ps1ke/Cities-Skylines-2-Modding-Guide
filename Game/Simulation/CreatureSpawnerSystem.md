# Game.Simulation.CreatureSpawnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CreatureSpawnerSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_SpawnerQuery;
    private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
    private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle;

    public CreatureSpawnerSystem();

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

- `private Unity.Entities.EntityQuery m_SpawnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnerQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
```

- `private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CreatureSpawnerSystem()`  

```csharp
[Preserve]
	public CreatureSpawnerSystem()
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
		return 512;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SpawnerQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Creatures.CreatureSpawner>(), ComponentType.ReadWrite<OwnedCreature>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_AnimalSpawnTypes = new ComponentTypeSet(ComponentType.ReadWrite<AnimalCurrentLane>(), ComponentType.ReadWrite<Owner>(), ComponentType.ReadWrite<TripSource>(), ComponentType.ReadWrite<Unspawned>());
		RequireForUpdate(m_SpawnerQuery);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new CreatureSpawnerJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnedCreatureType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Creatures_OwnedCreature_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroupMemberData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DomesticatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Domesticated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCreatureSpawnData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CreatureSpawnData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAnimalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AnimalData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWildlifeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WildlifeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDomesticatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DomesticatedData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceholderObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_AnimalSpawnTypes = m_AnimalSpawnTypes,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_SpawnerQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.CreatureSpawnerSystem+CreatureSpawnerJob`  
- `Game.Simulation.CreatureSpawnerSystem+TypeHandle`  


# Game.Simulation.DomesticatedAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DomesticatedAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Entities.EntityQuery m_GroupCreatureQuery;
    private Game.Simulation.DomesticatedAISystem+TypeHandle __TypeHandle;

    public DomesticatedAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Entities.EntityQuery m_GroupCreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_GroupCreatureQuery;
```

- `private Game.Simulation.DomesticatedAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DomesticatedAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DomesticatedAISystem()`  

```csharp
[Preserve]
	public DomesticatedAISystem()
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 9;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_CreatureQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Creatures.Domesticated>(), ComponentType.ReadWrite<Animal>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<GroupMember>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Stumbling>());
		m_GroupCreatureQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Creatures.Domesticated>(), ComponentType.ReadWrite<Animal>(), ComponentType.ReadOnly<GroupMember>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Stumbling>());
		RequireAnyForUpdate(m_CreatureQuery, m_GroupCreatureQuery);
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
		JobHandle deps;
		DomesticatedTickJob jobData = new DomesticatedTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Animal_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DomesticatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Domesticated_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NavigationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalNavigation_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAnimalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AnimalData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDomesticatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DomesticatedData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		DomesticatedGroupTickJob jobData2 = new DomesticatedGroupTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroupMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_GroupMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Animal_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = jobData.m_CommandBuffer
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_CreatureQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData2, m_GroupCreatureQuery, jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.DomesticatedAISystem+DomesticatedGroupTickJob`  
- `Game.Simulation.DomesticatedAISystem+DomesticatedTickJob`  
- `Game.Simulation.DomesticatedAISystem+TypeHandle`  


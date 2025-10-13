# Game.Simulation.FloodCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FloodCheckSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_TargetQuery;
    private Unity.Entities.EntityQuery m_WaterLevelChangeQuery;
    private Unity.Entities.EntityArchetype m_SubmergeArchetype;
    private Game.Simulation.FloodCheckSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public FloodCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_TargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_TargetQuery;
```

- `private Unity.Entities.EntityQuery m_WaterLevelChangeQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterLevelChangeQuery;
```

- `private Unity.Entities.EntityArchetype m_SubmergeArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_SubmergeArchetype;
```

- `private Game.Simulation.FloodCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FloodCheckSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public FloodCheckSystem()`  

```csharp
[Preserve]
	public FloodCheckSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TargetQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Placeholder>(), ComponentType.Exclude<Flooded>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_WaterLevelChangeQuery = GetEntityQuery(ComponentType.ReadOnly<WaterLevelChange>(), ComponentType.ReadOnly<Duration>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_SubmergeArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Submerge>());
		RequireForUpdate(m_TargetQuery);
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
		uint updateFrameIndex = (m_SimulationSystem.frameIndex >> 4) & 0xF;
		JobHandle deps;
		JobHandle outJobHandle;
		FloodCheckJob jobData = new FloodCheckJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterLevelChangeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_WaterLevelChange_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DurationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Duration_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InDangerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InDanger_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterLevelChangeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_WaterLevelChange_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWaterLevelChangeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterLevelChangeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefaObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefaPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdateFrameIndex = updateFrameIndex,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_WaterLevelChangeChunks = m_WaterLevelChangeQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_SubmergeArchetype = m_SubmergeArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TargetQuery, JobHandle.CombineDependencies(base.Dependency, deps, outJobHandle));
		m_TerrainSystem.AddCPUHeightReader(base.Dependency);
		m_WaterSystem.AddSurfaceReader(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.FloodCheckSystem+FloodCheckJob`  
- `Game.Simulation.FloodCheckSystem+TypeHandle`  


# Game.Events.EndangerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EndangerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_EndangerQuery;
    private Game.Events.EndangerSystem+TypeHandle __TypeHandle;

    public EndangerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_EndangerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EndangerQuery;
```

- `private Game.Events.EndangerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.EndangerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EndangerSystem()`  

```csharp
[Preserve]
	public EndangerSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_EndangerQuery = GetEntityQuery(ComponentType.ReadOnly<Endanger>(), ComponentType.ReadOnly<Game.Common.Event>());
		RequireForUpdate(m_EndangerQuery);
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
		NativeList<ArchetypeChunk> chunks = m_EndangerQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new EndangerJob
		{
			m_Chunks = chunks,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_EndangerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Endanger_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SchoolData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_School_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HospitalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Hospital_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InDangerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InDanger_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Events.EndangerSystem+EndangerJob`  
- `Game.Events.EndangerSystem+TypeHandle`  


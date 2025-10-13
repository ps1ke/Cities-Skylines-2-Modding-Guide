# Game.Simulation.InDangerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InDangerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_InDangerQuery;
    private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype;
    private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 UPDATE_INTERVAL;

    public InDangerSystem();

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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_InDangerQuery`  

```csharp
private Unity.Entities.EntityQuery m_InDangerQuery;
```

- `private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype;
```

- `private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public InDangerSystem()`  

```csharp
[Preserve]
	public InDangerSystem()
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
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_InDangerQuery = GetEntityQuery(ComponentType.ReadWrite<InDanger>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EvacuationRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<EvacuationRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireForUpdate(m_InDangerQuery);
		Assert.IsTrue(condition: true);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new InDangerJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_InDangerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_InDanger_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DurationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_Duration_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EvacuationRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_EvacuationRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_EvacuationRequestArchetype = m_EvacuationRequestArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_InDangerQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.InDangerSystem+InDangerJob`  
- `Game.Simulation.InDangerSystem+TypeHandle`  


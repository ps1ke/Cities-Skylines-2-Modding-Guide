# Game.Prefabs.ProcessingRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProcessingRequirementSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle;

    public ProcessingRequirementSystem();

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

- `private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem`  

```csharp
private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ProcessingRequirementSystem()`  

```csharp
[Preserve]
	public ProcessingRequirementSystem()
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
		return 128;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ProcessingCompanySystem = base.World.GetOrCreateSystemManaged<ProcessingCompanySystem>();
		m_RequirementQuery = GetEntityQuery(ComponentType.ReadOnly<ProcessingRequirementData>(), ComponentType.ReadWrite<UnlockRequirementData>(), ComponentType.ReadOnly<Locked>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		RequireForUpdate(m_RequirementQuery);
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
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new ProcessingRequirementJob
		{
			m_ProducedResources = m_ProcessingCompanySystem.GetProducedResourcesArray(out dependencies),
			m_UnlockEventArchetype = m_UnlockEventArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ProcessingRequirementType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ProcessingRequirementData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnlockRequirementType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UnlockRequirementData_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		}, m_RequirementQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_ProcessingCompanySystem.AddProducedResourcesReader(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Prefabs.ProcessingRequirementSystem+ProcessingRequirementJob`  
- `Game.Prefabs.ProcessingRequirementSystem+TypeHandle`  


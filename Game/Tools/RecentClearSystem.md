# Game.Tools.RecentClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RecentClearSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_RecentQuery;
    private Game.Tools.RecentClearSystem+TypeHandle __TypeHandle;

    public RecentClearSystem();

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

- `private Unity.Entities.EntityQuery m_RecentQuery`  

```csharp
private Unity.Entities.EntityQuery m_RecentQuery;
```

- `private Game.Tools.RecentClearSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.RecentClearSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RecentClearSystem()`  

```csharp
[Preserve]
	public RecentClearSystem()
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
		return 65536;
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
		m_RecentQuery = GetEntityQuery(ComponentType.ReadOnly<Recent>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_RecentQuery);
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
		if (m_SimulationSystem.frameIndex >= 262144)
		{
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new ClearRecentJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_RecentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Recent_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SimulationFrame = m_SimulationSystem.frameIndex,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_RecentQuery, base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Tools.RecentClearSystem+ClearRecentJob`  
- `Game.Tools.RecentClearSystem+TypeHandle`  


# Game.Simulation.MailBoxSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MailBoxSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_MailBoxQuery;
    private Unity.Entities.EntityQuery m_PostConfigurationQuery;
    private Unity.Entities.EntityArchetype m_PostVanRequestArchetype;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.MailBoxSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public MailBoxSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MailBoxQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailBoxQuery;
```

- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostConfigurationQuery;
```

- `private Unity.Entities.EntityArchetype m_PostVanRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PostVanRequestArchetype;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.MailBoxSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MailBoxSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public MailBoxSystem()`  

```csharp
[Preserve]
	public MailBoxSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_MailBoxQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Routes.MailBox>(), ComponentType.ReadOnly<Game.Routes.TransportStop>(), ComponentType.Exclude<Game.Buildings.PostFacility>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>());
		m_PostConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<PostConfigurationData>());
		m_PostVanRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<PostVanRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireForUpdate(m_MailBoxQuery);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new MailBoxTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_MailBoxType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_MailBox_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PostVanRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_PostVanRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PostVanRequestArchetype = m_PostVanRequestArchetype,
			m_PostConfigurationData = m_PostConfigurationQuery.GetSingleton<PostConfigurationData>(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_MailBoxQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.MailBoxSystem+MailBoxTickJob`  
- `Game.Simulation.MailBoxSystem+TypeHandle`  


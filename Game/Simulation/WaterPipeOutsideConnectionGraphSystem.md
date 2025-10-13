# Game.Simulation.WaterPipeOutsideConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeOutsideConnectionGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
    private Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeOutsideConnectionGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
```

- `private Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeOutsideConnectionGraphSystem()`  

```csharp
[Preserve]
	public WaterPipeOutsideConnectionGraphSystem()
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
		m_WaterPipeFlowSystem = base.World.GetOrCreateSystemManaged<WaterPipeFlowSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier3>();
		m_CreatedConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<WaterPipeOutsideConnection>(), ComponentType.ReadOnly<Owner>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CreatedConnectionQuery);
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
		CreateOutsideConnectionsJob jobData = new CreateOutsideConnectionsJob
		{
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPipeNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterPipeNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_EdgeArchetype = m_WaterPipeFlowSystem.edgeArchetype,
			m_SourceNode = m_WaterPipeFlowSystem.sourceNode,
			m_SinkNode = m_WaterPipeFlowSystem.sinkNode
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedConnectionQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.WaterPipeOutsideConnectionGraphSystem+CreateOutsideConnectionsJob`  
- `Game.Simulation.WaterPipeOutsideConnectionGraphSystem+TypeHandle`  


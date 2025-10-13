# Game.Simulation.ElectricityOutsideConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityOutsideConnectionGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
    private Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle __TypeHandle;

    public ElectricityOutsideConnectionGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatedConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedConnectionQuery;
```

- `private Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityOutsideConnectionGraphSystem()`  

```csharp
[Preserve]
	public ElectricityOutsideConnectionGraphSystem()
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
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier3>();
		m_CreatedConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityOutsideConnection>(), ComponentType.ReadOnly<Owner>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
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
			m_ElectricityNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_EdgeArchetype = m_ElectricityFlowSystem.edgeArchetype,
			m_SourceNode = m_ElectricityFlowSystem.sourceNode,
			m_SinkNode = m_ElectricityFlowSystem.sinkNode
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedConnectionQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ElectricityOutsideConnectionGraphSystem+CreateOutsideConnectionsJob`  
- `Game.Simulation.ElectricityOutsideConnectionGraphSystem+TypeHandle`  


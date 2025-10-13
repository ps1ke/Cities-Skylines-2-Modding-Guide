# Game.Simulation.ServiceRequestSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceRequestSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_RequestGroupQuery;
    private Unity.Entities.EntityQuery m_HandleRequestQuery;
    private Game.Simulation.ServiceRequestSystem+TypeHandle __TypeHandle;

    public ServiceRequestSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_RequestGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequestGroupQuery;
```

- `private Unity.Entities.EntityQuery m_HandleRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_HandleRequestQuery;
```

- `private Game.Simulation.ServiceRequestSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceRequestSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceRequestSystem()`  

```csharp
[Preserve]
	public ServiceRequestSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_RequestGroupQuery = GetEntityQuery(ComponentType.ReadOnly<RequestGroup>());
		m_HandleRequestQuery = GetEntityQuery(ComponentType.ReadOnly<HandleRequest>());
		RequireAnyForUpdate(m_RequestGroupQuery, m_HandleRequestQuery);
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
		if (!m_RequestGroupQuery.IsEmptyIgnoreFilter)
		{
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UpdateRequestGroupJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_RequestGroupType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_RequestGroup_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RandomSeed = RandomSeed.Next(),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_RequestGroupQuery, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
		if (!m_HandleRequestQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			JobHandle jobHandle2 = IJobExtensions.Schedule(new HandleRequestJob
			{
				m_HandleRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_HandleRequest_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DispatchedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Dispatched_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Chunks = m_HandleRequestQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
			}, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
			base.Dependency = jobHandle2;
		}
	}
```


## Nested types

- `Game.Simulation.ServiceRequestSystem+UpdateRequestGroupJob`  
- `Game.Simulation.ServiceRequestSystem+HandleRequestJob`  
- `Game.Simulation.ServiceRequestSystem+TypeHandle`  


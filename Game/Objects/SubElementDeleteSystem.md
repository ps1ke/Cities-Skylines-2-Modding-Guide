# Game.Objects.SubElementDeleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubElementDeleteSystem : Game.GameSystemBase
{
    private Game.Tools.ToolReadyBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle;

    public SubElementDeleteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolReadyBarrier m_ModificationBarrier`  

```csharp
private Game.Tools.ToolReadyBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubElementDeleteSystem()`  

```csharp
[Preserve]
	public SubElementDeleteSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ToolReadyBarrier>();
		m_DeletedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<SubArea>(),
				ComponentType.ReadOnly<SubNet>(),
				ComponentType.ReadOnly<SubRoute>(),
				ComponentType.ReadOnly<OwnedVehicle>()
			}
		});
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Vehicle>(), ComponentType.ReadOnly<Owner>());
		m_AppliedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		RequireForUpdate(m_DeletedQuery);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new DeleteSubElementsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SubAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubRouteType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_SubRoute_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnedVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_AppliedTypes = m_AppliedTypes,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_DeletedQuery, base.Dependency);
		if (!m_CreatedQuery.IsEmptyIgnoreFilter)
		{
			CheckDeletedOwnersJob jobData = new CheckDeletedOwnersJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			jobHandle = JobHandle.CombineDependencies(jobHandle, JobChunkExtensions.ScheduleParallel(jobData, m_CreatedQuery, base.Dependency));
		}
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Objects.SubElementDeleteSystem+DeleteSubElementsJob`  
- `Game.Objects.SubElementDeleteSystem+CheckDeletedOwnersJob`  
- `Game.Objects.SubElementDeleteSystem+TypeHandle`  


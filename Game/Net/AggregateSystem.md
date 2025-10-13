# Game.Net.AggregateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AggregateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Game.Net.AggregateSystem+TypeHandle __TypeHandle;

    public AggregateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Game.Net.AggregateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.AggregateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AggregateSystem()`  

```csharp
[Preserve]
	public AggregateSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2B>();
		m_ModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Aggregated>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[0]
		});
		RequireForUpdate(m_ModifiedQuery);
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
		NativeList<ArchetypeChunk> chunks = m_ModifiedQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new UpdateAgregatesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAggregateData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AggregateNetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_AggregatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Aggregated_RW_ComponentLookup, ref base.CheckedStateRef),
			m_AggregateElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_AggregateElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_Chunks = chunks,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Net.AggregateSystem+UpdateAgregatesJob`  
- `Game.Net.AggregateSystem+TypeHandle`  


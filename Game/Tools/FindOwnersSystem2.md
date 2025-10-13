# Game.Tools.FindOwnersSystem2

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindOwnersSystem2 : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_OwnersQuery;
    private Unity.Entities.EntityQuery m_SubEntityQuery;
    private Game.Tools.FindOwnersSystem2+TypeHandle __TypeHandle;

    public FindOwnersSystem2();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_OwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnersQuery;
```

- `private Unity.Entities.EntityQuery m_SubEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubEntityQuery;
```

- `private Game.Tools.FindOwnersSystem2+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.FindOwnersSystem2+TypeHandle __TypeHandle;
```


## Constructors

- `public FindOwnersSystem2()`  

```csharp
[Preserve]
	public FindOwnersSystem2()
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
		m_OwnersQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.SubNet>(),
				ComponentType.ReadOnly<Game.Areas.SubArea>(),
				ComponentType.ReadOnly<Game.Objects.SubObject>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_SubEntityQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<OwnerDefinition>(),
				ComponentType.ReadOnly<Owner>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.Node>(),
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Area>(),
				ComponentType.ReadOnly<Object>()
			}
		});
		RequireForUpdate(m_SubEntityQuery);
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
		NativeList<ArchetypeChunk> ownerChunks = m_OwnersQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new FindOwnersSystem.SetSubEntityOwnerJob
		{
			m_OwnerChunks = ownerChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_SubEntityQuery, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
		ownerChunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.FindOwnersSystem2+TypeHandle`  


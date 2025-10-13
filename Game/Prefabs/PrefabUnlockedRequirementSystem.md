# Game.Prefabs.PrefabUnlockedRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabUnlockedRequirementSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Unity.Entities.EntityQuery m_UnlockQuery;
    private Unity.Entities.EntityQuery m_PrefabUnlockedQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle __TypeHandle;

    public PrefabUnlockedRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Unity.Entities.EntityQuery m_UnlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabUnlockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabUnlockedQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrefabUnlockedRequirementSystem()`  

```csharp
[Preserve]
	public PrefabUnlockedRequirementSystem()
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
		m_ModificationEndBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_UnlockQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_PrefabUnlockedQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabUnlockedRequirement>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
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
		if (!m_UnlockQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			NativeList<Entity> prefabUnlockedRequirementEntities = m_PrefabUnlockedQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new UnlockJob
			{
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_Buffer = m_ModificationEndBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_PrefabUnlockedRequirementEntities = prefabUnlockedRequirementEntities,
				m_PrefabUnlockedRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PrefabUnlockedRequirement_RO_BufferLookup, ref base.CheckedStateRef),
				m_LockedDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UnlockTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Unlock_RO_ComponentTypeHandle, ref base.CheckedStateRef)
			}, m_UnlockQuery, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
			prefabUnlockedRequirementEntities.Dispose(jobHandle);
			m_ModificationEndBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Prefabs.PrefabUnlockedRequirementSystem+UnlockJob`  
- `Game.Prefabs.PrefabUnlockedRequirementSystem+TypeHandle`  


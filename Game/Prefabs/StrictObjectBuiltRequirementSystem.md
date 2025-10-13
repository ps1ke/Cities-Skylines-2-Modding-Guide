# Game.Prefabs.StrictObjectBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StrictObjectBuiltRequirementSystem : Game.GameSystemBase
{
    private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Unity.Entities.EntityQuery m_ChangedQuery;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private System.Boolean m_Loaded;
    private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle;

    public StrictObjectBuiltRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  

```csharp
private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Unity.Entities.EntityQuery m_ChangedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChangedQuery;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StrictObjectBuiltRequirementSystem()`  

```csharp
[Preserve]
	public StrictObjectBuiltRequirementSystem()
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

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_InstanceCountSystem = base.World.GetOrCreateSystemManaged<InstanceCountSystem>();
		m_ModificationEndBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_ChangedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabRef>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_RequirementQuery = GetEntityQuery(ComponentType.ReadOnly<StrictObjectBuiltRequirementData>(), ComponentType.ReadWrite<UnlockRequirementData>(), ComponentType.ReadOnly<Locked>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (GetLoaded() || !m_ChangedQuery.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			TrackObjectsJob jobData = new TrackObjectsJob
			{
				m_Buffer = m_ModificationEndBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_InstanceCounts = m_InstanceCountSystem.GetInstanceCounts(readOnly: true, out dependencies),
				m_ObjectBuiltRequirementDataHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_StrictObjectBuiltRequirementData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RequirementDataHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UnlockRequirementData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_UnlockEventArchetype = m_UnlockEventArchetype
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_RequirementQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
			m_InstanceCountSystem.AddCountReader(base.Dependency);
			m_ModificationEndBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Prefabs.StrictObjectBuiltRequirementSystem+TrackObjectsJob`  
- `Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle`  


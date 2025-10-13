# Game.Prefabs.ObjectBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectBuiltRequirementSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Unity.Entities.EntityQuery m_ChangedQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private System.Boolean m_Loaded;
    private Game.Prefabs.ObjectBuiltRequirementSystem+TypeHandle __TypeHandle;

    public ObjectBuiltRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Unity.Entities.EntityQuery m_ChangedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChangedQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Prefabs.ObjectBuiltRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ObjectBuiltRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectBuiltRequirementSystem()`  

```csharp
[Preserve]
	public ObjectBuiltRequirementSystem()
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
		m_ModificationEndBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_ChangedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabRef>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Native>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_AllQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Native>(), ComponentType.Exclude<Temp>());
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
		EntityQuery query = (GetLoaded() ? m_AllQuery : m_ChangedQuery);
		if (!query.IsEmptyIgnoreFilter)
		{
			UnlockOnBuildJob jobData = new UnlockOnBuildJob
			{
				m_UnlockEventArchetype = m_UnlockEventArchetype,
				m_Buffer = m_ModificationEndBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_PrefabRefTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LockedDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UnlockOnBuildDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockOnBuildData_RO_BufferLookup, ref base.CheckedStateRef),
				m_UnlockRequirementDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirementData_RW_ComponentLookup, ref base.CheckedStateRef),
				m_UnlockOnBuildRequirementDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectBuiltRequirementData_RO_ComponentLookup, ref base.CheckedStateRef)
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, query, base.Dependency);
			m_ModificationEndBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Prefabs.ObjectBuiltRequirementSystem+UnlockOnBuildJob`  
- `Game.Prefabs.ObjectBuiltRequirementSystem+TypeHandle`  


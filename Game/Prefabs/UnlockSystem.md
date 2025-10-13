# Game.Prefabs.UnlockSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UnlockSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_LockedQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private System.Boolean m_Loaded;
    private Colossal.Logging.ILog m_Log;
    private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle;

    public UnlockSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    public System.Boolean IsLocked(Game.Prefabs.PrefabBase prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private System.Boolean ProcessEvents();
    private System.Void UnlockPrefab(Unity.Entities.Entity unlock, System.Boolean createEvent);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_LockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Colossal.Logging.ILog m_Log`  

```csharp
private Colossal.Logging.ILog m_Log;
```

- `private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UnlockSystem()`  

```csharp
[Preserve]
	public UnlockSystem()
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

- `public IsLocked(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public bool IsLocked(PrefabBase prefab)
	{
		return m_PrefabSystem.HasEnabledComponent<Locked>(prefab);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_LockedQuery = GetEntityQuery(ComponentType.ReadOnly<Locked>(), ComponentType.ReadOnly<UnlockRequirement>());
		m_UpdatedQuery = GetEntityQuery(ComponentType.ReadOnly<Locked>(), ComponentType.ReadOnly<UnlockRequirement>(), ComponentType.ReadOnly<Updated>());
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		m_Log = LogManager.GetLogger("Unlocking");
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
protected override void OnGameLoaded(Context context)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		if (!ProcessEvents() && !loaded && m_UpdatedQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeQueue<Entity> nativeQueue = new NativeQueue<Entity>(Allocator.TempJob);
		try
		{
			while (true)
			{
				JobChunkExtensions.ScheduleParallel(new CheckUnlockRequirementsJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_UnlockRequirementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_LockedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
					m_UnlockQueue = nativeQueue.AsParallelWriter()
				}, m_LockedQuery, default(JobHandle)).Complete();
				if (nativeQueue.Count == 0)
				{
					break;
				}
				Entity item;
				while (nativeQueue.TryDequeue(out item))
				{
					UnlockPrefab(item, createEvent: true);
				}
			}
		}
		finally
		{
			nativeQueue.Dispose();
		}
	}
```

- `private ProcessEvents() : System.Boolean`  

```csharp
private bool ProcessEvents()
	{
		if (m_EventQuery.IsEmptyIgnoreFilter)
		{
			return false;
		}
		bool result = false;
		NativeArray<Unlock> nativeArray = m_EventQuery.ToComponentDataArray<Unlock>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity prefab = nativeArray[i].m_Prefab;
				if (base.EntityManager.HasEnabledComponent<Locked>(prefab))
				{
					UnlockPrefab(prefab, createEvent: false);
					result = true;
				}
			}
			return result;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `private UnlockPrefab(Unity.Entities.Entity unlock, System.Boolean createEvent) : System.Void`  

```csharp
private void UnlockPrefab(Entity unlock, bool createEvent)
	{
		base.EntityManager.SetComponentEnabled<Locked>(unlock, value: false);
		if (createEvent)
		{
			Entity entity = base.EntityManager.CreateEntity(m_UnlockEventArchetype);
			base.EntityManager.SetComponentData(entity, new Unlock(unlock));
		}
		if (!base.EntityManager.HasEnabledComponent<PrefabData>(unlock))
		{
			PrefabID obsoleteID = m_PrefabSystem.GetObsoleteID(unlock);
			m_Log.DebugFormat("Prefab unlocked: {0}", obsoleteID);
		}
		else
		{
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(unlock);
			m_Log.DebugFormat("Prefab unlocked: {0}", prefab);
		}
	}
```


## Nested types

- `Game.Prefabs.UnlockSystem+CheckUnlockRequirementsJob`  
- `Game.Prefabs.UnlockSystem+TypeHandle`  


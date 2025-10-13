# Game.Prefabs.PrefabInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle;

    public PrefabInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void InitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.Queue<Game.Prefabs.PrefabInitializeSystem+QueueItem> queue, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabSet, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
    private System.Void LateInitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrefabInitializeSystem()`  

```csharp
[Preserve]
	public PrefabInitializeSystem()
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

- `private InitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.Queue<Game.Prefabs.PrefabInitializeSystem+QueueItem> queue, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabSet, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Void`  

```csharp
private void InitializePrefab(Entity entity, PrefabBase prefab, Queue<QueueItem> queue, HashSet<PrefabBase> prefabSet, List<PrefabBase> dependencies, List<ComponentBase> components)
	{
		prefab.GetComponents(components);
		for (int i = 0; i < components.Count; i++)
		{
			ComponentBase componentBase = components[i];
			try
			{
				componentBase.Initialize(base.EntityManager, entity);
				componentBase.GetDependencies(dependencies);
			}
			catch (Exception exception)
			{
				COSystemBase.baseLog.ErrorFormat(prefab, exception, "Error when initializing prefab: {0} ({1})", prefab.name, (prefab.asset != null) ? ((object)prefab.asset) : ((object)"No asset"));
			}
			finally
			{
				foreach (PrefabBase dependency in dependencies)
				{
					if (dependency == null || prefabSet.Add(dependency))
					{
						queue.Enqueue(new QueueItem(dependency, prefab, componentBase));
					}
				}
				dependencies.Clear();
			}
		}
		components.Clear();
	}
```

- `private LateInitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Void`  

```csharp
private void LateInitializePrefab(Entity entity, PrefabBase prefab, List<PrefabBase> dependencies, List<ComponentBase> components)
	{
		bool flag = m_PrefabSystem.IsUnlockable(prefab);
		bool canIgnoreUnlockDependencies = prefab.canIgnoreUnlockDependencies;
		prefab.GetComponents(components);
		UnlockableBase unlockableBase = null;
		if (flag)
		{
			unlockableBase = prefab.GetComponent<UnlockableBase>();
		}
		for (int i = 0; i < components.Count; i++)
		{
			ComponentBase componentBase = components[i];
			if (!(componentBase != unlockableBase))
			{
				continue;
			}
			try
			{
				componentBase.LateInitialize(base.EntityManager, entity);
				if (!canIgnoreUnlockDependencies || !componentBase.ignoreUnlockDependencies)
				{
					componentBase.GetDependencies(dependencies);
				}
			}
			catch (Exception exception)
			{
				COSystemBase.baseLog.ErrorFormat(prefab, exception, "Error when initializing prefab: {0} ({1})", prefab.name, (prefab.asset != null) ? ((object)prefab.asset) : ((object)"No asset"));
			}
		}
		if (flag)
		{
			try
			{
				if (unlockableBase != null)
				{
					unlockableBase.LateInitialize(base.EntityManager, entity, dependencies);
				}
				else
				{
					UnlockableBase.DefaultLateInitialize(base.EntityManager, entity, dependencies);
				}
			}
			catch (Exception exception2)
			{
				COSystemBase.baseLog.ErrorFormat(prefab, exception2, "Error when initializing prefab: {0} ({1})", prefab.name, (prefab.asset != null) ? ((object)prefab.asset) : ((object)"No asset"));
			}
		}
		components.Clear();
		dependencies.Clear();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<PrefabData>());
		RequireForUpdate(m_PrefabQuery);
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
		NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			List<ListItem> list = new List<ListItem>();
			Queue<QueueItem> queue = new Queue<QueueItem>();
			HashSet<PrefabBase> hashSet = new HashSet<PrefabBase>();
			List<PrefabBase> dependencies = new List<PrefabBase>();
			List<ComponentBase> components = new List<ComponentBase>();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray3.Length; j++)
				{
					PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(nativeArray3[j]);
					list.Add(new ListItem(nativeArray2[j], prefab));
					hashSet.Add(prefab);
				}
			}
			foreach (ListItem item in list)
			{
				InitializePrefab(item.m_Entity, item.m_Prefab, queue, hashSet, dependencies, components);
			}
			QueueItem result;
			while (queue.TryDequeue(out result))
			{
				if (m_PrefabSystem.AddPrefab(result.m_Prefab, null, result.m_ParentPrefab, result.m_ParentComponent))
				{
					Entity entity = m_PrefabSystem.GetEntity(result.m_Prefab);
					InitializePrefab(entity, result.m_Prefab, queue, hashSet, dependencies, components);
					list.Add(new ListItem(entity, result.m_Prefab));
				}
			}
			foreach (ListItem item2 in list)
			{
				LateInitializePrefab(item2.m_Entity, item2.m_Prefab, dependencies, components);
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


## Nested types

- `Game.Prefabs.PrefabInitializeSystem+ListItem`  
- `Game.Prefabs.PrefabInitializeSystem+QueueItem`  
- `Game.Prefabs.PrefabInitializeSystem+TypeHandle`  


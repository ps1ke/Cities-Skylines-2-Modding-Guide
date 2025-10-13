# Game.Tutorials.TutorialObjectSelectionDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectSelectionDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle;

    public TutorialObjectSelectionDeactivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckDeactivate(Unity.Entities.EntityQuery query, Unity.Entities.Entity selection, System.Boolean tool);
    private Unity.Entities.Entity GetSelection(System.Boolean& tool);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```

- `private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectSelectionDeactivationSystem()`  

```csharp
[Preserve]
	public TutorialObjectSelectionDeactivationSystem()
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

- `private CheckDeactivate(Unity.Entities.EntityQuery query, Unity.Entities.Entity selection, System.Boolean tool) : System.Void`  

```csharp
private void CheckDeactivate(EntityQuery query, Entity selection, bool tool)
	{
		CheckTutorialsJob jobData = new CheckTutorialsJob
		{
			m_DeactivationDataType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectSelectionActivationData_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_Selection = selection,
			m_Tool = tool,
			m_Buffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, query, base.Dependency);
		m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
	}
```

- `private GetSelection(System.Boolean& tool) : Unity.Entities.Entity`  

```csharp
private Entity GetSelection(out bool tool)
	{
		tool = true;
		if (base.EntityManager.TryGetComponent<PrefabRef>(m_ToolSystem.selected, out var component))
		{
			tool = false;
			return component.m_Prefab;
		}
		if (m_ToolSystem.activeTool == m_ObjectToolSystem && m_ObjectToolSystem.prefab != null)
		{
			return m_PrefabSystem.GetEntity(m_ObjectToolSystem.prefab);
		}
		if (m_ToolSystem.activeTool == m_NetToolSystem && m_NetToolSystem.prefab != null)
		{
			return m_PrefabSystem.GetEntity(m_NetToolSystem.prefab);
		}
		tool = false;
		return Entity.Null;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PendingTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<ObjectSelectionActivationData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
		m_ActiveTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<ObjectSelectionActivationData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NetToolSystem = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
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
		if (!m_PendingTutorialQuery.IsEmptyIgnoreFilter || !m_ActiveTutorialQuery.IsEmptyIgnoreFilter)
		{
			bool tool;
			Entity selection = GetSelection(out tool);
			if (!m_PendingTutorialQuery.IsEmptyIgnoreFilter)
			{
				CheckDeactivate(m_PendingTutorialQuery, selection, tool);
			}
			if (!m_ActiveTutorialQuery.IsEmptyIgnoreFilter && base.phaseCanDeactivate)
			{
				CheckDeactivate(m_ActiveTutorialQuery, selection, tool);
			}
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialObjectSelectionDeactivationSystem+CheckTutorialsJob`  
- `Game.Tutorials.TutorialObjectSelectionDeactivationSystem+TypeHandle`  


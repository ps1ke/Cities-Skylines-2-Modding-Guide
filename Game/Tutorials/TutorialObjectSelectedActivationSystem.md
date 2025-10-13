# Game.Tutorials.TutorialObjectSelectedActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectSelectedActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle;

    public TutorialObjectSelectedActivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Entities.Entity GetSelection(System.Boolean& tool);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectSelectedActivationSystem()`  

```csharp
[Preserve]
	public TutorialObjectSelectedActivationSystem()
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
		if (m_ToolSystem.activeTool == m_AreaToolSystem && m_AreaToolSystem.prefab != null)
		{
			return m_PrefabSystem.GetEntity(m_AreaToolSystem.prefab);
		}
		if (m_ToolSystem.activeTool == m_RouteToolSystem && m_RouteToolSystem.prefab != null)
		{
			return m_PrefabSystem.GetEntity(m_RouteToolSystem.prefab);
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
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_NetToolSystem = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_RouteToolSystem = base.World.GetOrCreateSystemManaged<RouteToolSystem>();
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectSelectionActivationData>(), ComponentType.Exclude<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>());
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
		if (!m_TutorialQuery.IsEmptyIgnoreFilter)
		{
			bool tool;
			Entity selection = GetSelection(out tool);
			if (selection != Entity.Null)
			{
				ActivateJob jobData = new ActivateJob
				{
					m_ActivationDataType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectSelectionActivationData_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_Selection = selection,
					m_Tool = tool,
					m_Writer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
				};
				base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TutorialQuery, base.Dependency);
				m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
			}
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialObjectSelectedActivationSystem+ActivateJob`  
- `Game.Tutorials.TutorialObjectSelectedActivationSystem+TypeHandle`  


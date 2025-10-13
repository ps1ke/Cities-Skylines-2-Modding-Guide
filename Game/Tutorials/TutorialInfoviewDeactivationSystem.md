# Game.Tutorials.TutorialInfoviewDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialInfoviewDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle;

    public TutorialInfoviewDeactivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckDeactivation(Unity.Entities.EntityQuery query);
    private Unity.Entities.Entity GetActiveInfoview();
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

- `private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialInfoviewDeactivationSystem()`  

```csharp
[Preserve]
	public TutorialInfoviewDeactivationSystem()
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

- `private CheckDeactivation(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private void CheckDeactivation(EntityQuery query)
	{
		CheckDeactivationJob jobData = new CheckDeactivationJob
		{
			m_ActivationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_InfoviewActivationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_Infoview = GetActiveInfoview(),
			m_Buffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, query, base.Dependency);
		m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
	}
```

- `private GetActiveInfoview() : Unity.Entities.Entity`  

```csharp
private Entity GetActiveInfoview()
	{
		if (m_ToolSystem.activeInfoview == null)
		{
			return Entity.Null;
		}
		return m_PrefabSystem.GetEntity(m_ToolSystem.activeInfoview);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PendingTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<InfoviewActivationData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
		m_ActiveTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<InfoviewActivationData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
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
		if (!m_PendingTutorialQuery.IsEmptyIgnoreFilter)
		{
			CheckDeactivation(m_PendingTutorialQuery);
		}
		if (!m_ActiveTutorialQuery.IsEmptyIgnoreFilter && base.phaseCanDeactivate)
		{
			CheckDeactivation(m_ActiveTutorialQuery);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialInfoviewDeactivationSystem+CheckDeactivationJob`  
- `Game.Tutorials.TutorialInfoviewDeactivationSystem+TypeHandle`  


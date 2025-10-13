# Game.Tutorials.TutorialInfoviewActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialInfoviewActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle __TypeHandle;

    public TutorialInfoviewActivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialInfoviewActivationSystem()`  

```csharp
[Preserve]
	public TutorialInfoviewActivationSystem()
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
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<InfoviewActivationData>(), ComponentType.Exclude<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>());
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
		if (!m_TutorialQuery.IsEmptyIgnoreFilter && m_ToolSystem.activeInfoview != null)
		{
			CheckActivationJob jobData = new CheckActivationJob
			{
				m_ActivationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_InfoviewActivationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_Infoview = m_PrefabSystem.GetEntity(m_ToolSystem.infoview),
				m_Writer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TutorialQuery, base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialInfoviewActivationSystem+CheckActivationJob`  
- `Game.Tutorials.TutorialInfoviewActivationSystem+TypeHandle`  


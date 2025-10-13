# Game.Tutorials.TutorialControlSchemeDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialControlSchemeDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase
{
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle __TypeHandle;

    public TutorialControlSchemeDeactivationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CheckDeactivate(Unity.Entities.EntityQuery query);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```

- `private Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialControlSchemeDeactivationSystem()`  

```csharp
[Preserve]
	public TutorialControlSchemeDeactivationSystem()
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

- `private CheckDeactivate(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private void CheckDeactivate(EntityQuery query)
	{
		if (!query.IsEmptyIgnoreFilter)
		{
			DeactivateJob jobData = new DeactivateJob
			{
				m_ControlSchemeDeactivationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_ControlSchemeActivationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ControlScheme = InputManager.instance.activeControlScheme,
				m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, query, base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PendingTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<ControlSchemeActivationData>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
		m_ActiveTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<ControlSchemeActivationData>(), ComponentType.ReadOnly<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
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
		if (InputManager.instance != null)
		{
			if (!m_PendingTutorialQuery.IsEmptyIgnoreFilter)
			{
				CheckDeactivate(m_PendingTutorialQuery);
			}
			if (!m_ActiveTutorialQuery.IsEmptyIgnoreFilter && base.phaseCanDeactivate)
			{
				CheckDeactivate(m_ActiveTutorialQuery);
			}
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialControlSchemeDeactivationSystem+DeactivateJob`  
- `Game.Tutorials.TutorialControlSchemeDeactivationSystem+TypeHandle`  


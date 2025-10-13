# Game.Tutorials.TutorialControlSchemeActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialControlSchemeActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_TutorialQuery;
    private Game.Tutorials.TutorialControlSchemeActivationSystem+TypeHandle __TypeHandle;

    public TutorialControlSchemeActivationSystem();

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

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Game.Tutorials.TutorialControlSchemeActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialControlSchemeActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialControlSchemeActivationSystem()`  

```csharp
[Preserve]
	public TutorialControlSchemeActivationSystem()
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
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<ControlSchemeActivationData>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<TutorialActivated>());
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
		if (!m_TutorialQuery.IsEmptyIgnoreFilter && InputManager.instance != null)
		{
			ActivateJob jobData = new ActivateJob
			{
				m_ControlSchemeActivationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_ControlSchemeActivationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ControlScheme = InputManager.instance.activeControlScheme,
				m_Writer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TutorialQuery, base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialControlSchemeActivationSystem+ActivateJob`  
- `Game.Tutorials.TutorialControlSchemeActivationSystem+TypeHandle`  


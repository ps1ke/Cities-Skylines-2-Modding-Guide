# Game.Tutorials.TutorialAutoActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialAutoActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_AutoActivateQuery;
    private Game.Tutorials.TutorialAutoActivationSystem+TypeHandle __TypeHandle;

    public TutorialAutoActivationSystem();

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

- `private Unity.Entities.EntityQuery m_AutoActivateQuery`  

```csharp
private Unity.Entities.EntityQuery m_AutoActivateQuery;
```

- `private Game.Tutorials.TutorialAutoActivationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialAutoActivationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialAutoActivationSystem()`  

```csharp
[Preserve]
	public TutorialAutoActivationSystem()
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
		m_AutoActivateQuery = GetEntityQuery(ComponentType.ReadOnly<AutoActivationData>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<TutorialActivated>());
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
		if (!m_AutoActivateQuery.IsEmptyIgnoreFilter)
		{
			ActivateJob jobData = new ActivateJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_LockedDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AutoActivationDataTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tutorials_AutoActivationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Writer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_AutoActivateQuery, base.Dependency);
			m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialAutoActivationSystem+ActivateJob`  
- `Game.Tutorials.TutorialAutoActivationSystem+TypeHandle`  


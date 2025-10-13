# Game.Tutorials.TutorialObjectSelectionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialObjectSelectionTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Entities.Entity m_LastSelection;
    private Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle __TypeHandle;

    public TutorialObjectSelectionTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Entities.Entity m_LastSelection`  

```csharp
private Unity.Entities.Entity m_LastSelection;
```

- `private Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TutorialObjectSelectionTriggerSystem()`  

```csharp
[Preserve]
	public TutorialObjectSelectionTriggerSystem()
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
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectSelectionTriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.Exclude<TriggerCompleted>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		RequireForUpdate(m_ActiveTriggerQuery);
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
		base.OnUpdate();
		if (base.triggersChanged)
		{
			m_LastSelection = m_ToolSystem.selected;
		}
		if (m_ToolSystem.selected != Entity.Null && m_ToolSystem.selected != m_LastSelection)
		{
			m_LastSelection = m_ToolSystem.selected;
			if (base.EntityManager.TryGetComponent<PrefabRef>(m_ToolSystem.selected, out var component))
			{
				CheckSelectionJob jobData = new CheckSelectionJob
				{
					m_ForcedUnlockDataFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ForceUIGroupUnlockData_RO_BufferLookup, ref base.CheckedStateRef),
					m_UnlockRequirementFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_UnlockRequirement_RO_BufferLookup, ref base.CheckedStateRef),
					m_TriggerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Tutorials_ObjectSelectionTriggerData_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_UnlockEventArchetype = m_UnlockEventArchetype,
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_Selection = component.m_Prefab,
					m_CommandBuffer = m_BarrierSystem.CreateCommandBuffer().AsParallelWriter()
				};
				base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ActiveTriggerQuery, base.Dependency);
				m_BarrierSystem.AddJobHandleForProducer(base.Dependency);
			}
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialObjectSelectionTriggerSystem+CheckSelectionJob`  
- `Game.Tutorials.TutorialObjectSelectionTriggerSystem+TypeHandle`  


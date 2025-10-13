# Game.Tutorials.TutorialDeactivationSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class TutorialDeactivationSystemBase : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ActivePhaseQuery;
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;

    protected System.Boolean phaseCanDeactivate { protected get; }

    protected TutorialDeactivationSystemBase();

    protected virtual System.Void OnCreate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ActivePhaseQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActivePhaseQuery;
```

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```


## Properties

- `protected System.Boolean phaseCanDeactivate { protected get }`  

```csharp
protected System.Boolean phaseCanDeactivate { protected get; }
```


## Constructors

- `protected TutorialDeactivationSystemBase()`  

```csharp
[Preserve]
	protected TutorialDeactivationSystemBase()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier3>();
		m_ActivePhaseQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialPhaseData>(), ComponentType.ReadOnly<TutorialPhaseActive>(), ComponentType.ReadOnly<TutorialPhaseCanDeactivate>());
	}
```



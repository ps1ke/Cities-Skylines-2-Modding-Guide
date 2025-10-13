# Game.Tutorials.TutorialTriggerSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class TutorialTriggerSystemBase : Game.GameSystemBase
{
    protected Game.Common.ModificationBarrier5 m_BarrierSystem;
    protected Unity.Entities.EntityQuery m_ActiveTriggerQuery;
    private Game.Tutorials.TutorialSystem m_TutorialSystem;
    private Unity.Entities.Entity m_LastPhase;
    private System.Boolean <triggersChanged>k__BackingField;

    protected System.Boolean triggersChanged { protected get; private set; }

    protected TutorialTriggerSystemBase();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Game.Common.ModificationBarrier5 m_BarrierSystem`  

```csharp
protected Game.Common.ModificationBarrier5 m_BarrierSystem;
```

- `protected Unity.Entities.EntityQuery m_ActiveTriggerQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ActiveTriggerQuery;
```

- `private Game.Tutorials.TutorialSystem m_TutorialSystem`  

```csharp
private Game.Tutorials.TutorialSystem m_TutorialSystem;
```

- `private Unity.Entities.Entity m_LastPhase`  

```csharp
private Unity.Entities.Entity m_LastPhase;
```

- `private System.Boolean <triggersChanged>k__BackingField`  

```csharp
private System.Boolean <triggersChanged>k__BackingField;
```


## Properties

- `protected System.Boolean triggersChanged { protected get; private set }`  

```csharp
protected System.Boolean triggersChanged { protected get; private set; }
```


## Constructors

- `protected TutorialTriggerSystemBase()`  

```csharp
[Preserve]
	protected TutorialTriggerSystemBase()
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
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_TutorialSystem = base.World.GetOrCreateSystemManaged<TutorialSystem>();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_LastPhase = Entity.Null;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		m_LastPhase = Entity.Null;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		Entity activeTutorialPhase = m_TutorialSystem.activeTutorialPhase;
		if (activeTutorialPhase != m_LastPhase)
		{
			m_LastPhase = activeTutorialPhase;
			triggersChanged = true;
		}
		else
		{
			triggersChanged = false;
		}
	}
```



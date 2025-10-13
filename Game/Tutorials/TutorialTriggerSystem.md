# Game.Tutorials.TutorialTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class TutorialTriggerSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems;
    private Unity.Entities.EntityQuery m_TriggerQuery;

    public TutorialTriggerSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems`  

```csharp
private readonly System.Collections.Generic.List<Game.Tutorials.TutorialTriggerSystemBase> m_Systems;
```

- `private Unity.Entities.EntityQuery m_TriggerQuery`  

```csharp
private Unity.Entities.EntityQuery m_TriggerQuery;
```


## Constructors

- `public TutorialTriggerSystem()`  

```csharp
[Preserve]
	public TutorialTriggerSystem()
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
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialObjectPlacementTriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialInputTriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialAreaTriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialObjectSelectionTriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialUpgradeTriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialUITriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialPolicyAdjustmentTriggerSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialZoningTriggerSystem>());
		m_TriggerQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialTriggerData>());
		base.Enabled = false;
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		foreach (TutorialTriggerSystemBase system in m_Systems)
		{
			try
			{
				system.Update();
			}
			catch (Exception exception)
			{
				COSystemBase.baseLog.Critical(exception);
			}
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		base.EntityManager.RemoveComponent<TriggerActive>(m_TriggerQuery);
		base.EntityManager.RemoveComponent<TriggerPreCompleted>(m_TriggerQuery);
		base.EntityManager.RemoveComponent<TriggerCompleted>(m_TriggerQuery);
		base.EntityManager.RemoveComponent<TutorialNextPhase>(m_TriggerQuery);
	}
```



# Game.Tutorials.TutorialDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialDeactivationSystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.Tutorials.TutorialDeactivationSystemBase> m_Systems;

    public TutorialDeactivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Collections.Generic.List<Game.Tutorials.TutorialDeactivationSystemBase> m_Systems`  

```csharp
private System.Collections.Generic.List<Game.Tutorials.TutorialDeactivationSystemBase> m_Systems;
```


## Constructors

- `public TutorialDeactivationSystem()`  

```csharp
[Preserve]
	public TutorialDeactivationSystem()
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
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialControlSchemeDeactivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialUIDeactivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialObjectSelectionDeactivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialInfoviewDeactivationSystem>());
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
		foreach (TutorialDeactivationSystemBase system in m_Systems)
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



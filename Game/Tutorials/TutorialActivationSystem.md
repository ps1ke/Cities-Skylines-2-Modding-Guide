# Game.Tutorials.TutorialActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialActivationSystem : Game.GameSystemBase
{
    private readonly System.Collections.Generic.List<Game.GameSystemBase> m_Systems;

    public TutorialActivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.GameSystemBase> m_Systems`  

```csharp
private readonly System.Collections.Generic.List<Game.GameSystemBase> m_Systems;
```


## Constructors

- `public TutorialActivationSystem()`  

```csharp
[Preserve]
	public TutorialActivationSystem()
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
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialUIActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialAutoActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialControlSchemeActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialObjectSelectedActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialInfoviewActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialFireActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialHealthProblemActivationSystem>());
		m_Systems.Add(base.World.GetOrCreateSystemManaged<TutorialEventActivationSystem>());
		base.Enabled = false;
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame() || mode.IsEditor();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		foreach (GameSystemBase system in m_Systems)
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



# Game.GameSystemBase

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class abstract public  

**Base:** `Colossal.Entities.COSystemBase`  

## Code

```csharp
public abstract class GameSystemBase : Colossal.Entities.COSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;

    protected GameSystemBase();

    private System.Void FocusChanged(System.Boolean hasfocus);
    private System.Void GameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void GameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    private System.Void GamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnFocusChanged(System.Boolean hasFocus);
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnWorldReady();
    public System.Void ResetDependency();
    private System.Void WorldReady();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```


## Constructors

- `protected GameSystemBase()`  

```csharp
[Preserve]
	protected GameSystemBase()
	{
	}
```


## Methods

- `private FocusChanged(System.Boolean hasfocus) : System.Void`  

```csharp
private void FocusChanged(bool hasfocus)
	{
		try
		{
			OnFocusChanged(hasfocus);
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, GetType().Name + ": Error on Focus change");
		}
	}
```

- `private GameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
private void GameLoaded(Context serializationContext)
	{
		try
		{
			OnGameLoaded(serializationContext);
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, GetType().Name + ": Error on game load, disabling system...");
			base.Enabled = false;
		}
	}
```

- `private GameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private void GameLoadingComplete(Purpose purpose, GameMode mode)
	{
		try
		{
			OnGameLoadingComplete(purpose, mode);
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, GetType().Name + ": Error on state change, disabling system...");
		}
	}
```

- `private GamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private void GamePreload(Purpose purpose, GameMode mode)
	{
		try
		{
			OnGamePreload(purpose, mode);
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, GetType().Name + ": Error on game preload, disabling system...");
			base.Enabled = false;
		}
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 1;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return -1;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		if (base.World == World.DefaultGameObjectInjectionWorld)
		{
			m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
			LoadGameSystem loadGameSystem = m_LoadGameSystem;
			loadGameSystem.onOnSaveGameLoaded = (LoadGameSystem.EventGameLoaded)Delegate.Combine(loadGameSystem.onOnSaveGameLoaded, new LoadGameSystem.EventGameLoaded(GameLoaded));
		}
		GameManager.instance.onWorldReady += WorldReady;
		GameManager.instance.onGamePreload += GamePreload;
		GameManager.instance.onGameLoadingComplete += GameLoadingComplete;
		Application.focusChanged += FocusChanged;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		GameManager.instance.onWorldReady -= WorldReady;
		GameManager.instance.onGamePreload -= GamePreload;
		GameManager.instance.onGameLoadingComplete -= GameLoadingComplete;
		if (base.World == World.DefaultGameObjectInjectionWorld && m_LoadGameSystem != null)
		{
			LoadGameSystem loadGameSystem = m_LoadGameSystem;
			loadGameSystem.onOnSaveGameLoaded = (LoadGameSystem.EventGameLoaded)Delegate.Remove(loadGameSystem.onOnSaveGameLoaded, new LoadGameSystem.EventGameLoaded(GameLoaded));
		}
		Application.focusChanged -= FocusChanged;
		base.OnDestroy();
	}
```

- `protected virtual OnFocusChanged(System.Boolean hasFocus) : System.Void`  

```csharp
protected virtual void OnFocusChanged(bool hasFocus)
	{
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual void OnGameLoaded(Context serializationContext)
	{
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual void OnGameLoadingComplete(Purpose purpose, GameMode mode)
	{
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual void OnGamePreload(Purpose purpose, GameMode mode)
	{
	}
```

- `protected virtual OnWorldReady() : System.Void`  

```csharp
protected virtual void OnWorldReady()
	{
	}
```

- `public ResetDependency() : System.Void`  

```csharp
public void ResetDependency()
	{
		base.Dependency = default(JobHandle);
	}
```

- `private WorldReady() : System.Void`  

```csharp
private void WorldReady()
	{
		try
		{
			OnWorldReady();
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, GetType().Name + ": Error on game preload, disabling system...");
			base.Enabled = false;
		}
	}
```



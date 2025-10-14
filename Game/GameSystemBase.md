# Game.GameSystemBase

**Assembly:**  
**Namespace:** Game

**Type:** abstract class

**Base:** COSystemBase

**Summary:** GameSystemBase is an abstract base class for game systems that need to integrate with the Cities: Skylines 2 game lifecycle. It wires into GameManager and LoadGameSystem events (world ready, preload, loading complete, save-game loaded) and forwards those events to protected virtual handlers which derived systems can override. It also listens for application focus changes and provides utility methods for update scheduling and dependency resetting. The base implementation wraps event callbacks in try/catch blocks and logs errors (disabling the system on severe failures) so derived systems get a stable, fault-tolerant integration point.
---

## Fields

- `private LoadGameSystem m_LoadGameSystem`  
Holds a reference to the LoadGameSystem retrieved from the default world. Used to subscribe/unsubscribe to the save-game loaded event so the system can be notified when a save is deserialized.

## Properties

This class does not declare any properties.

## Constructors

- `protected GameSystemBase()`  
Preserved constructor used by the runtime. Does not perform initialization itself; initialization is done in OnCreate. Marked with Preserve to avoid stripping.

## Methods

- `protected override void OnCreate()`  
Initializes the system: if running in the default World it gets or creates the LoadGameSystem and subscribes the GameLoaded handler to its onOnSaveGameLoaded event. Also subscribes to GameManager lifecycle events (onWorldReady, onGamePreload, onGameLoadingComplete) and to Application.focusChanged. All event callbacks from the game are routed to protected virtual methods that derived classes may override. Exceptions thrown in callbacks are caught and logged to prevent crashes; on serious errors the system may be disabled.

- `private void FocusChanged(bool hasfocus)`  
Internal handler for Application.focusChanged. Calls the protected virtual OnFocusChanged inside a try/catch and logs any exceptions.

- `protected override void OnDestroy()`  
Tears down event subscriptions: unsubscribes from GameManager events, removes the GameLoaded delegate from LoadGameSystem if it was registered, unsubscribes Application.focusChanged, and calls base.OnDestroy().

- `private void GameLoadingComplete(Purpose purpose, GameMode mode)`  
Internal handler invoked when the game loading completes. Calls OnGameLoadingComplete in a try/catch and logs errors; on exception the system may be disabled.

- `private void GameLoaded(Context serializationContext)`  
Internal handler invoked after a save game is loaded. Calls OnGameLoaded in a try/catch; on exception the error is logged and the system is disabled.

- `private void GamePreload(Purpose purpose, GameMode mode)`  
Internal handler invoked during game preload. Calls OnGamePreload in a try/catch and disables the system on exception.

- `private void WorldReady()`  
Internal handler for when the game world becomes ready. Calls OnWorldReady in a try/catch and may disable the system on exception.

- `protected virtual void OnWorldReady()`  
Virtual callback for derived systems to implement logic when the world is ready. Default implementation is empty.

- `protected virtual void OnGamePreload(Purpose purpose, GameMode mode)`  
Virtual callback for derived systems to react to the game's preload phase. Default implementation is empty.

- `protected virtual void OnGameLoaded(Context serializationContext)`  
Virtual callback for derived systems to react after a save game is loaded. Default implementation is empty.

- `protected virtual void OnGameLoadingComplete(Purpose purpose, GameMode mode)`  
Virtual callback for derived systems to react once the game loading is complete. Default implementation is empty.

- `protected virtual void OnFocusChanged(bool hasFocus)`  
Virtual callback to respond to application focus changes. Default implementation is empty.

- `public virtual int GetUpdateInterval(SystemUpdatePhase phase)`  
Returns the update interval used by the system. Default returns 1. Derived systems can override to change how frequently the system runs relative to the scheduler.

- `public virtual int GetUpdateOffset(SystemUpdatePhase phase)`  
Returns an update offset for scheduling relative updates. Default returns -1. Override to control per-phase offset placement.

- `public void ResetDependency()`  
Resets the ECS Dependency property to the default JobHandle, clearing any previously set dependency. Useful when a system wants to break dependency chains or ensure no pending jobs are awaited.

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
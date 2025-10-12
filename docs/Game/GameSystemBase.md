# Game.GameSystemBase

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class abstract public  

**Base:** `Colossal.Entities.COSystemBase`  

## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

## Constructors

- `protected GameSystemBase()`  

## Methods

- `private FocusChanged(System.Boolean hasfocus) : System.Void`  
- `private GameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private GameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `private GamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnFocusChanged(System.Boolean hasFocus) : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnWorldReady() : System.Void`  
- `public ResetDependency() : System.Void`  
- `private WorldReady() : System.Void`  


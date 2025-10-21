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
protected GameSystemBase();
```


## Methods

- `private FocusChanged(System.Boolean hasfocus) : System.Void`  

```csharp
private System.Void FocusChanged(System.Boolean hasfocus);
```

- `private GameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
private System.Void GameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private GameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private System.Void GameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `private GamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private System.Void GamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnFocusChanged(System.Boolean hasFocus) : System.Void`  

```csharp
protected virtual System.Void OnFocusChanged(System.Boolean hasFocus);
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnWorldReady() : System.Void`  

```csharp
protected virtual System.Void OnWorldReady();
```

- `public ResetDependency() : System.Void`  

```csharp
public System.Void ResetDependency();
```

- `private WorldReady() : System.Void`  

```csharp
private System.Void WorldReady();
```



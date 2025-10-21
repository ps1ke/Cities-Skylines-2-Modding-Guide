# Game.Prefabs.UnlockSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UnlockSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_LockedQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private System.Boolean m_Loaded;
    private Colossal.Logging.ILog m_Log;
    private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle;

    public UnlockSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    public System.Boolean IsLocked(Game.Prefabs.PrefabBase prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private System.Boolean ProcessEvents();
    private System.Void UnlockPrefab(Unity.Entities.Entity unlock, System.Boolean createEvent);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_LockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Colossal.Logging.ILog m_Log`  

```csharp
private Colossal.Logging.ILog m_Log;
```

- `private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.UnlockSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UnlockSystem()`  

```csharp
public UnlockSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public IsLocked(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean IsLocked(Game.Prefabs.PrefabBase prefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessEvents() : System.Boolean`  

```csharp
private System.Boolean ProcessEvents();
```

- `private UnlockPrefab(Unity.Entities.Entity unlock, System.Boolean createEvent) : System.Void`  

```csharp
private System.Void UnlockPrefab(Unity.Entities.Entity unlock, System.Boolean createEvent);
```


## Nested types

- `Game.Prefabs.UnlockSystem+CheckUnlockRequirementsJob`  
- `Game.Prefabs.UnlockSystem+TypeHandle`  


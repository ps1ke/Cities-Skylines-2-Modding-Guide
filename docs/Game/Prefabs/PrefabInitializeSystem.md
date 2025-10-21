# Game.Prefabs.PrefabInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle;

    public PrefabInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void InitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.Queue<Game.Prefabs.PrefabInitializeSystem+QueueItem> queue, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabSet, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
    private System.Void LateInitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.PrefabInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrefabInitializeSystem()`  

```csharp
public PrefabInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private InitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.Queue<Game.Prefabs.PrefabInitializeSystem+QueueItem> queue, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabSet, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Void`  

```csharp
private System.Void InitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.Queue<Game.Prefabs.PrefabInitializeSystem+QueueItem> queue, System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> prefabSet, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
```

- `private LateInitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Void`  

```csharp
private System.Void LateInitializePrefab(Unity.Entities.Entity entity, Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Prefabs.PrefabInitializeSystem+ListItem`  
- `Game.Prefabs.PrefabInitializeSystem+QueueItem`  
- `Game.Prefabs.PrefabInitializeSystem+TypeHandle`  


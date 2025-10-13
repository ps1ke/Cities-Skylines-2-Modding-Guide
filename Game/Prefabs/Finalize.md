# Game.Prefabs.ReplacePrefabSystem+Finalize

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class Finalize : Game.GameSystemBase
{
    private Game.Prefabs.ReplacePrefabSystem m_ReplacePrefabSystem;
    private Unity.Entities.EntityQuery m_LaneContainerQuery;
    private Game.Prefabs.ReplacePrefabSystem+Finalize+TypeHandle __TypeHandle;

    public Finalize();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.ReplacePrefabSystem m_ReplacePrefabSystem`  

```csharp
private Game.Prefabs.ReplacePrefabSystem m_ReplacePrefabSystem;
```

- `private Unity.Entities.EntityQuery m_LaneContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneContainerQuery;
```

- `private Game.Prefabs.ReplacePrefabSystem+Finalize+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ReplacePrefabSystem+Finalize+TypeHandle __TypeHandle;
```


## Constructors

- `public Finalize()`  

```csharp
public Finalize();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Prefabs.ReplacePrefabSystem+Finalize+AreaKey`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize+NetKey`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize+UpdateInstanceElementsJob`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize+CheckPrefabReplacesJob`  
- `Game.Prefabs.ReplacePrefabSystem+Finalize+TypeHandle`  


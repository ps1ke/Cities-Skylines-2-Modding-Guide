# Game.Pathfind.LanesModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LanesModifiedSystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_CreatedLanesQuery;
    private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
    private Unity.Entities.EntityQuery m_DeletedLanesQuery;
    private Unity.Entities.EntityQuery m_AllLanesQuery;
    private System.Boolean m_Loaded;
    private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle;

    public LanesModifiedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_AllLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLanesQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LanesModifiedSystem()`  

```csharp
public LanesModifiedSystem();
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

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Pathfind.LanesModifiedSystem+AddPathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+UpdatePathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+RemovePathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+TypeHandle`  


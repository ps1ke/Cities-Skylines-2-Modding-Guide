# Game.Pathfind.RoutesModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoutesModifiedSystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_CreatedSubElementQuery;
    private Unity.Entities.EntityQuery m_UpdatedSubElementQuery;
    private Unity.Entities.EntityQuery m_DeletedSubElementQuery;
    private Unity.Entities.EntityQuery m_AllSubElementQuery;
    private System.Boolean m_Loaded;
    private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle;

    public RoutesModifiedSystem();

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

- `private Unity.Entities.EntityQuery m_CreatedSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedSubElementQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSubElementQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedSubElementQuery;
```

- `private Unity.Entities.EntityQuery m_AllSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllSubElementQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoutesModifiedSystem()`  

```csharp
public RoutesModifiedSystem();
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

- `Game.Pathfind.RoutesModifiedSystem+AddPathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+UpdatePathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+RemovePathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+TypeHandle`  


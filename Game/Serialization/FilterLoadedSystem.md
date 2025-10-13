# Game.Serialization.FilterLoadedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FilterLoadedSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_NetLaneQuery;
    private Unity.Entities.EntityQuery m_EditorContainerQuery;
    private Game.Serialization.FilterLoadedSystem+TypeHandle __TypeHandle;

    public FilterLoadedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_NetLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetLaneQuery;
```

- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EditorContainerQuery;
```

- `private Game.Serialization.FilterLoadedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.FilterLoadedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FilterLoadedSystem()`  

```csharp
public FilterLoadedSystem();
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

- `Game.Serialization.FilterLoadedSystem+CheckLanesJob`  
- `Game.Serialization.FilterLoadedSystem+TypeHandle`  


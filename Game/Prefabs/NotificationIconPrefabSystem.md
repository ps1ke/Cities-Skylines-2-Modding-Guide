# Game.Prefabs.NotificationIconPrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconPrefabSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.NotificationIconRenderSystem m_NotificationIconRenderSystem;
    private Game.Prefabs.NotificationIconPrefabSystem+TypeHandle __TypeHandle;

    public NotificationIconPrefabSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.NotificationIconRenderSystem m_NotificationIconRenderSystem`  

```csharp
private Game.Rendering.NotificationIconRenderSystem m_NotificationIconRenderSystem;
```

- `private Game.Prefabs.NotificationIconPrefabSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NotificationIconPrefabSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconPrefabSystem()`  

```csharp
public NotificationIconPrefabSystem();
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

- `Game.Prefabs.NotificationIconPrefabSystem+TypeHandle`  


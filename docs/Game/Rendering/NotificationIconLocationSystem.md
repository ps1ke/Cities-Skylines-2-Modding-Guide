# Game.Rendering.NotificationIconLocationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconLocationSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_IconQuery;
    private Game.Rendering.NotificationIconLocationSystem+TypeHandle __TypeHandle;

    public NotificationIconLocationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Game.Rendering.NotificationIconLocationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NotificationIconLocationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconLocationSystem()`  

```csharp
public NotificationIconLocationSystem();
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

- `Game.Rendering.NotificationIconLocationSystem+NotificationIconMoveJob`  
- `Game.Rendering.NotificationIconLocationSystem+TypeHandle`  


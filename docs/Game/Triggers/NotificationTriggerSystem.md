# Game.Triggers.NotificationTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationTriggerSystem : Game.GameSystemBase
{
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_CreatedNotificationsQuery;
    private Unity.Entities.EntityQuery m_DeletedNotificationsQuery;
    private Unity.Entities.EntityQuery m_AllNotificationsQuery;
    private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle;

    public NotificationTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedNotificationsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedNotificationsQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedNotificationsQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedNotificationsQuery;
```

- `private Unity.Entities.EntityQuery m_AllNotificationsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllNotificationsQuery;
```

- `private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationTriggerSystem()`  

```csharp
public NotificationTriggerSystem();
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Triggers.NotificationTriggerSystem+TriggerJob`  
- `Game.Triggers.NotificationTriggerSystem+TypeHandle`  


# Game.UI.InGame.NotificationsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult;
    private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult;
    private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set; }

    public NotificationsSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Collections.NativeList<Game.UI.InGame.Notification> GetNotifications(Unity.Entities.EntityManager EntityManager, Unity.Entities.Entity entity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications);
    public static Unity.Collections.NativeList<Game.UI.InGame.Notification> GetNotifications(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefDataFromEntity, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBufferFromEntity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications);
    public static System.Boolean HasNotifications(Unity.Entities.Entity entity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBuffer, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult;
```

- `private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set; }
```


## Constructors

- `public NotificationsSection()`  

```csharp
public NotificationsSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetNotifications(Unity.Entities.EntityManager EntityManager, Unity.Entities.Entity entity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications) : Unity.Collections.NativeList<Game.UI.InGame.Notification>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.InGame.Notification> GetNotifications(Unity.Entities.EntityManager EntityManager, Unity.Entities.Entity entity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications);
```

- `public static GetNotifications(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefDataFromEntity, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBufferFromEntity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications) : Unity.Collections.NativeList<Game.UI.InGame.Notification>`  

```csharp
public static Unity.Collections.NativeList<Game.UI.InGame.Notification> GetNotifications(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefDataFromEntity, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBufferFromEntity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications);
```

- `public static HasNotifications(Unity.Entities.Entity entity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBuffer, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity) : System.Boolean`  

```csharp
public static System.Boolean HasNotifications(Unity.Entities.Entity entity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBuffer, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```


## Nested types

- `Game.UI.InGame.NotificationsSection+CheckAndCacheNotificationsJob`  
- `Game.UI.InGame.NotificationsSection+CheckAndCacheVisitorNotificationsJob`  
- `Game.UI.InGame.NotificationsSection+TypeHandle`  


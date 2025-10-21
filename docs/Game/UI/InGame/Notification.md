# Game.UI.InGame.Notification

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Notification
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    private readonly Unity.Entities.Entity <target>k__BackingField;
    private readonly Game.Notifications.IconPriority <priority>k__BackingField;

    public Unity.Entities.Entity entity { get; }
    public Unity.Entities.Entity target { get; }
    public Game.Notifications.IconPriority priority { get; }

    public Notification(Unity.Entities.Entity entity, Unity.Entities.Entity target, Game.Notifications.IconPriority priority);

}
```


## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```

- `private readonly Unity.Entities.Entity <target>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <target>k__BackingField;
```

- `private readonly Game.Notifications.IconPriority <priority>k__BackingField`  

```csharp
private readonly Game.Notifications.IconPriority <priority>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```

- `public Unity.Entities.Entity target { get }`  

```csharp
public Unity.Entities.Entity target { get; }
```

- `public Game.Notifications.IconPriority priority { get }`  

```csharp
public Game.Notifications.IconPriority priority { get; }
```


## Constructors

- `public Notification(Unity.Entities.Entity entity, Unity.Entities.Entity target, Game.Notifications.IconPriority priority)`  

```csharp
public Notification(Unity.Entities.Entity entity, Unity.Entities.Entity target, Game.Notifications.IconPriority priority);
```



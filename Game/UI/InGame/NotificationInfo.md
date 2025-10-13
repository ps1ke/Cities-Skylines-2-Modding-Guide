# Game.UI.InGame.NotificationInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Game.UI.InGame.NotificationInfo>`  

## Code

```csharp
public class NotificationInfo : System.IComparable<Game.UI.InGame.NotificationInfo>
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    private readonly Unity.Entities.Entity <target>k__BackingField;
    private readonly System.Int32 <priority>k__BackingField;
    private readonly System.Collections.Generic.List<Unity.Entities.Entity> m_Targets;

    public Unity.Entities.Entity entity { get; }
    public Unity.Entities.Entity target { get; }
    public System.Int32 priority { get; }
    public System.Int32 count { get; }

    public NotificationInfo(Game.UI.InGame.Notification notification);

    public System.Void AddTarget(Unity.Entities.Entity otherTarget);
    public System.Int32 CompareTo(Game.UI.InGame.NotificationInfo other);
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

- `private readonly System.Int32 <priority>k__BackingField`  

```csharp
private readonly System.Int32 <priority>k__BackingField;
```

- `private readonly System.Collections.Generic.List<Unity.Entities.Entity> m_Targets`  

```csharp
private readonly System.Collections.Generic.List<Unity.Entities.Entity> m_Targets;
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

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `public NotificationInfo(Game.UI.InGame.Notification notification)`  

```csharp
public NotificationInfo(Notification notification)
	{
		entity = notification.entity;
		target = notification.target;
		priority = (int)notification.priority;
		m_Targets = new List<Entity>(10) { notification.target };
	}
```


## Methods

- `public AddTarget(Unity.Entities.Entity otherTarget) : System.Void`  

```csharp
public void AddTarget(Entity otherTarget)
	{
		if (!m_Targets.Contains(otherTarget))
		{
			m_Targets.Add(otherTarget);
		}
	}
```

- `public CompareTo(Game.UI.InGame.NotificationInfo other) : System.Int32`  

```csharp
public int CompareTo(NotificationInfo other)
	{
		return priority - other.priority;
	}
```



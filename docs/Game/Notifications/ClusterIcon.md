# Game.Notifications.IconClusterSystem+ClusterIcon

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ClusterIcon
{
    private Unity.Entities.Entity m_Icon;
    private Unity.Entities.Entity m_Prefab;
    private Unity.Mathematics.float2 m_Order;
    private Game.Notifications.IconPriority m_Priority;
    private Game.Notifications.IconFlags m_Flags;

    public Unity.Entities.Entity icon { get; }
    public Unity.Entities.Entity prefab { get; }
    public Unity.Mathematics.float2 order { get; }
    public Game.Notifications.IconPriority priority { get; }
    public Game.Notifications.IconFlags flags { get; }

    public ClusterIcon(Unity.Entities.Entity icon, Unity.Entities.Entity prefab, Unity.Mathematics.float2 order, Game.Notifications.IconPriority priority, Game.Notifications.IconFlags flags);

}
```


## Fields

- `private Unity.Entities.Entity m_Icon`  

```csharp
private Unity.Entities.Entity m_Icon;
```

- `private Unity.Entities.Entity m_Prefab`  

```csharp
private Unity.Entities.Entity m_Prefab;
```

- `private Unity.Mathematics.float2 m_Order`  

```csharp
private Unity.Mathematics.float2 m_Order;
```

- `private Game.Notifications.IconPriority m_Priority`  

```csharp
private Game.Notifications.IconPriority m_Priority;
```

- `private Game.Notifications.IconFlags m_Flags`  

```csharp
private Game.Notifications.IconFlags m_Flags;
```


## Properties

- `public Unity.Entities.Entity icon { get }`  

```csharp
public Unity.Entities.Entity icon { get; }
```

- `public Unity.Entities.Entity prefab { get }`  

```csharp
public Unity.Entities.Entity prefab { get; }
```

- `public Unity.Mathematics.float2 order { get }`  

```csharp
public Unity.Mathematics.float2 order { get; }
```

- `public Game.Notifications.IconPriority priority { get }`  

```csharp
public Game.Notifications.IconPriority priority { get; }
```

- `public Game.Notifications.IconFlags flags { get }`  

```csharp
public Game.Notifications.IconFlags flags { get; }
```


## Constructors

- `public ClusterIcon(Unity.Entities.Entity icon, Unity.Entities.Entity prefab, Unity.Mathematics.float2 order, Game.Notifications.IconPriority priority, Game.Notifications.IconFlags flags)`  

```csharp
public ClusterIcon(Unity.Entities.Entity icon, Unity.Entities.Entity prefab, Unity.Mathematics.float2 order, Game.Notifications.IconPriority priority, Game.Notifications.IconFlags flags);
```



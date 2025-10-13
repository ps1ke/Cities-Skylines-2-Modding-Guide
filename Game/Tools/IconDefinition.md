# Game.Tools.IconDefinition

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct IconDefinition : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Mathematics.float3 m_Location;
    public Game.Notifications.IconPriority m_Priority;
    public Game.Notifications.IconClusterLayer m_ClusterLayer;
    public Game.Notifications.IconFlags m_Flags;

    public IconDefinition(Game.Notifications.Icon icon);

}
```


## Fields

- `public Unity.Mathematics.float3 m_Location`  

```csharp
public Unity.Mathematics.float3 m_Location;
```

- `public Game.Notifications.IconPriority m_Priority`  

```csharp
public Game.Notifications.IconPriority m_Priority;
```

- `public Game.Notifications.IconClusterLayer m_ClusterLayer`  

```csharp
public Game.Notifications.IconClusterLayer m_ClusterLayer;
```

- `public Game.Notifications.IconFlags m_Flags`  

```csharp
public Game.Notifications.IconFlags m_Flags;
```


## Constructors

- `public IconDefinition(Game.Notifications.Icon icon)`  

```csharp
public IconDefinition(Game.Notifications.Icon icon);
```



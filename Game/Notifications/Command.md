# Game.Notifications.IconCommandBuffer+Command

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Notifications.IconCommandBuffer+Command>`  

## Code

```csharp
public sealed struct Command : System.IComparable<Game.Notifications.IconCommandBuffer+Command>
{
    public Unity.Entities.Entity m_Owner;
    public Unity.Entities.Entity m_Prefab;
    public Unity.Entities.Entity m_Target;
    public Unity.Mathematics.float3 m_Location;
    public Game.Notifications.IconCommandBuffer+CommandFlags m_CommandFlags;
    public Game.Notifications.IconPriority m_Priority;
    public Game.Notifications.IconClusterLayer m_ClusterLayer;
    public Game.Notifications.IconFlags m_Flags;
    public System.Int32 m_BufferIndex;
    public System.Single m_Delay;

    public System.Int32 CompareTo(Game.Notifications.IconCommandBuffer+Command other);
}
```


## Fields

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Unity.Mathematics.float3 m_Location`  

```csharp
public Unity.Mathematics.float3 m_Location;
```

- `public Game.Notifications.IconCommandBuffer+CommandFlags m_CommandFlags`  

```csharp
public Game.Notifications.IconCommandBuffer+CommandFlags m_CommandFlags;
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

- `public System.Int32 m_BufferIndex`  

```csharp
public System.Int32 m_BufferIndex;
```

- `public System.Single m_Delay`  

```csharp
public System.Single m_Delay;
```


## Methods

- `public CompareTo(Game.Notifications.IconCommandBuffer+Command other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Notifications.IconCommandBuffer+Command other);
```



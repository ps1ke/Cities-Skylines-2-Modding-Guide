# Game.Notifications.Icon

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Notifications.Icon>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Icon : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Notifications.Icon>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Location;
    public Game.Notifications.IconPriority m_Priority;
    public Game.Notifications.IconClusterLayer m_ClusterLayer;
    public Game.Notifications.IconFlags m_Flags;
    public System.Int32 m_ClusterIndex;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Notifications.Icon other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
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

- `public System.Int32 m_ClusterIndex`  

```csharp
public System.Int32 m_ClusterIndex;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Notifications.Icon other) : System.Boolean`  

```csharp
public bool Equals(Icon other)
	{
		return m_Location.Equals(other.m_Location) & (m_Priority == other.m_Priority) & (m_ClusterLayer == other.m_ClusterLayer) & (m_Flags == other.m_Flags);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Location.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



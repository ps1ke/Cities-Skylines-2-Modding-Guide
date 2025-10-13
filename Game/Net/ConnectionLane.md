# Game.Net.ConnectionLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `System.IEquatable<Game.Net.ConnectionLane>`  

## Code

```csharp
public sealed struct ConnectionLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, System.IEquatable<Game.Net.ConnectionLane>
{
    public Unity.Entities.Entity m_AccessRestriction;
    public Game.Net.ConnectionLaneFlags m_Flags;
    public Game.Net.TrackTypes m_TrackTypes;
    public Game.Net.RoadTypes m_RoadTypes;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Net.ConnectionLane other);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_AccessRestriction`  

```csharp
public Unity.Entities.Entity m_AccessRestriction;
```

- `public Game.Net.ConnectionLaneFlags m_Flags`  

```csharp
public Game.Net.ConnectionLaneFlags m_Flags;
```

- `public Game.Net.TrackTypes m_TrackTypes`  

```csharp
public Game.Net.TrackTypes m_TrackTypes;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Net.ConnectionLane other) : System.Boolean`  

```csharp
public bool Equals(ConnectionLane other)
	{
		if (m_Flags == other.m_Flags && m_TrackTypes == other.m_TrackTypes)
		{
			return m_RoadTypes == other.m_RoadTypes;
		}
		return false;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



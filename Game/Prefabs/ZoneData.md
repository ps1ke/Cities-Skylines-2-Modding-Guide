# Game.Prefabs.ZoneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ZoneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Zones.ZoneType m_ZoneType;
    public Game.Zones.AreaType m_AreaType;
    public Game.Prefabs.ZoneFlags m_ZoneFlags;
    public System.UInt16 m_MinOddHeight;
    public System.UInt16 m_MinEvenHeight;
    public System.UInt16 m_MaxHeight;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean IsOffice();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Zones.ZoneType m_ZoneType`  

```csharp
public Game.Zones.ZoneType m_ZoneType;
```

- `public Game.Zones.AreaType m_AreaType`  

```csharp
public Game.Zones.AreaType m_AreaType;
```

- `public Game.Prefabs.ZoneFlags m_ZoneFlags`  

```csharp
public Game.Prefabs.ZoneFlags m_ZoneFlags;
```

- `public System.UInt16 m_MinOddHeight`  

```csharp
public System.UInt16 m_MinOddHeight;
```

- `public System.UInt16 m_MinEvenHeight`  

```csharp
public System.UInt16 m_MinEvenHeight;
```

- `public System.UInt16 m_MaxHeight`  

```csharp
public System.UInt16 m_MaxHeight;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public IsOffice() : System.Boolean`  

```csharp
public bool IsOffice()
	{
		return (m_ZoneFlags & ZoneFlags.Office) != 0;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



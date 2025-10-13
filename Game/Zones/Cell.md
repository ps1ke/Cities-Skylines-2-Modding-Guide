# Game.Zones.Cell

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Cell : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Game.Zones.CellFlags m_State;
    public Game.Zones.ZoneType m_Zone;
    public System.Int16 m_Height;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Zones.CellFlags m_State`  

```csharp
public Game.Zones.CellFlags m_State;
```

- `public Game.Zones.ZoneType m_Zone`  

```csharp
public Game.Zones.ZoneType m_Zone;
```

- `public System.Int16 m_Height`  

```csharp
public System.Int16 m_Height;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		if (context.version >= Version.zoneHeightLimit)
		{
			return 4 + m_Zone.GetStride(context);
		}
		return 2 + m_Zone.GetStride(context);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



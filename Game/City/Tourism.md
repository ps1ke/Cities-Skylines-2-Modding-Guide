# Game.City.Tourism

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Tourism : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_CurrentTourists;
    public System.Int32 m_AverageTourists;
    public System.Int32 m_Attractiveness;
    public Unity.Mathematics.int2 m_Lodging;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public System.Int32 m_CurrentTourists`  

```csharp
public System.Int32 m_CurrentTourists;
```

- `public System.Int32 m_AverageTourists`  

```csharp
public System.Int32 m_AverageTourists;
```

- `public System.Int32 m_Attractiveness`  

```csharp
public System.Int32 m_Attractiveness;
```

- `public Unity.Mathematics.int2 m_Lodging`  

```csharp
public Unity.Mathematics.int2 m_Lodging;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_CurrentTourists = 0;
		m_AverageTourists = 0;
		m_Attractiveness = 0;
		m_Lodging = default(int2);
	}
```



# Game.City.Population

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Population : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Population;
    public System.Int32 m_PopulationWithMoveIn;
    public System.Int32 m_AverageHappiness;
    public System.Int32 m_AverageHealth;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public System.Int32 m_Population`  

```csharp
public System.Int32 m_Population;
```

- `public System.Int32 m_PopulationWithMoveIn`  

```csharp
public System.Int32 m_PopulationWithMoveIn;
```

- `public System.Int32 m_AverageHappiness`  

```csharp
public System.Int32 m_AverageHappiness;
```

- `public System.Int32 m_AverageHealth`  

```csharp
public System.Int32 m_AverageHealth;
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
		m_Population = 0;
		m_PopulationWithMoveIn = 0;
		m_AverageHappiness = 50;
		m_AverageHealth = 50;
	}
```



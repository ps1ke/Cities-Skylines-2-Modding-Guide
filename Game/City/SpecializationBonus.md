# Game.City.SpecializationBonus

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SpecializationBonus : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Value;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetBonus(System.Single maxBonus, System.Int32 coefficient);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `public System.Int32 m_Value`  

```csharp
public System.Int32 m_Value;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetBonus(System.Single maxBonus, System.Int32 coefficient) : System.Single`  

```csharp
public float GetBonus(float maxBonus, int coefficient)
	{
		return maxBonus * (float)m_Value / (float)(m_Value + coefficient);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_Value = 0;
	}
```



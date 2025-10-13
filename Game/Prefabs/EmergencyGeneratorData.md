# Game.Prefabs.EmergencyGeneratorData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.EmergencyGeneratorData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct EmergencyGeneratorData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.EmergencyGeneratorData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_ElectricityProduction;
    public Colossal.Mathematics.Bounds1 m_ActivationThreshold;

    public System.Void Combine(Game.Prefabs.EmergencyGeneratorData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_ElectricityProduction`  

```csharp
public System.Int32 m_ElectricityProduction;
```

- `public Colossal.Mathematics.Bounds1 m_ActivationThreshold`  

```csharp
public Colossal.Mathematics.Bounds1 m_ActivationThreshold;
```


## Methods

- `public Combine(Game.Prefabs.EmergencyGeneratorData otherData) : System.Void`  

```csharp
public void Combine(EmergencyGeneratorData otherData)
	{
		m_ElectricityProduction += otherData.m_ElectricityProduction;
		m_ActivationThreshold = new Bounds1(math.max(otherData.m_ActivationThreshold.min, m_ActivationThreshold.min), math.max(otherData.m_ActivationThreshold.max, m_ActivationThreshold.max));
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



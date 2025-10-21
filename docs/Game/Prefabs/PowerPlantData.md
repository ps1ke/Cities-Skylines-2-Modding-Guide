# Game.Prefabs.PowerPlantData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PowerPlantData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PowerPlantData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.PowerPlantData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_ElectricityProduction;

    public System.Void Combine(Game.Prefabs.PowerPlantData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_ElectricityProduction`  

```csharp
public System.Int32 m_ElectricityProduction;
```


## Methods

- `public Combine(Game.Prefabs.PowerPlantData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.PowerPlantData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



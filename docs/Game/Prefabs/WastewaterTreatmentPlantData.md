# Game.Prefabs.WastewaterTreatmentPlantData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.WastewaterTreatmentPlantData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WastewaterTreatmentPlantData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.WastewaterTreatmentPlantData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Capacity;
    public System.Int32 m_WaterStorage;

    public System.Void Combine(Game.Prefabs.WastewaterTreatmentPlantData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Int32 m_WaterStorage`  

```csharp
public System.Int32 m_WaterStorage;
```


## Methods

- `public Combine(Game.Prefabs.WastewaterTreatmentPlantData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.WastewaterTreatmentPlantData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



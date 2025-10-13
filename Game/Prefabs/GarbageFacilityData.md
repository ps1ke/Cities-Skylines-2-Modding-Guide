# Game.Prefabs.GarbageFacilityData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.GarbageFacilityData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageFacilityData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.GarbageFacilityData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_GarbageCapacity;
    public System.Int32 m_VehicleCapacity;
    public System.Int32 m_TransportCapacity;
    public System.Int32 m_ProcessingSpeed;
    public System.Boolean m_IndustrialWasteOnly;
    public System.Boolean m_LongTermStorage;

    public System.Void Combine(Game.Prefabs.GarbageFacilityData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_GarbageCapacity`  

```csharp
public System.Int32 m_GarbageCapacity;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Int32 m_TransportCapacity`  

```csharp
public System.Int32 m_TransportCapacity;
```

- `public System.Int32 m_ProcessingSpeed`  

```csharp
public System.Int32 m_ProcessingSpeed;
```

- `public System.Boolean m_IndustrialWasteOnly`  

```csharp
public System.Boolean m_IndustrialWasteOnly;
```

- `public System.Boolean m_LongTermStorage`  

```csharp
public System.Boolean m_LongTermStorage;
```


## Methods

- `public Combine(Game.Prefabs.GarbageFacilityData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.GarbageFacilityData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



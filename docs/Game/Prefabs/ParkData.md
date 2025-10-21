# Game.Prefabs.ParkData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.ParkData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ParkData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.ParkData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int16 m_MaintenancePool;
    public System.Boolean m_AllowHomeless;

    public System.Void Combine(Game.Prefabs.ParkData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int16 m_MaintenancePool`  

```csharp
public System.Int16 m_MaintenancePool;
```

- `public System.Boolean m_AllowHomeless`  

```csharp
public System.Boolean m_AllowHomeless;
```


## Methods

- `public Combine(Game.Prefabs.ParkData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.ParkData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



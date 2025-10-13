# Game.Prefabs.WorkVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WorkVehicleData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.VehicleWorkType m_WorkType;
    public Game.Areas.MapFeature m_MapFeature;
    public Game.Economy.Resource m_Resources;
    public System.Single m_MaxWorkAmount;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.VehicleWorkType m_WorkType`  

```csharp
public Game.Vehicles.VehicleWorkType m_WorkType;
```

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public Game.Economy.Resource m_Resources`  

```csharp
public Game.Economy.Resource m_Resources;
```

- `public System.Single m_MaxWorkAmount`  

```csharp
public System.Single m_MaxWorkAmount;
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



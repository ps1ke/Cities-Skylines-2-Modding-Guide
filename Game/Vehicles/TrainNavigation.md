# Game.Vehicles.TrainNavigation

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrainNavigation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.TrainBogiePosition m_Front;
    public Game.Vehicles.TrainBogiePosition m_Rear;
    public System.Single m_Speed;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.TrainBogiePosition m_Front`  

```csharp
public Game.Vehicles.TrainBogiePosition m_Front;
```

- `public Game.Vehicles.TrainBogiePosition m_Rear`  

```csharp
public Game.Vehicles.TrainBogiePosition m_Rear;
```

- `public System.Single m_Speed`  

```csharp
public System.Single m_Speed;
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



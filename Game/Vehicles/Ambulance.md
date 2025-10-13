# Game.Vehicles.Ambulance

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Ambulance : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.AmbulanceFlags m_State;
    public Unity.Entities.Entity m_TargetPatient;
    public Unity.Entities.Entity m_TargetLocation;
    public Unity.Entities.Entity m_TargetRequest;
    public System.Single m_PathElementTime;

    public Ambulance(Unity.Entities.Entity targetPatient, Unity.Entities.Entity targetLocation, Game.Vehicles.AmbulanceFlags state);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.AmbulanceFlags m_State`  

```csharp
public Game.Vehicles.AmbulanceFlags m_State;
```

- `public Unity.Entities.Entity m_TargetPatient`  

```csharp
public Unity.Entities.Entity m_TargetPatient;
```

- `public Unity.Entities.Entity m_TargetLocation`  

```csharp
public Unity.Entities.Entity m_TargetLocation;
```

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```


## Constructors

- `public Ambulance(Unity.Entities.Entity targetPatient, Unity.Entities.Entity targetLocation, Game.Vehicles.AmbulanceFlags state)`  

```csharp
public Ambulance(Entity targetPatient, Entity targetLocation, AmbulanceFlags state)
	{
		m_State = state;
		m_TargetPatient = targetPatient;
		m_TargetLocation = targetLocation;
		m_TargetRequest = Entity.Null;
		m_PathElementTime = 0f;
	}
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



# Game.Vehicles.WorkVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WorkVehicle : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.WorkVehicleFlags m_State;
    public System.Single m_WorkAmount;
    public System.Single m_DoneAmount;

    public WorkVehicle(Game.Vehicles.WorkVehicleFlags flags, System.Single workAmount);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.WorkVehicleFlags m_State`  

```csharp
public Game.Vehicles.WorkVehicleFlags m_State;
```

- `public System.Single m_WorkAmount`  

```csharp
public System.Single m_WorkAmount;
```

- `public System.Single m_DoneAmount`  

```csharp
public System.Single m_DoneAmount;
```


## Constructors

- `public WorkVehicle(Game.Vehicles.WorkVehicleFlags flags, System.Single workAmount)`  

```csharp
public WorkVehicle(WorkVehicleFlags flags, float workAmount)
	{
		m_State = flags;
		m_WorkAmount = workAmount;
		m_DoneAmount = 0f;
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



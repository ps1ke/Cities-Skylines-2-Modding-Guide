# Game.Simulation.FireRescueRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FireRescueRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public System.Single m_Priority;
    public Game.Simulation.FireRescueRequestType m_Type;

    public FireRescueRequest(Unity.Entities.Entity target, System.Single priority, Game.Simulation.FireRescueRequestType type);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public System.Single m_Priority`  

```csharp
public System.Single m_Priority;
```

- `public Game.Simulation.FireRescueRequestType m_Type`  

```csharp
public Game.Simulation.FireRescueRequestType m_Type;
```


## Constructors

- `public FireRescueRequest(Unity.Entities.Entity target, System.Single priority, Game.Simulation.FireRescueRequestType type)`  

```csharp
public FireRescueRequest(Entity target, float priority, FireRescueRequestType type)
	{
		m_Target = target;
		m_Priority = priority;
		m_Type = type;
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



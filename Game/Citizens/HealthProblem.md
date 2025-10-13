# Game.Citizens.HealthProblem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HealthProblem : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_HealthcareRequest;
    public Game.Citizens.HealthProblemFlags m_Flags;
    public System.Byte m_Timer;

    public HealthProblem(Unity.Entities.Entity _event, Game.Citizens.HealthProblemFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public Unity.Entities.Entity m_HealthcareRequest`  

```csharp
public Unity.Entities.Entity m_HealthcareRequest;
```

- `public Game.Citizens.HealthProblemFlags m_Flags`  

```csharp
public Game.Citizens.HealthProblemFlags m_Flags;
```

- `public System.Byte m_Timer`  

```csharp
public System.Byte m_Timer;
```


## Constructors

- `public HealthProblem(Unity.Entities.Entity _event, Game.Citizens.HealthProblemFlags flags)`  

```csharp
public HealthProblem(Entity _event, HealthProblemFlags flags)
	{
		m_Event = _event;
		m_HealthcareRequest = Entity.Null;
		m_Flags = flags;
		m_Timer = 0;
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



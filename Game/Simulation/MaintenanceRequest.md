# Game.Simulation.MaintenanceRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct MaintenanceRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public System.Int32 m_Priority;
    public System.Byte m_DispatchIndex;

    public MaintenanceRequest(Unity.Entities.Entity target, System.Int32 priority);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Byte m_DispatchIndex`  

```csharp
public System.Byte m_DispatchIndex;
```


## Constructors

- `public MaintenanceRequest(Unity.Entities.Entity target, System.Int32 priority)`  

```csharp
public MaintenanceRequest(Entity target, int priority)
	{
		m_Target = target;
		m_Priority = priority;
		m_DispatchIndex = 0;
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



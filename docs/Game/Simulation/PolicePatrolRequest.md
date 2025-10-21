# Game.Simulation.PolicePatrolRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PolicePatrolRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public System.Single m_Priority;
    public System.Byte m_DispatchIndex;

    public PolicePatrolRequest(Unity.Entities.Entity target, System.Single priority);

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

- `public System.Byte m_DispatchIndex`  

```csharp
public System.Byte m_DispatchIndex;
```


## Constructors

- `public PolicePatrolRequest(Unity.Entities.Entity target, System.Single priority)`  

```csharp
public PolicePatrolRequest(Unity.Entities.Entity target, System.Single priority);
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



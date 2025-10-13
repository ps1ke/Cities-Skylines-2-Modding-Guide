# Game.Simulation.PoliceEmergencyRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PoliceEmergencyRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Site;
    public Unity.Entities.Entity m_Target;
    public System.Single m_Priority;
    public Game.Prefabs.PolicePurpose m_Purpose;

    public PoliceEmergencyRequest(Unity.Entities.Entity site, Unity.Entities.Entity target, System.Single priority, Game.Prefabs.PolicePurpose purpose);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Site`  

```csharp
public Unity.Entities.Entity m_Site;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public System.Single m_Priority`  

```csharp
public System.Single m_Priority;
```

- `public Game.Prefabs.PolicePurpose m_Purpose`  

```csharp
public Game.Prefabs.PolicePurpose m_Purpose;
```


## Constructors

- `public PoliceEmergencyRequest(Unity.Entities.Entity site, Unity.Entities.Entity target, System.Single priority, Game.Prefabs.PolicePurpose purpose)`  

```csharp
public PoliceEmergencyRequest(Unity.Entities.Entity site, Unity.Entities.Entity target, System.Single priority, Game.Prefabs.PolicePurpose purpose);
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



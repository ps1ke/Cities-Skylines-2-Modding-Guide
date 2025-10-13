# Game.Prefabs.AircraftData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AircraftData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Single m_GroundMaxSpeed;
    public System.Single m_GroundAcceleration;
    public System.Single m_GroundBraking;
    public Unity.Mathematics.float2 m_GroundTurning;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Single m_GroundMaxSpeed`  

```csharp
public System.Single m_GroundMaxSpeed;
```

- `public System.Single m_GroundAcceleration`  

```csharp
public System.Single m_GroundAcceleration;
```

- `public System.Single m_GroundBraking`  

```csharp
public System.Single m_GroundBraking;
```

- `public Unity.Mathematics.float2 m_GroundTurning`  

```csharp
public Unity.Mathematics.float2 m_GroundTurning;
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



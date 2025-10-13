# Game.Prefabs.HelicopterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HelicopterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.HelicopterType m_HelicopterType;
    public System.Single m_FlyingMaxSpeed;
    public System.Single m_FlyingAcceleration;
    public System.Single m_FlyingAngularAcceleration;
    public System.Single m_AccelerationSwayFactor;
    public System.Single m_VelocitySwayFactor;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.HelicopterType m_HelicopterType`  

```csharp
public Game.Vehicles.HelicopterType m_HelicopterType;
```

- `public System.Single m_FlyingMaxSpeed`  

```csharp
public System.Single m_FlyingMaxSpeed;
```

- `public System.Single m_FlyingAcceleration`  

```csharp
public System.Single m_FlyingAcceleration;
```

- `public System.Single m_FlyingAngularAcceleration`  

```csharp
public System.Single m_FlyingAngularAcceleration;
```

- `public System.Single m_AccelerationSwayFactor`  

```csharp
public System.Single m_AccelerationSwayFactor;
```

- `public System.Single m_VelocitySwayFactor`  

```csharp
public System.Single m_VelocitySwayFactor;
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



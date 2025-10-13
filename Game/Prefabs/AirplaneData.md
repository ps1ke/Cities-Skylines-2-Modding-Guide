# Game.Prefabs.AirplaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AirplaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float2 m_FlyingSpeed;
    public System.Single m_FlyingAcceleration;
    public System.Single m_FlyingBraking;
    public System.Single m_FlyingTurning;
    public System.Single m_FlyingAngularAcceleration;
    public System.Single m_ClimbAngle;
    public System.Single m_SlowPitchAngle;
    public System.Single m_TurningRollFactor;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float2 m_FlyingSpeed`  

```csharp
public Unity.Mathematics.float2 m_FlyingSpeed;
```

- `public System.Single m_FlyingAcceleration`  

```csharp
public System.Single m_FlyingAcceleration;
```

- `public System.Single m_FlyingBraking`  

```csharp
public System.Single m_FlyingBraking;
```

- `public System.Single m_FlyingTurning`  

```csharp
public System.Single m_FlyingTurning;
```

- `public System.Single m_FlyingAngularAcceleration`  

```csharp
public System.Single m_FlyingAngularAcceleration;
```

- `public System.Single m_ClimbAngle`  

```csharp
public System.Single m_ClimbAngle;
```

- `public System.Single m_SlowPitchAngle`  

```csharp
public System.Single m_SlowPitchAngle;
```

- `public System.Single m_TurningRollFactor`  

```csharp
public System.Single m_TurningRollFactor;
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



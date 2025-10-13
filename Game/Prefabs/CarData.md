# Game.Prefabs.CarData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CarData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.SizeClass m_SizeClass;
    public Game.Vehicles.EnergyTypes m_EnergyType;
    public System.Single m_MaxSpeed;
    public System.Single m_Acceleration;
    public System.Single m_Braking;
    public System.Single m_PivotOffset;
    public Unity.Mathematics.float2 m_Turning;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public Game.Vehicles.EnergyTypes m_EnergyType`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyType;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```

- `public System.Single m_Braking`  

```csharp
public System.Single m_Braking;
```

- `public System.Single m_PivotOffset`  

```csharp
public System.Single m_PivotOffset;
```

- `public Unity.Mathematics.float2 m_Turning`  

```csharp
public Unity.Mathematics.float2 m_Turning;
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



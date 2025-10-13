# Game.Vehicles.CarTrailerLane

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CarTrailerLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Entities.Entity m_NextLane;
    public Unity.Mathematics.float2 m_CurvePosition;
    public Unity.Mathematics.float2 m_NextPosition;
    public System.Single m_Duration;
    public System.Single m_Distance;

    public CarTrailerLane(Game.Vehicles.ParkedCar parkedCar);
    public CarTrailerLane(Game.Vehicles.CarCurrentLane currentLane);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Entities.Entity m_NextLane`  

```csharp
public Unity.Entities.Entity m_NextLane;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```

- `public Unity.Mathematics.float2 m_NextPosition`  

```csharp
public Unity.Mathematics.float2 m_NextPosition;
```

- `public System.Single m_Duration`  

```csharp
public System.Single m_Duration;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```


## Constructors

- `public CarTrailerLane(Game.Vehicles.ParkedCar parkedCar)`  

```csharp
public CarTrailerLane(CarCurrentLane currentLane)
	{
		m_Lane = currentLane.m_Lane;
		m_NextLane = Entity.Null;
		m_CurvePosition = currentLane.m_CurvePosition.xy;
		m_NextPosition = 0f;
		m_Duration = 0f;
		m_Distance = 0f;
	}
```

- `public CarTrailerLane(Game.Vehicles.CarCurrentLane currentLane)`  

```csharp
public CarTrailerLane(CarCurrentLane currentLane)
	{
		m_Lane = currentLane.m_Lane;
		m_NextLane = Entity.Null;
		m_CurvePosition = currentLane.m_CurvePosition.xy;
		m_NextPosition = 0f;
		m_Duration = 0f;
		m_Distance = 0f;
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



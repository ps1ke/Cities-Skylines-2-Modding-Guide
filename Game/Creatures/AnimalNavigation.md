# Game.Creatures.AnimalNavigation

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AnimalNavigation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_TargetPosition;
    public Unity.Mathematics.float3 m_TargetDirection;
    public System.Single m_MaxSpeed;
    public Game.Objects.TransformState m_TransformState;
    public System.Byte m_LastActivity;
    public System.Byte m_TargetActivity;

    public AnimalNavigation(Unity.Mathematics.float3 position);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_TargetPosition`  

```csharp
public Unity.Mathematics.float3 m_TargetPosition;
```

- `public Unity.Mathematics.float3 m_TargetDirection`  

```csharp
public Unity.Mathematics.float3 m_TargetDirection;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public Game.Objects.TransformState m_TransformState`  

```csharp
public Game.Objects.TransformState m_TransformState;
```

- `public System.Byte m_LastActivity`  

```csharp
public System.Byte m_LastActivity;
```

- `public System.Byte m_TargetActivity`  

```csharp
public System.Byte m_TargetActivity;
```


## Constructors

- `public AnimalNavigation(Unity.Mathematics.float3 position)`  

```csharp
public AnimalNavigation(float3 position)
	{
		m_TargetPosition = position;
		m_TargetDirection = default(float3);
		m_MaxSpeed = 0f;
		m_TransformState = TransformState.Default;
		m_LastActivity = 0;
		m_TargetActivity = 0;
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



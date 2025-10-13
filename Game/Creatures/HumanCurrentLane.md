# Game.Creatures.HumanCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HumanCurrentLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Entities.Entity m_QueueEntity;
    public Colossal.Mathematics.Sphere3 m_QueueArea;
    public Unity.Mathematics.float2 m_CurvePosition;
    public Game.Creatures.CreatureLaneFlags m_Flags;
    public System.Single m_LanePosition;

    public HumanCurrentLane(Game.Routes.AccessLane accessLane, Game.Creatures.CreatureLaneFlags flags);
    public HumanCurrentLane(Game.Pathfind.PathElement pathElement, Game.Creatures.CreatureLaneFlags flags);
    public HumanCurrentLane(Game.Creatures.CreatureLaneFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Entities.Entity m_QueueEntity`  

```csharp
public Unity.Entities.Entity m_QueueEntity;
```

- `public Colossal.Mathematics.Sphere3 m_QueueArea`  

```csharp
public Colossal.Mathematics.Sphere3 m_QueueArea;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```

- `public Game.Creatures.CreatureLaneFlags m_Flags`  

```csharp
public Game.Creatures.CreatureLaneFlags m_Flags;
```

- `public System.Single m_LanePosition`  

```csharp
public System.Single m_LanePosition;
```


## Constructors

- `public HumanCurrentLane(Game.Routes.AccessLane accessLane, Game.Creatures.CreatureLaneFlags flags)`  

```csharp
public HumanCurrentLane(CreatureLaneFlags flags)
	{
		m_Lane = Entity.Null;
		m_QueueEntity = Entity.Null;
		m_QueueArea = default(Sphere3);
		m_CurvePosition = 0f;
		m_Flags = flags;
		m_LanePosition = 0f;
	}
```

- `public HumanCurrentLane(Game.Pathfind.PathElement pathElement, Game.Creatures.CreatureLaneFlags flags)`  

```csharp
public HumanCurrentLane(CreatureLaneFlags flags)
	{
		m_Lane = Entity.Null;
		m_QueueEntity = Entity.Null;
		m_QueueArea = default(Sphere3);
		m_CurvePosition = 0f;
		m_Flags = flags;
		m_LanePosition = 0f;
	}
```

- `public HumanCurrentLane(Game.Creatures.CreatureLaneFlags flags)`  

```csharp
public HumanCurrentLane(CreatureLaneFlags flags)
	{
		m_Lane = Entity.Null;
		m_QueueEntity = Entity.Null;
		m_QueueArea = default(Sphere3);
		m_CurvePosition = 0f;
		m_Flags = flags;
		m_LanePosition = 0f;
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



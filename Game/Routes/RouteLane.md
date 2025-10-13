# Game.Routes.RouteLane

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Routes.RouteLane>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct RouteLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Routes.RouteLane>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_StartLane;
    public Unity.Entities.Entity m_EndLane;
    public System.Single m_StartCurvePos;
    public System.Single m_EndCurvePos;

    public RouteLane(Unity.Entities.Entity startLane, Unity.Entities.Entity endLane, System.Single startCurvePos, System.Single endCurvePos);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Routes.RouteLane other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_StartLane`  

```csharp
public Unity.Entities.Entity m_StartLane;
```

- `public Unity.Entities.Entity m_EndLane`  

```csharp
public Unity.Entities.Entity m_EndLane;
```

- `public System.Single m_StartCurvePos`  

```csharp
public System.Single m_StartCurvePos;
```

- `public System.Single m_EndCurvePos`  

```csharp
public System.Single m_EndCurvePos;
```


## Constructors

- `public RouteLane(Unity.Entities.Entity startLane, Unity.Entities.Entity endLane, System.Single startCurvePos, System.Single endCurvePos)`  

```csharp
public RouteLane(Entity startLane, Entity endLane, float startCurvePos, float endCurvePos)
	{
		m_StartLane = startLane;
		m_EndLane = endLane;
		m_StartCurvePos = startCurvePos;
		m_EndCurvePos = endCurvePos;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Routes.RouteLane other) : System.Boolean`  

```csharp
public bool Equals(RouteLane other)
	{
		if (m_StartLane.Equals(other.m_StartLane) && m_EndLane.Equals(other.m_EndLane) && m_StartCurvePos.Equals(other.m_StartCurvePos))
		{
			return m_EndCurvePos.Equals(other.m_EndCurvePos);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (((17 * 31 + m_StartLane.GetHashCode()) * 31 + m_EndLane.GetHashCode()) * 31 + m_StartCurvePos.GetHashCode()) * 31 + m_EndCurvePos.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```



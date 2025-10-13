# Game.Routes.RouteSegment

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct RouteSegment : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Segment;

    public RouteSegment(Unity.Entities.Entity segment);

}
```


## Fields

- `public Unity.Entities.Entity m_Segment`  

```csharp
public Unity.Entities.Entity m_Segment;
```


## Constructors

- `public RouteSegment(Unity.Entities.Entity segment)`  

```csharp
public RouteSegment(Entity segment)
	{
		m_Segment = segment;
	}
```



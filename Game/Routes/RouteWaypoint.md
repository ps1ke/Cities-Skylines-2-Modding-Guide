# Game.Routes.RouteWaypoint

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct RouteWaypoint : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Waypoint;

    public RouteWaypoint(Unity.Entities.Entity waypoint);

}
```


## Fields

- `public Unity.Entities.Entity m_Waypoint`  

```csharp
public Unity.Entities.Entity m_Waypoint;
```


## Constructors

- `public RouteWaypoint(Unity.Entities.Entity waypoint)`  

```csharp
public RouteWaypoint(Unity.Entities.Entity waypoint);
```



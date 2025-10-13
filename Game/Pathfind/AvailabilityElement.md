# Game.Pathfind.AvailabilityElement

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct AvailabilityElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Edge;
    public Unity.Mathematics.float2 m_Availability;

}
```


## Fields

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```

- `public Unity.Mathematics.float2 m_Availability`  

```csharp
public Unity.Mathematics.float2 m_Availability;
```



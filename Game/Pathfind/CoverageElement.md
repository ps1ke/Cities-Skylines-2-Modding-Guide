# Game.Pathfind.CoverageElement

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct CoverageElement : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Edge;
    public Unity.Mathematics.float2 m_Cost;

}
```


## Fields

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```

- `public Unity.Mathematics.float2 m_Cost`  

```csharp
public Unity.Mathematics.float2 m_Cost;
```



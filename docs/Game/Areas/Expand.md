# Game.Areas.Expand

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Expand : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.float2 m_Offset;

    public Expand(Unity.Mathematics.float2 offset);

}
```


## Fields

- `public Unity.Mathematics.float2 m_Offset`  

```csharp
public Unity.Mathematics.float2 m_Offset;
```


## Constructors

- `public Expand(Unity.Mathematics.float2 offset)`  

```csharp
public Expand(Unity.Mathematics.float2 offset);
```



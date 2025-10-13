# Game.Routes.CurveElement

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct CurveElement : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Mathematics.Bezier4x3 m_Curve;

}
```


## Fields

- `public Colossal.Mathematics.Bezier4x3 m_Curve`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Curve;
```



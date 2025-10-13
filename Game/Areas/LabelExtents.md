# Game.Areas.LabelExtents

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LabelExtents : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Mathematics.Bounds2 m_Bounds;

    public LabelExtents(Unity.Mathematics.float2 min, Unity.Mathematics.float2 max);

}
```


## Fields

- `public Colossal.Mathematics.Bounds2 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds2 m_Bounds;
```


## Constructors

- `public LabelExtents(Unity.Mathematics.float2 min, Unity.Mathematics.float2 max)`  

```csharp
public LabelExtents(float2 min, float2 max)
	{
		m_Bounds = new Bounds2(min, max);
	}
```



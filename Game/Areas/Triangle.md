# Game.Areas.Triangle

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Triangle : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.int3 m_Indices;
    public Colossal.Mathematics.Bounds1 m_HeightRange;
    public System.Int32 m_MinLod;

    public Triangle(System.Int32 a, System.Int32 b, System.Int32 c);

}
```


## Fields

- `public Unity.Mathematics.int3 m_Indices`  

```csharp
public Unity.Mathematics.int3 m_Indices;
```

- `public Colossal.Mathematics.Bounds1 m_HeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightRange;
```

- `public System.Int32 m_MinLod`  

```csharp
public System.Int32 m_MinLod;
```


## Constructors

- `public Triangle(System.Int32 a, System.Int32 b, System.Int32 c)`  

```csharp
public Triangle(int a, int b, int c)
	{
		m_Indices = new int3(a, b, c);
		m_HeightRange = default(Bounds1);
		m_MinLod = 0;
	}
```



# Game.Net.LabelPosition

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LabelPosition : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Mathematics.Bezier4x3 m_Curve;
    public System.Int32 m_ElementIndex;
    public System.Single m_HalfLength;
    public System.Single m_MaxScale;
    public System.Boolean m_IsUnderground;

}
```


## Fields

- `public Colossal.Mathematics.Bezier4x3 m_Curve`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Curve;
```

- `public System.Int32 m_ElementIndex`  

```csharp
public System.Int32 m_ElementIndex;
```

- `public System.Single m_HalfLength`  

```csharp
public System.Single m_HalfLength;
```

- `public System.Single m_MaxScale`  

```csharp
public System.Single m_MaxScale;
```

- `public System.Boolean m_IsUnderground`  

```csharp
public System.Boolean m_IsUnderground;
```



# Game.Rendering.CullingInfo

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct CullingInfo : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public System.Single m_Radius;
    public System.Int32 m_CullingIndex;
    public Game.Common.BoundsMask m_Mask;
    public System.Byte m_MinLod;
    public System.Byte m_PassedCulling;

}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public System.Single m_Radius`  

```csharp
public System.Single m_Radius;
```

- `public System.Int32 m_CullingIndex`  

```csharp
public System.Int32 m_CullingIndex;
```

- `public Game.Common.BoundsMask m_Mask`  

```csharp
public Game.Common.BoundsMask m_Mask;
```

- `public System.Byte m_MinLod`  

```csharp
public System.Byte m_MinLod;
```

- `public System.Byte m_PassedCulling`  

```csharp
public System.Byte m_PassedCulling;
```



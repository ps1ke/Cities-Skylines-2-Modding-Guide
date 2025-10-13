# Game.Areas.Geometry

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Geometry : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Unity.Mathematics.float3 m_CenterPosition;
    public System.Single m_SurfaceArea;

}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Unity.Mathematics.float3 m_CenterPosition`  

```csharp
public Unity.Mathematics.float3 m_CenterPosition;
```

- `public System.Single m_SurfaceArea`  

```csharp
public System.Single m_SurfaceArea;
```



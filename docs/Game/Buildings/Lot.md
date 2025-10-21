# Game.Buildings.Lot

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Lot : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.float3 m_FrontHeights;
    public Unity.Mathematics.float3 m_RightHeights;
    public Unity.Mathematics.float3 m_BackHeights;
    public Unity.Mathematics.float3 m_LeftHeights;

}
```


## Fields

- `public Unity.Mathematics.float3 m_FrontHeights`  

```csharp
public Unity.Mathematics.float3 m_FrontHeights;
```

- `public Unity.Mathematics.float3 m_RightHeights`  

```csharp
public Unity.Mathematics.float3 m_RightHeights;
```

- `public Unity.Mathematics.float3 m_BackHeights`  

```csharp
public Unity.Mathematics.float3 m_BackHeights;
```

- `public Unity.Mathematics.float3 m_LeftHeights`  

```csharp
public Unity.Mathematics.float3 m_LeftHeights;
```



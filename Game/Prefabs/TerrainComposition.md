# Game.Prefabs.TerrainComposition

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TerrainComposition : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Mathematics.float2 m_WidthOffset;
    public Unity.Mathematics.float2 m_ClipHeightOffset;
    public Unity.Mathematics.float3 m_MinHeightOffset;
    public Unity.Mathematics.float3 m_MaxHeightOffset;

}
```


## Fields

- `public Unity.Mathematics.float2 m_WidthOffset`  

```csharp
public Unity.Mathematics.float2 m_WidthOffset;
```

- `public Unity.Mathematics.float2 m_ClipHeightOffset`  

```csharp
public Unity.Mathematics.float2 m_ClipHeightOffset;
```

- `public Unity.Mathematics.float3 m_MinHeightOffset`  

```csharp
public Unity.Mathematics.float3 m_MinHeightOffset;
```

- `public Unity.Mathematics.float3 m_MaxHeightOffset`  

```csharp
public Unity.Mathematics.float3 m_MaxHeightOffset;
```



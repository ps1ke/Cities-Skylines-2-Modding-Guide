# Game.Prefabs.SecondaryLaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct SecondaryLaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.SecondaryLaneDataFlags m_Flags;
    public Unity.Mathematics.float3 m_PositionOffset;
    public Unity.Mathematics.float2 m_LengthOffset;
    public System.Single m_CutMargin;
    public System.Single m_CutOffset;
    public System.Single m_CutOverlap;
    public System.Single m_Spacing;

}
```


## Fields

- `public Game.Prefabs.SecondaryLaneDataFlags m_Flags`  

```csharp
public Game.Prefabs.SecondaryLaneDataFlags m_Flags;
```

- `public Unity.Mathematics.float3 m_PositionOffset`  

```csharp
public Unity.Mathematics.float3 m_PositionOffset;
```

- `public Unity.Mathematics.float2 m_LengthOffset`  

```csharp
public Unity.Mathematics.float2 m_LengthOffset;
```

- `public System.Single m_CutMargin`  

```csharp
public System.Single m_CutMargin;
```

- `public System.Single m_CutOffset`  

```csharp
public System.Single m_CutOffset;
```

- `public System.Single m_CutOverlap`  

```csharp
public System.Single m_CutOverlap;
```

- `public System.Single m_Spacing`  

```csharp
public System.Single m_Spacing;
```



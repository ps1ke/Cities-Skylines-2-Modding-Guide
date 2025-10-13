# Game.Simulation.TerrainSystem+LaneSection

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LaneSection
{
    public Colossal.Mathematics.Bounds2 m_Bounds;
    public Unity.Mathematics.float4x3 m_Left;
    public Unity.Mathematics.float4x3 m_Right;
    public Unity.Mathematics.float3 m_MinOffset;
    public Unity.Mathematics.float3 m_MaxOffset;
    public Unity.Mathematics.float2 m_ClipOffset;
    public System.Single m_WidthOffset;
    public System.Single m_MiddleSize;
    public Game.Simulation.TerrainSystem+LaneFlags m_Flags;

}
```


## Fields

- `public Colossal.Mathematics.Bounds2 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds2 m_Bounds;
```

- `public Unity.Mathematics.float4x3 m_Left`  

```csharp
public Unity.Mathematics.float4x3 m_Left;
```

- `public Unity.Mathematics.float4x3 m_Right`  

```csharp
public Unity.Mathematics.float4x3 m_Right;
```

- `public Unity.Mathematics.float3 m_MinOffset`  

```csharp
public Unity.Mathematics.float3 m_MinOffset;
```

- `public Unity.Mathematics.float3 m_MaxOffset`  

```csharp
public Unity.Mathematics.float3 m_MaxOffset;
```

- `public Unity.Mathematics.float2 m_ClipOffset`  

```csharp
public Unity.Mathematics.float2 m_ClipOffset;
```

- `public System.Single m_WidthOffset`  

```csharp
public System.Single m_WidthOffset;
```

- `public System.Single m_MiddleSize`  

```csharp
public System.Single m_MiddleSize;
```

- `public Game.Simulation.TerrainSystem+LaneFlags m_Flags`  

```csharp
public Game.Simulation.TerrainSystem+LaneFlags m_Flags;
```



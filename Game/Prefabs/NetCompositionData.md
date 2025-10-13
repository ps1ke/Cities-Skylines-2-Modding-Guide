# Game.Prefabs.NetCompositionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct NetCompositionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Mathematics.float4 m_SyncVertexOffsetsLeft;
    public Unity.Mathematics.float4 m_SyncVertexOffsetsRight;
    public Colossal.Mathematics.Bounds1 m_HeightRange;
    public Colossal.Mathematics.Bounds1 m_SurfaceHeight;
    public Unity.Mathematics.float4 m_EdgeHeights;
    public Unity.Mathematics.float2 m_RoundaboutSize;
    public Unity.Mathematics.float2 m_SideConnectionOffset;
    public Game.Prefabs.CompositionFlags m_Flags;
    public Game.Prefabs.CompositionState m_State;
    public System.Single m_Width;
    public System.Single m_MiddleOffset;
    public System.Single m_WidthOffset;
    public System.Single m_NodeOffset;
    public System.Int32 m_MinLod;

}
```


## Fields

- `public Unity.Mathematics.float4 m_SyncVertexOffsetsLeft`  

```csharp
public Unity.Mathematics.float4 m_SyncVertexOffsetsLeft;
```

- `public Unity.Mathematics.float4 m_SyncVertexOffsetsRight`  

```csharp
public Unity.Mathematics.float4 m_SyncVertexOffsetsRight;
```

- `public Colossal.Mathematics.Bounds1 m_HeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightRange;
```

- `public Colossal.Mathematics.Bounds1 m_SurfaceHeight`  

```csharp
public Colossal.Mathematics.Bounds1 m_SurfaceHeight;
```

- `public Unity.Mathematics.float4 m_EdgeHeights`  

```csharp
public Unity.Mathematics.float4 m_EdgeHeights;
```

- `public Unity.Mathematics.float2 m_RoundaboutSize`  

```csharp
public Unity.Mathematics.float2 m_RoundaboutSize;
```

- `public Unity.Mathematics.float2 m_SideConnectionOffset`  

```csharp
public Unity.Mathematics.float2 m_SideConnectionOffset;
```

- `public Game.Prefabs.CompositionFlags m_Flags`  

```csharp
public Game.Prefabs.CompositionFlags m_Flags;
```

- `public Game.Prefabs.CompositionState m_State`  

```csharp
public Game.Prefabs.CompositionState m_State;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_MiddleOffset`  

```csharp
public System.Single m_MiddleOffset;
```

- `public System.Single m_WidthOffset`  

```csharp
public System.Single m_WidthOffset;
```

- `public System.Single m_NodeOffset`  

```csharp
public System.Single m_NodeOffset;
```

- `public System.Int32 m_MinLod`  

```csharp
public System.Int32 m_MinLod;
```



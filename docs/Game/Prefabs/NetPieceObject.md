# Game.Prefabs.NetPieceObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetPieceObject : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Offset;
    public Unity.Mathematics.float3 m_Spacing;
    public Unity.Mathematics.float2 m_UseCurveRotation;
    public System.Single m_MinLength;
    public System.Int32 m_Probability;
    public Unity.Mathematics.float2 m_CurveOffsetRange;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Prefabs.CompositionFlags m_CompositionAll;
    public Game.Prefabs.CompositionFlags m_CompositionAny;
    public Game.Prefabs.CompositionFlags m_CompositionNone;
    public Game.Prefabs.NetSectionFlags m_SectionAll;
    public Game.Prefabs.NetSectionFlags m_SectionAny;
    public Game.Prefabs.NetSectionFlags m_SectionNone;
    public Game.Prefabs.SubObjectFlags m_Flags;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```

- `public Unity.Mathematics.float3 m_Spacing`  

```csharp
public Unity.Mathematics.float3 m_Spacing;
```

- `public Unity.Mathematics.float2 m_UseCurveRotation`  

```csharp
public Unity.Mathematics.float2 m_UseCurveRotation;
```

- `public System.Single m_MinLength`  

```csharp
public System.Single m_MinLength;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
```

- `public Unity.Mathematics.float2 m_CurveOffsetRange`  

```csharp
public Unity.Mathematics.float2 m_CurveOffsetRange;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAll`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAll;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAny`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAny;
```

- `public Game.Prefabs.CompositionFlags m_CompositionNone`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionNone;
```

- `public Game.Prefabs.NetSectionFlags m_SectionAll`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionAll;
```

- `public Game.Prefabs.NetSectionFlags m_SectionAny`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionAny;
```

- `public Game.Prefabs.NetSectionFlags m_SectionNone`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionNone;
```

- `public Game.Prefabs.SubObjectFlags m_Flags`  

```csharp
public Game.Prefabs.SubObjectFlags m_Flags;
```



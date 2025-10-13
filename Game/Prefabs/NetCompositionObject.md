# Game.Prefabs.NetCompositionObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetCompositionObject : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float2 m_Position;
    public Unity.Mathematics.float3 m_Offset;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Prefabs.SubObjectFlags m_Flags;
    public Game.Prefabs.CompositionFlags+General m_SpacingIgnore;
    public Unity.Mathematics.float2 m_UseCurveRotation;
    public Unity.Mathematics.float2 m_CurveOffsetRange;
    public System.Int32 m_Probability;
    public System.Single m_Spacing;
    public System.Single m_AvoidSpacing;
    public System.Single m_MinLength;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Mathematics.float2 m_Position`  

```csharp
public Unity.Mathematics.float2 m_Position;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Prefabs.SubObjectFlags m_Flags`  

```csharp
public Game.Prefabs.SubObjectFlags m_Flags;
```

- `public Game.Prefabs.CompositionFlags+General m_SpacingIgnore`  

```csharp
public Game.Prefabs.CompositionFlags+General m_SpacingIgnore;
```

- `public Unity.Mathematics.float2 m_UseCurveRotation`  

```csharp
public Unity.Mathematics.float2 m_UseCurveRotation;
```

- `public Unity.Mathematics.float2 m_CurveOffsetRange`  

```csharp
public Unity.Mathematics.float2 m_CurveOffsetRange;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
```

- `public System.Single m_Spacing`  

```csharp
public System.Single m_Spacing;
```

- `public System.Single m_AvoidSpacing`  

```csharp
public System.Single m_AvoidSpacing;
```

- `public System.Single m_MinLength`  

```csharp
public System.Single m_MinLength;
```



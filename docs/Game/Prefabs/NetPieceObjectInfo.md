# Game.Prefabs.NetPieceObjectInfo

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class NetPieceObjectInfo
{
    public Game.Prefabs.ObjectPrefab m_Object;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Offset;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Prefabs.NetPieceRequirements[] m_RequireAll;
    public Game.Prefabs.NetPieceRequirements[] m_RequireAny;
    public Game.Prefabs.NetPieceRequirements[] m_RequireNone;
    public System.Int32 m_Probability;
    public System.Single m_MinLength;
    public Unity.Mathematics.float2 m_CurveOffsetRange;
    public Unity.Mathematics.float3 m_Spacing;
    public Unity.Mathematics.float2 m_UseCurveRotation;
    public System.Boolean m_FlipWhenInverted;
    public System.Boolean m_EvenSpacing;
    public System.Boolean m_SpacingOverride;

    public NetPieceObjectInfo();

}
```


## Fields

- `public Game.Prefabs.ObjectPrefab m_Object`  

```csharp
public Game.Prefabs.ObjectPrefab m_Object;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Prefabs.NetPieceRequirements[] m_RequireAll`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_RequireAll;
```

- `public Game.Prefabs.NetPieceRequirements[] m_RequireAny`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_RequireAny;
```

- `public Game.Prefabs.NetPieceRequirements[] m_RequireNone`  

```csharp
public Game.Prefabs.NetPieceRequirements[] m_RequireNone;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
```

- `public System.Single m_MinLength`  

```csharp
public System.Single m_MinLength;
```

- `public Unity.Mathematics.float2 m_CurveOffsetRange`  

```csharp
public Unity.Mathematics.float2 m_CurveOffsetRange;
```

- `public Unity.Mathematics.float3 m_Spacing`  

```csharp
public Unity.Mathematics.float3 m_Spacing;
```

- `public Unity.Mathematics.float2 m_UseCurveRotation`  

```csharp
public Unity.Mathematics.float2 m_UseCurveRotation;
```

- `public System.Boolean m_FlipWhenInverted`  

```csharp
public System.Boolean m_FlipWhenInverted;
```

- `public System.Boolean m_EvenSpacing`  

```csharp
public System.Boolean m_EvenSpacing;
```

- `public System.Boolean m_SpacingOverride`  

```csharp
public System.Boolean m_SpacingOverride;
```


## Constructors

- `public NetPieceObjectInfo()`  

```csharp
public NetPieceObjectInfo();
```



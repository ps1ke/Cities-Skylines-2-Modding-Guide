# Game.Rendering.Animated

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Animated : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Colossal.Collections.NativeHeapBlock m_BoneAllocation;
    public System.Int32 m_MetaIndex;
    public Unity.Mathematics.float4 m_Time;
    public Unity.Mathematics.float2 m_MovementSpeed;
    public System.Single m_Interpolation;
    public System.Single m_PreviousTime;
    public System.Int16 m_ClipIndexBody0;
    public System.Int16 m_ClipIndexBody0I;
    public System.Int16 m_ClipIndexBody1;
    public System.Int16 m_ClipIndexBody1I;
    public System.Int16 m_ClipIndexFace0;
    public System.Int16 m_ClipIndexFace1;

}
```


## Fields

- `public Colossal.Collections.NativeHeapBlock m_BoneAllocation`  

```csharp
public Colossal.Collections.NativeHeapBlock m_BoneAllocation;
```

- `public System.Int32 m_MetaIndex`  

```csharp
public System.Int32 m_MetaIndex;
```

- `public Unity.Mathematics.float4 m_Time`  

```csharp
public Unity.Mathematics.float4 m_Time;
```

- `public Unity.Mathematics.float2 m_MovementSpeed`  

```csharp
public Unity.Mathematics.float2 m_MovementSpeed;
```

- `public System.Single m_Interpolation`  

```csharp
public System.Single m_Interpolation;
```

- `public System.Single m_PreviousTime`  

```csharp
public System.Single m_PreviousTime;
```

- `public System.Int16 m_ClipIndexBody0`  

```csharp
public System.Int16 m_ClipIndexBody0;
```

- `public System.Int16 m_ClipIndexBody0I`  

```csharp
public System.Int16 m_ClipIndexBody0I;
```

- `public System.Int16 m_ClipIndexBody1`  

```csharp
public System.Int16 m_ClipIndexBody1;
```

- `public System.Int16 m_ClipIndexBody1I`  

```csharp
public System.Int16 m_ClipIndexBody1I;
```

- `public System.Int16 m_ClipIndexFace0`  

```csharp
public System.Int16 m_ClipIndexFace0;
```

- `public System.Int16 m_ClipIndexFace1`  

```csharp
public System.Int16 m_ClipIndexFace1;
```



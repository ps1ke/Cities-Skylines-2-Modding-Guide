# Game.Prefabs.ProceduralBone

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ProceduralBone : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_ObjectPosition;
    public Unity.Mathematics.quaternion m_Rotation;
    public Unity.Mathematics.quaternion m_ObjectRotation;
    public Unity.Mathematics.float3 m_Scale;
    public Unity.Mathematics.float4x4 m_BindPose;
    public Game.Prefabs.BoneType m_Type;
    public System.Int32 m_ParentIndex;
    public System.Int32 m_BindIndex;
    public System.Int32 m_HierarchyDepth;
    public System.Int32 m_ConnectionID;
    public System.Int32 m_SourceIndex;
    public System.Single m_Speed;
    public System.Single m_Acceleration;

}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_ObjectPosition`  

```csharp
public Unity.Mathematics.float3 m_ObjectPosition;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Unity.Mathematics.quaternion m_ObjectRotation`  

```csharp
public Unity.Mathematics.quaternion m_ObjectRotation;
```

- `public Unity.Mathematics.float3 m_Scale`  

```csharp
public Unity.Mathematics.float3 m_Scale;
```

- `public Unity.Mathematics.float4x4 m_BindPose`  

```csharp
public Unity.Mathematics.float4x4 m_BindPose;
```

- `public Game.Prefabs.BoneType m_Type`  

```csharp
public Game.Prefabs.BoneType m_Type;
```

- `public System.Int32 m_ParentIndex`  

```csharp
public System.Int32 m_ParentIndex;
```

- `public System.Int32 m_BindIndex`  

```csharp
public System.Int32 m_BindIndex;
```

- `public System.Int32 m_HierarchyDepth`  

```csharp
public System.Int32 m_HierarchyDepth;
```

- `public System.Int32 m_ConnectionID`  

```csharp
public System.Int32 m_ConnectionID;
```

- `public System.Int32 m_SourceIndex`  

```csharp
public System.Int32 m_SourceIndex;
```

- `public System.Single m_Speed`  

```csharp
public System.Single m_Speed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```



# Game.Prefabs.Effect

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Effect : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Effect;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Scale;
    public Unity.Mathematics.quaternion m_Rotation;
    public Unity.Mathematics.int2 m_BoneIndex;
    public System.Single m_Intensity;
    public System.Int32 m_ParentMesh;
    public System.Int32 m_AnimationIndex;
    public System.Boolean m_Procedural;

}
```


## Fields

- `public Unity.Entities.Entity m_Effect`  

```csharp
public Unity.Entities.Entity m_Effect;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Scale`  

```csharp
public Unity.Mathematics.float3 m_Scale;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Unity.Mathematics.int2 m_BoneIndex`  

```csharp
public Unity.Mathematics.int2 m_BoneIndex;
```

- `public System.Single m_Intensity`  

```csharp
public System.Single m_Intensity;
```

- `public System.Int32 m_ParentMesh`  

```csharp
public System.Int32 m_ParentMesh;
```

- `public System.Int32 m_AnimationIndex`  

```csharp
public System.Int32 m_AnimationIndex;
```

- `public System.Boolean m_Procedural`  

```csharp
public System.Boolean m_Procedural;
```



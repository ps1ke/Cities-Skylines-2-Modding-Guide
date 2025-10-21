# Game.Prefabs.AnimationMotion

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct AnimationMotion : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float3 m_StartOffset;
    public Unity.Mathematics.float3 m_EndOffset;
    public Unity.Mathematics.quaternion m_StartRotation;
    public Unity.Mathematics.quaternion m_EndRotation;

}
```


## Fields

- `public Unity.Mathematics.float3 m_StartOffset`  

```csharp
public Unity.Mathematics.float3 m_StartOffset;
```

- `public Unity.Mathematics.float3 m_EndOffset`  

```csharp
public Unity.Mathematics.float3 m_EndOffset;
```

- `public Unity.Mathematics.quaternion m_StartRotation`  

```csharp
public Unity.Mathematics.quaternion m_StartRotation;
```

- `public Unity.Mathematics.quaternion m_EndRotation`  

```csharp
public Unity.Mathematics.quaternion m_EndRotation;
```



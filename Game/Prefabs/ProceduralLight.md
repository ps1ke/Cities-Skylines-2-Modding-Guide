# Game.Prefabs.ProceduralLight

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ProceduralLight : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float4 m_Color;
    public Unity.Mathematics.float4 m_Color2;
    public Game.Prefabs.EmissiveProperties+Purpose m_Purpose;
    public System.Single m_ResponseSpeed;
    public System.Int32 m_AnimationIndex;

}
```


## Fields

- `public Unity.Mathematics.float4 m_Color`  

```csharp
public Unity.Mathematics.float4 m_Color;
```

- `public Unity.Mathematics.float4 m_Color2`  

```csharp
public Unity.Mathematics.float4 m_Color2;
```

- `public Game.Prefabs.EmissiveProperties+Purpose m_Purpose`  

```csharp
public Game.Prefabs.EmissiveProperties+Purpose m_Purpose;
```

- `public System.Single m_ResponseSpeed`  

```csharp
public System.Single m_ResponseSpeed;
```

- `public System.Int32 m_AnimationIndex`  

```csharp
public System.Int32 m_AnimationIndex;
```



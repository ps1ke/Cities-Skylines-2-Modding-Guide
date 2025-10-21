# Game.Tools.LocalTransformCache

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct LocalTransformCache : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public System.Int32 m_ParentMesh;
    public System.Int32 m_GroupIndex;
    public System.Int32 m_Probability;
    public System.Int32 m_PrefabSubIndex;

}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public System.Int32 m_ParentMesh`  

```csharp
public System.Int32 m_ParentMesh;
```

- `public System.Int32 m_GroupIndex`  

```csharp
public System.Int32 m_GroupIndex;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
```

- `public System.Int32 m_PrefabSubIndex`  

```csharp
public System.Int32 m_PrefabSubIndex;
```



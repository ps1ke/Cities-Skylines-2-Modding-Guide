# Game.Prefabs.SubObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubObject : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Game.Prefabs.SubObjectFlags m_Flags;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public System.Int32 m_ParentIndex;
    public System.Int32 m_GroupIndex;
    public System.Int32 m_Probability;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Game.Prefabs.SubObjectFlags m_Flags`  

```csharp
public Game.Prefabs.SubObjectFlags m_Flags;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public System.Int32 m_ParentIndex`  

```csharp
public System.Int32 m_ParentIndex;
```

- `public System.Int32 m_GroupIndex`  

```csharp
public System.Int32 m_GroupIndex;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
```



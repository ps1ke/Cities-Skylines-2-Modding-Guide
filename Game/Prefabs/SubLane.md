# Game.Prefabs.SubLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubLane : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Colossal.Mathematics.Bezier4x3 m_Curve;
    public Unity.Mathematics.int2 m_NodeIndex;
    public Unity.Mathematics.int2 m_ParentMesh;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Colossal.Mathematics.Bezier4x3 m_Curve`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Curve;
```

- `public Unity.Mathematics.int2 m_NodeIndex`  

```csharp
public Unity.Mathematics.int2 m_NodeIndex;
```

- `public Unity.Mathematics.int2 m_ParentMesh`  

```csharp
public Unity.Mathematics.int2 m_ParentMesh;
```



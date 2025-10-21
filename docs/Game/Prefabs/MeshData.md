# Game.Prefabs.MeshData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct MeshData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Game.Prefabs.MeshFlags m_State;
    public Game.Rendering.DecalLayers m_DecalLayer;
    public Game.Prefabs.MeshLayer m_DefaultLayers;
    public Game.Prefabs.MeshLayer m_AvailableLayers;
    public Game.Prefabs.MeshType m_AvailableTypes;
    public System.Byte m_MinLod;
    public System.Byte m_ShadowLod;
    public System.Single m_LodBias;
    public System.Single m_ShadowBias;
    public System.Single m_SmoothingDistance;
    public System.Int32 m_SubMeshCount;
    public System.Int32 m_IndexCount;
    public System.Int32 m_TilingCount;

}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Game.Prefabs.MeshFlags m_State`  

```csharp
public Game.Prefabs.MeshFlags m_State;
```

- `public Game.Rendering.DecalLayers m_DecalLayer`  

```csharp
public Game.Rendering.DecalLayers m_DecalLayer;
```

- `public Game.Prefabs.MeshLayer m_DefaultLayers`  

```csharp
public Game.Prefabs.MeshLayer m_DefaultLayers;
```

- `public Game.Prefabs.MeshLayer m_AvailableLayers`  

```csharp
public Game.Prefabs.MeshLayer m_AvailableLayers;
```

- `public Game.Prefabs.MeshType m_AvailableTypes`  

```csharp
public Game.Prefabs.MeshType m_AvailableTypes;
```

- `public System.Byte m_MinLod`  

```csharp
public System.Byte m_MinLod;
```

- `public System.Byte m_ShadowLod`  

```csharp
public System.Byte m_ShadowLod;
```

- `public System.Single m_LodBias`  

```csharp
public System.Single m_LodBias;
```

- `public System.Single m_ShadowBias`  

```csharp
public System.Single m_ShadowBias;
```

- `public System.Single m_SmoothingDistance`  

```csharp
public System.Single m_SmoothingDistance;
```

- `public System.Int32 m_SubMeshCount`  

```csharp
public System.Int32 m_SubMeshCount;
```

- `public System.Int32 m_IndexCount`  

```csharp
public System.Int32 m_IndexCount;
```

- `public System.Int32 m_TilingCount`  

```csharp
public System.Int32 m_TilingCount;
```



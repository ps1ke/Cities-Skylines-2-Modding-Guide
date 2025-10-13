# Game.Prefabs.NetCompositionMeshData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct NetCompositionMeshData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.MeshLayer m_DefaultLayers;
    public Game.Prefabs.MeshLayer m_AvailableLayers;
    public Game.Prefabs.MeshFlags m_State;
    public Game.Prefabs.CompositionFlags m_Flags;
    public Colossal.Mathematics.Bounds1 m_HeightRange;
    public System.Single m_Width;
    public System.Single m_MiddleOffset;
    public System.Single m_IndexFactor;
    public System.Single m_LodBias;
    public System.Single m_ShadowBias;
    public System.Int32 m_Hash;

}
```


## Fields

- `public Game.Prefabs.MeshLayer m_DefaultLayers`  

```csharp
public Game.Prefabs.MeshLayer m_DefaultLayers;
```

- `public Game.Prefabs.MeshLayer m_AvailableLayers`  

```csharp
public Game.Prefabs.MeshLayer m_AvailableLayers;
```

- `public Game.Prefabs.MeshFlags m_State`  

```csharp
public Game.Prefabs.MeshFlags m_State;
```

- `public Game.Prefabs.CompositionFlags m_Flags`  

```csharp
public Game.Prefabs.CompositionFlags m_Flags;
```

- `public Colossal.Mathematics.Bounds1 m_HeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightRange;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_MiddleOffset`  

```csharp
public System.Single m_MiddleOffset;
```

- `public System.Single m_IndexFactor`  

```csharp
public System.Single m_IndexFactor;
```

- `public System.Single m_LodBias`  

```csharp
public System.Single m_LodBias;
```

- `public System.Single m_ShadowBias`  

```csharp
public System.Single m_ShadowBias;
```

- `public System.Int32 m_Hash`  

```csharp
public System.Int32 m_Hash;
```



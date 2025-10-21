# Game.Rendering.GroupData

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct GroupData
{
    public Unity.Entities.Entity m_Mesh;
    public Unity.Mathematics.float3 m_SecondaryCenter;
    public Unity.Mathematics.float3 m_SecondarySize;
    public Game.Prefabs.MeshLayer m_Layer;
    public Game.Prefabs.MeshType m_MeshType;
    public System.UInt16 m_Partition;
    public Game.Rendering.BatchRenderFlags m_RenderFlags;
    public System.Byte m_LodCount;
    private Game.Rendering.GroupData+<m_Properties>e__FixedBuffer m_Properties;
    private static const System.Int32 MAX_PROPERTY_COUNT1;
    private static const System.Int32 MAX_PROPERTY_COUNT2;
    public static const System.Int32 MAX_PROPERTY_COUNT;

    public System.Boolean GetPropertyIndex(System.Int32 property, System.Int32& index);
    public System.Void SetPropertyIndex(System.Int32 property, System.Int32 index);
}
```


## Fields

- `public Unity.Entities.Entity m_Mesh`  

```csharp
public Unity.Entities.Entity m_Mesh;
```

- `public Unity.Mathematics.float3 m_SecondaryCenter`  

```csharp
public Unity.Mathematics.float3 m_SecondaryCenter;
```

- `public Unity.Mathematics.float3 m_SecondarySize`  

```csharp
public Unity.Mathematics.float3 m_SecondarySize;
```

- `public Game.Prefabs.MeshLayer m_Layer`  

```csharp
public Game.Prefabs.MeshLayer m_Layer;
```

- `public Game.Prefabs.MeshType m_MeshType`  

```csharp
public Game.Prefabs.MeshType m_MeshType;
```

- `public System.UInt16 m_Partition`  

```csharp
public System.UInt16 m_Partition;
```

- `public Game.Rendering.BatchRenderFlags m_RenderFlags`  

```csharp
public Game.Rendering.BatchRenderFlags m_RenderFlags;
```

- `public System.Byte m_LodCount`  

```csharp
public System.Byte m_LodCount;
```

- `private Game.Rendering.GroupData+<m_Properties>e__FixedBuffer m_Properties`  

```csharp
private Game.Rendering.GroupData+<m_Properties>e__FixedBuffer m_Properties;
```

- `private static const System.Int32 MAX_PROPERTY_COUNT1`  

```csharp
private static const System.Int32 MAX_PROPERTY_COUNT1;
```

- `private static const System.Int32 MAX_PROPERTY_COUNT2`  

```csharp
private static const System.Int32 MAX_PROPERTY_COUNT2;
```

- `public static const System.Int32 MAX_PROPERTY_COUNT`  

```csharp
public static const System.Int32 MAX_PROPERTY_COUNT;
```


## Methods

- `public GetPropertyIndex(System.Int32 property, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean GetPropertyIndex(System.Int32 property, System.Int32& index);
```

- `public SetPropertyIndex(System.Int32 property, System.Int32 index) : System.Void`  

```csharp
public System.Void SetPropertyIndex(System.Int32 property, System.Int32 index);
```


## Nested types

- `Game.Rendering.GroupData+<m_Properties>e__FixedBuffer`  


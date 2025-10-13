# Game.Prefabs.MeshMaterial

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MeshMaterial : Unity.Entities.IBufferElementData
{
    public System.Int32 m_StartIndex;
    public System.Int32 m_IndexCount;
    public System.Int32 m_StartVertex;
    public System.Int32 m_VertexCount;
    public System.Int32 m_MaterialIndex;

    public MeshMaterial(System.Int32 startIndex, System.Int32 indexCount, System.Int32 startVertex, System.Int32 vertexCount, System.Int32 materialIndex);

}
```


## Fields

- `public System.Int32 m_StartIndex`  

```csharp
public System.Int32 m_StartIndex;
```

- `public System.Int32 m_IndexCount`  

```csharp
public System.Int32 m_IndexCount;
```

- `public System.Int32 m_StartVertex`  

```csharp
public System.Int32 m_StartVertex;
```

- `public System.Int32 m_VertexCount`  

```csharp
public System.Int32 m_VertexCount;
```

- `public System.Int32 m_MaterialIndex`  

```csharp
public System.Int32 m_MaterialIndex;
```


## Constructors

- `public MeshMaterial(System.Int32 startIndex, System.Int32 indexCount, System.Int32 startVertex, System.Int32 vertexCount, System.Int32 materialIndex)`  

```csharp
public MeshMaterial(int startIndex, int indexCount, int startVertex, int vertexCount, int materialIndex)
	{
		m_StartIndex = startIndex;
		m_IndexCount = indexCount;
		m_StartVertex = startVertex;
		m_VertexCount = vertexCount;
		m_MaterialIndex = materialIndex;
	}
```



# Game.Prefabs.SubAreaNode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubAreaNode : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float3 m_Position;
    public System.Int32 m_ParentMesh;

    public SubAreaNode(Unity.Mathematics.float3 position, System.Int32 parentMesh);

}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public System.Int32 m_ParentMesh`  

```csharp
public System.Int32 m_ParentMesh;
```


## Constructors

- `public SubAreaNode(Unity.Mathematics.float3 position, System.Int32 parentMesh)`  

```csharp
public SubAreaNode(float3 position, int parentMesh)
	{
		m_Position = position;
		m_ParentMesh = parentMesh;
	}
```



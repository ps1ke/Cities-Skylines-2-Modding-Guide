# Game.Rendering.BatchMeshHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BatchMeshHelpers
{
    public static Unity.Jobs.JobHandle GenerateMeshes(Game.Rendering.BatchMeshSystem meshSystem, Unity.Collections.NativeList<Unity.Entities.Entity> meshes, UnityEngine.Mesh+MeshDataArray meshDataArray, Unity.Jobs.JobHandle dependencies);
}
```


## Methods

- `public static GenerateMeshes(Game.Rendering.BatchMeshSystem meshSystem, Unity.Collections.NativeList<Unity.Entities.Entity> meshes, UnityEngine.Mesh+MeshDataArray meshDataArray, Unity.Jobs.JobHandle dependencies) : Unity.Jobs.JobHandle`  

```csharp
public static JobHandle GenerateMeshes(BatchMeshSystem meshSystem, NativeList<Entity> meshes, Mesh.MeshDataArray meshDataArray, JobHandle dependencies)
	{
		return IJobParallelForExtensions.Schedule(new GenerateBatchMeshJob
		{
			m_Entities = meshes,
			m_MeshData = meshSystem.GetComponentLookup<MeshData>(isReadOnly: true),
			m_CompositionMeshData = meshSystem.GetComponentLookup<NetCompositionMeshData>(isReadOnly: true),
			m_CompositionPieces = meshSystem.GetBufferLookup<NetCompositionPiece>(isReadOnly: true),
			m_MeshVertices = meshSystem.GetBufferLookup<MeshVertex>(isReadOnly: true),
			m_MeshNormals = meshSystem.GetBufferLookup<MeshNormal>(isReadOnly: true),
			m_MeshTangents = meshSystem.GetBufferLookup<MeshTangent>(isReadOnly: true),
			m_MeshUV0s = meshSystem.GetBufferLookup<MeshUV0>(isReadOnly: true),
			m_MeshIndices = meshSystem.GetBufferLookup<MeshIndex>(isReadOnly: true),
			m_MeshNodes = meshSystem.GetBufferLookup<MeshNode>(isReadOnly: true),
			m_MeshMaterials = meshSystem.GetBufferLookup<MeshMaterial>(),
			m_MeshDataArray = meshDataArray
		}, meshes.Length, 1, dependencies);
	}
```


## Nested types

- `Game.Rendering.BatchMeshHelpers+GenerateBatchMeshJob`  


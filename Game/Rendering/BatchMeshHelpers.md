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
public static Unity.Jobs.JobHandle GenerateMeshes(Game.Rendering.BatchMeshSystem meshSystem, Unity.Collections.NativeList<Unity.Entities.Entity> meshes, UnityEngine.Mesh+MeshDataArray meshDataArray, Unity.Jobs.JobHandle dependencies);
```


## Nested types

- `Game.Rendering.BatchMeshHelpers+GenerateBatchMeshJob`  

